---
Description: Ink collection begins with the digitizer.
ms.assetid: 95e49f5b-d6f0-4a5a-868b-aa0caf87c39c
title: Ink Collection
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Ink Collection

Ink collection begins with the digitizer. A user places a pen on the digitizer and starts to write. You can use the ink collection features of the API to manage the collection of ink data that "flows" from the pen. You have access to information about the available hardware on Tablet PC through the [**Tablets**](/windows/desktop/api/msinkaut/) collection and the [**Tablet**](/windows/desktop/api/msinkaut/nn-msinkaut-iinktablet) object. You then use the [**InkCollector**](/windows/desktop/api/msinkaut/) object to get the data that comes from the digitizer.

## Tablets and the Tablet Object

A [**Tablet**](/windows/desktop/api/msinkaut/nn-msinkaut-iinktablet) represents a digitizer device of Tablet PC. A Tablet PC may have more than one digitizer. Using the **Tablet** object, you can query for the available digitizer devices that are attached to Tablet PC and their respective hardware capabilities. For example, you can determine if the **Tablet** you are working with is integrated with the display or is a separate external device.

## InkCollector Object

The [**InkCollector**](/windows/desktop/api/msinkaut/) object captures ink input from available [**Tablet**](/windows/desktop/api/msinkaut/nn-msinkaut-iinktablet) devices. The **InkCollector** object only collects ink and gestures that are input into a specific window. A very efficient event sink renders this input in real time. The **InkCollector** object captures the input and directs it into an [**Ink**](/windows/desktop/api/msinkaut/) object.

> [!Note]  
> Simultaneously laying down ink with multiple pens may or may not work, depending on the hardware capabilities of the digitizer device.

 

### How the Ink Collector Works

The [**InkCollector**](/windows/desktop/api/msinkaut/) object attaches itself to a known application window. It then enables users to employ any available Tablet PC device (including the mouse) to lay down ink in real time on that window. The ink strokes that it collects are stored in an associated [**Ink**](/windows/desktop/api/msinkaut/) object. These strokes can then be manipulated or sent to a recognizer for recognition. The **InkCollector** object also notifies the application when a cursor comes into range of any of the Tablet PC devices that are being used.

For the [**InkCollector**](/windows/desktop/api/msinkaut/) object to accurately set the mouse cursor within an ink-enabled window, that window must be able to receive the **WM\_SETCURSOR** message. This is successful for all regular windows but, for a control within a dialog box, the dialog parent of the control filters this message. For the control to receive the message, set the **SS\_NOTIFY** style.

## InkOverlay Object

The [**InkCollector**](/windows/desktop/api/msinkaut/) object, discussed previously, is useful for applications to provide their own model for selecting, erasing, and other user interaction. The [**InkOverlay**](/windows/desktop/api/msinkaut/) object is a superset of the **InkCollector** object that provides editing support. This is useful for applications to integrate ink drawing and editing into their own document canvas by using a set of standard ink selection models that the object provides.

Both the [**InkCollector**](/windows/desktop/api/msinkaut/) object and the [**InkOverlay**](/windows/desktop/api/msinkaut/) object (as well as the [InkPicture](inkpicture-control.md) control) use common constructs, such as the [**Ink**](/windows/desktop/api/msinkaut/) object and the [**DrawingAttributes**](/windows/desktop/api/msinkaut/) collection, so that the basic way to change the color of ink is the same everywhere. This enables you to reuse code and to have common programmatic access, which can be particularly important if you offer scripting support in your application.

[**InkOverlay**](/windows/desktop/api/msinkaut/) is a COM object that is useful for annotation scenarios in which users are not concerned with performing recognition on ink but, instead, are interested in the size, shape, color, and position of the ink. It is well suited for taking notes and basic scribbling. The default user interface is a transparent rectangle with opaque ink.

[**InkOverlay**](/windows/desktop/api/msinkaut/) extends the [**InkCollector**](/windows/desktop/api/msinkaut/) class in three ways:

-   It raises events for begin-stroke, end-stroke, and ink attribute changes.
-   It enables users to select, erase, and resize ink.
-   It supports Cut, Copy, and Paste commands.

A typical scenario in which [**InkOverlay**](/windows/desktop/api/msinkaut/) is useful is in marking up a presentation slide or image. The **InkOverlay** object enables easy implementation of the ink and layout capabilities that this scenario requires.

To work with [**InkOverlay**](/windows/desktop/api/msinkaut/), you:

1.  Instantiate an [**InkOverlay**](/windows/desktop/api/msinkaut/) object.
2.  Attach the hWnd (handle, in managed code) of a window to the [**InkOverlay**](/windows/desktop/api/msinkaut/) object's [**hWnd**](/windows/desktop/api/msinkaut/) property ([Handle](https://www.bing.com/search?q=Handle) property, in managed code).
3.  Set the [**InkOverlay**](/windows/desktop/api/msinkaut/) object's [**Enabled**](/windows/desktop/api/msinkaut/) property to **TRUE**.

The [**InkOverlay**](/windows/desktop/api/msinkaut/) object includes basic printing support, but you must implement print preview or other advanced printing capabilities.

[**InkOverlay**](/windows/desktop/api/msinkaut/) persists ink in ink serialized format (ISF).

> [!Note]  
> If the [**InkOverlay**](/windows/desktop/api/msinkaut/) object's [**EditingMode**](/windows/desktop/api/msinkaut/) is set to **Delete** or **Select**, other events (such as [**InkAdded**](inkdisp-inkadded.md), [**InkDeleted**](inkdisp-inkdeleted.md), and [**Stroke**](inkoverlay-stroke.md)) are triggered. These events are useful if you want to implement your own delete or select modes.

 

### Selecting Ink

The [**InkOverlay**](/windows/desktop/api/msinkaut/) object enables users to use a lasso tool to select ink objects that are contained in a traced region. Users can also select ink by tapping any [**Ink**](/windows/desktop/api/msinkaut/) object.

Use the [**Selection**](/windows/desktop/api/msinkaut/) property to return a [**Strokes**](/windows/desktop/api/msinkaut/) collection that you can use to manipulate a user's selection.

When an [**Ink**](/windows/desktop/api/msinkaut/) object or a set of **Ink** objects is selected, sizing handles appear at the four corners of the ink's bounding box and at all midpoints between adjacent corners. If the user drags anywhere within the selected region, the ink becomes movable inside the control.

### Default Behavior

The [**InkOverlay**](/windows/desktop/api/msinkaut/) object is set to collect ink by default. Ink is 53 ink space units wide (where 1 ink space unit = 1 HIMETRIC). Ink is black if the user is not running in high-contrast mode. Otherwise, ink is set to the **COLOR\_WINDOWTEXT** value (**WindowText** in managed code). [**FitToCurve**](/windows/desktop/api/msinkaut/) is **FALSE**.

### Cursor and Button Objects

A cursor corresponds to the tip of the pen that is used on Tablet PC. For instance, a pencil has two ends. Usually, one end is used for writing and the other is used for erasing. These two ends correspond to two cursors. The [**Cursor**](/windows/desktop/api/msinkaut/nn-msinkaut-iinkcursor) class is not be confused with [**System.Windows.Forms.Cursor**](https://www.bing.com/search?q=**System.Windows.Forms.Cursor**).

On Tablet PC, a cursor is usually defined to be used either for writing or erasing. A cursor may potentially change roles if the application enables this functionality. Some Tablet PC devices allow multiple pens. Each cursor has an associated cursor ID that is unique on the system. A cursor can have zero or more associated buttons. These buttons are provided to the application as CursorButton objects. The application can provide a specific [**DrawingAttributes**](/windows/desktop/api/msinkaut/) object for any given cursor.

### Drawing Attributes Object

A [**DrawingAttributes**](/windows/desktop/api/msinkaut/) object describes how any known set of ink is to be drawn. A **DrawingAttributes** object includes basic properties such as [**Color**](/windows/desktop/api/msinkaut/), [**Width**](/windows/desktop/api/msinkaut/), and [**PenTip**](/windows/desktop/api/msinkaut/). It can also encompass advanced parameters, such as variable transparency and Bezier smoothing, that can provide interesting effects or improve ink readability.

### PenInputPanel Object

> [!Note]  
> The [**PenInputPanel**](/windows/desktop/api/msinkaut/) class has been deprecated. The **PenInputPanel** class has been replaced by the [**TextInputPanel**](/windows/desktop/api/peninputpanel/nn-peninputpanel-itextinputpanel) class.

 

The [**PenInputPanel**](/windows/desktop/api/msinkaut/) object allows you to easily add in-place pen input to your applications. The **PenInputPanel** is available as an attachable object that allows you to add Tablet PC Input Panel functionality to existing controls. The user interface is largely mandated by the current input language. You have the option of choosing the default input method for the **PenInputPanel**, either handwriting or keyboard. The end user can switch between input methods using buttons on the user interface.

## Related topics

<dl> <dt>

[**InkCollector Class (C++)**](/windows/desktop/api/msinkaut/)
</dt> <dt>

[**InkOverlay Class (C++)**](/windows/desktop/api/msinkaut/)
</dt> <dt>

[**Microsoft.Ink Namespace**](https://www.bing.com/search?q=**Microsoft.Ink+Namespace**)
</dt> </dl>

 

 


