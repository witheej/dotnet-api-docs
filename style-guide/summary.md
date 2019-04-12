# Summary Section

The summary succinctly states what a type or member does or represents. All types and members must have summaries, consisting of a short description (optimally one sentence) that conveys the importance of the class or member.

## Guidelines

Begin with a present-tense, third-person verb, except for exception classes, enum members, abstract members, and virtual members (see the links in the next section).

- Do not merely repeat the wording of the member name in the summary; provide a meaningful description and context. For example, instead of describing the **String.Format** method by saying *Formats a string*, you can use a description like this: *Replaces each format item in a specified string with the string representation of a specified object.*
- Use programming language-neutral text. For example, don't include Visual Basic or C#-specific terms in your summary.
- Avoid using special formatting such as lists that might cause problems for IntelliSense builds.
- Avoid using parameter names or self-referential type or member names in the summary. There are exceptions; for example, you can use the type name in summaries for constructors and for dispose methods.
- For overloaded constructors and methods, provide a general summary that is broad enough to apply to all the overloads, and write more specific summaries for the individual overloads. For the individual overloads, use wording that differentiates each overload from the others, and provide enough information to help users select the overload they'd like to call.

## Wording for specific types and members

The wording for Summary sections varies according to the type or member that you're documenting, as described in these sections:

- [Class](#class)
- [Constructor](#constructor)
- [Enum](#enum)
- [Event-related](#event-related)
- [Field](#field)
- [Abstract and virtual member](#abstract-and-virtual-member)
- [Method](#method)
- [Operator](#operator)
- [Property](#property)
- [Overloaded member](#overloaded-member)

## Class

The following table provides wording guidelines, boilerplate text, and examples of Summary sections in class pages. For event-related classes, such as **EventArgs** and event-handler delegates, see the [Event-related](#event-related) section.

| Item | Wording | Examples |
|------|---------|----------|
| General class, interface, or struct | \<Begin with a present-tense third-person verb.> | ***DataGrid*** *class summary:*<br />Displays XDO data in a scrollable grid.<br /><br />***TimeSpan*** *struct summary*:<br />Represents a time interval. |
| Interface | Defines...,   or Provides..,. or Exposes... | ***IComparable*** *interface summary*:<br />Defines a generalized type-specific comparison method that a value type or class implements to order or sort its instances.<br />***IFormattable*** *interface summary*:<br /><br />Provides functionality to format the value of an object into a string representation. |
| Abstract base class | Defines the core behavior of *\<class name or feature>* and provides a base for *\<derived classes or derivations>*.  | ***BaseNotificationEventType*** *class summary:*<br />Defines the core behavior of notification events and provides a base for derived classes.<br /><br />***MessageQuery*** *class summary*:<br />Defines the core behavior of classes that are used to search for specific correlating data in a message. |
| Class that represents a standard Windows control (for example, a button or check box) | Represents a Windows *\<control>* control. | ***Windows.Forms.Button*** *class*<br />Represents a Windows button control. |
| Exception class | The exception that is thrown when/for/by *\<condition>*.<br /><br /> **Note:**<br />This summary does not begin with a verb. | ***ArgumentOutOfRangeException*** *class summary:*<br />The exception that is thrown when the value of an argument is outside the allowable range of values as defined by the invoked method.<br /><br />***ComponentModel.Win32Exception*** *class summary:*<br />The exception that is thrown for a Win32 error code.<br />***Reflection.TargetInvocationException*** *class summary:*<br />The exception that is thrown by methods invoked through reflection. |

## Constructor

The following table provides wording guidelines and boilerplate text for Summary sections in constructor pages. For guidelines on documenting overloaded constructors, see the [Overloaded member](#overloaded-member) section.

| Item | Wording | Examples |
|------|---------|----------|
| Constructor, class | Initializes a new instance of the *\<Class>* class. | **WebProxy** *constructor summary:*<br />Initializes a new instance of the **WebProxy** class. |
| Constructor, abstract class | Called from constructors in derived classes to initialize the *\<Class>* class. | **Aes** *constructor summary:*<br />Called from constructors in derived classes to initialize the **Aes** class. |
| Constructor, struct | Initializes a new instance of the *\<Struct>* struct. | **SqlInt64** *constructor summary:*<br />Initializes a new instance of the **SqlInt64** struct using the supplied long integer. |

## Enum

The following table provides wording guidelines and boilerplate text for Summary sections in enum pages and its members.

| Item | Wording | Examples |
|------|---------|----------|
| Enum | \<Begin with a present-tense third-person verb, such as *Specifies* or *Describes*.>  | ***FormBorderStyle*** *enum summary:*<br />Specifies the border styles for a form.<br /><br />***MouseButtons*** *enum summary:*<br />Specifies constants that define which mouse button was pressed. |
| Enum member | \<Noun phrase. Begin with an introductory article, if appropriate.> | ***BorderStyle.FixedSingle*** *enum member summary:*<br />A single-line border. |
| Enum member used as a mask | A mask used to retrieve \<noun phrase>.<br /><br />**Note:**<br />If the enum member will be used as a mask, call this out, and specify the information to be retrieved using the mask. | ***MethodAttributes.MemberAccessMask*** *enum member summary:*<br />A mask used to retrieve the scope of a method. |

## Event-related

The following table provides wording guidelines and boilerplate text for Summary sections in event and event-related class pages.

| Item | Wording | Examples |
|------|---------|----------|
| Event | Occurs when *\<condition>*.  | **Click** event summary:<br />Occurs when the user clicks the control. |
| \<EventArgs> class | Provides data for the *\<Event>* event. | ***ComponentRenameEventArgs*** *class summary:*<br />Provides data for the **ComponentRename** event. |
| Event-handler delegate class, specific to one event on a control | Represents the callback method that will handle the *\<Event>* event of a *\<Class>*. | ***PeekCompletedEventHandler*** *delegate summary:*<br />Represents the callback method that will handle the **PeekCompleted** event of a **MessageQueue**. |
| Event-handler delegate class, specific to multiple events on a control | Represents the callback method that will handle the *\<Event1>* event, *\<Event2>* event, or *\<Event3>* event of a *\<Class>*. | ***PrintEventHandler*** *delegate summary:*<br />Represents the callback method that will handle the **BeginPrint** event or **EndPrint** event of a **PrintDocument**. |
| Event-handler delegate class, specific to one event on multiple controls | Represents the callback method that will handle the *\<Event>* event of a *\<Class1>* or a *\<Class2>*. | ***MeasureItemEventHandler*** *delegate summary:*<br />Represents the callback method that will handle the **MeasureItem** event of a **ListBox**, **ComboBox**, **CheckedListBox**, or **MenuItem** control. |
| Event-handler delegate class, generic | Represents the callback method that will handle an event of a control. | ***EventHandler Generic*** *delegate summary*<br />Represents the callback method that will handle the event. |
|**On**_\<Event>_ method\* | Raises the *\<Event>* event. | ***Control.OnBackgroundImageChanged*** *method summary:*<br />Raises the **BackgroundImageChanged** event. |

\* **Note:**
In some cases, such as the **WebPart** class, a method named **On***EventName* might not raise the *EventName* event. For example, **WebPart** defines four methods named **OnClosing**, **OnConnectModeChanged**, **OnDeleting**, and **OnEditModeChanged**. Derived classes override these methods and provide special handling for the state transitions named by the methods. Thus, the description of the **OnClosing** method reads, "*Enables derived classes to provide custom handling when* a **WebPart** control is closed on a Web Parts page." The phrase in italics is the appropriate pattern for such summaries. <br />Because this naming pattern violates .NET naming guidelines, the writer should raise the naming issue in the design phase, if the opportunity arises. A name such as **ClosingNotification** or **ClosingCallback** would be more appropriate in this scenario.<br />Other special cases in WPF and Silverlight content use either "Provides class handling for the *EventName* routed event" or "Called before the *EventName* event occurs" for the summary.

## Field

The following table provides wording guidelines and boilerplate text for Summary sections in field pages.

| Item | Wording | Examples |
|------|---------|----------|
| Field | \<Begin with a present-tense third-person verb, such as *Specifies* or *Represents*.> | ***MessageBox.YesNo*** *summary:*<br />Specifies that the message box should display Yes and No buttons.<br /><br />***Registry.CLASSES_ROOT*** *summary:*<br />Represents the HKEY_CLASSES_ROOT registry key. |

## Abstract and virtual member

The following table provides wording guidelines and boilerplate text for Summary sections for abstract and virtual members of abstract classes.

| Item | Wording | Examples |
|------|---------|----------|
| Abstract member of an abstract class | When overridden in a derived class, \<continue with a present-tense third-person verb stating what the member does>. | ***XmlWriter.Close*** *member summary:*<br />When overridden in a derived class, closes this stream and the underlying stream. |
| Virtual member of an abstract class that does not provide the intended implementation | When overridden in a derived class, \<continue with a present-tense third-person verb stating what the member does>.<br /><br />**Note:**<br />In the Remarks section, include a sentence that explains the default, unintended behavior. | ***Stream.ReadByte*** *summary:*<br />When overridden in a derived class, reads the next byte from this stream and advances the current position of the stream by one.<br /><br />*Include the following in* ***Stream.ReadByte*** *remarks:*<br />Because the **Stream** class doesn't support reading, **ReadByte** throws a **NotSupportedException** exception by default. |

## Method

The following table provides wording guidelines and boilerplate text for Summary sections in method pages. For guidelines about **On**_\<Event>_ methods, see the [Event-related](#event-related) section. For guidelines about documenting overloaded methods, see [Overloaded member](#overloaded-member).

| Item | Wording | Examples |
|------|---------|----------|
| General method  | \<Begin with a present-tense third-person verb.> | ***DataGrid*** *class summary:*<br />Displays XDO data in a scrollable grid.<br /><br />***Application.DoEvents*** *method summary:*<br />Processes Windows messages that are currently in the message queue. |
| **Dispose** method, general overload | Releases the resources used by the current instance of the **\<class>** class. | ***ComponentDesigner.Dispose*** *method summary:*<br />Releases the resources used by the current instance of the **ComponentDesigner** class. |
| **Dispose()** method | Releases the resources used by the current instance of the **\<class>** class. | ***Timer.Dispose*** *method summary:*<br />Releases the resources used by the current instance of the **Timer** class. |
| **Dispose(Boolean)** method | Called by the **Dispose()** and **Finalize()** methods to release the managed and unmanaged resources used by the current instance of the **\<class>** class.  | ***DocumentDesigner.Dispose*** *method (Boolean):*<br />Called by the **Dispose()** and **Finalize()** methods to release the managed and unmanaged resources used by the current instance of the **DocumentDesigner** class. |
| **ShouldSerialize** *\<Property>* method | Indicates whether the *\<Property>* property should be persisted. | ***DataGrid.ShouldSerializeBackgroundColor*** *method summary:*<br />Indicates whether the **BackgroundColor** property should be persisted. |
| **Reset**_\<Property>_ method | Resets the *\<Property>* property to its default value. | ***Control.ResetText*** *method summary:*<br />Resets the **Text** property to its default value. |
| Method that always throws an exception | Throws a/an *\<ExceptionType>* exception in all cases.<br /><br />**Note:**<br />In the Remarks section, explain why the member is not supported. | ***DataGridViewSelectedRowCollection.Clear*** *method summary:*<br />Throws a **NotSupportedException** exception in all cases. |
| Explicit interface method implementation | \<Copy from the interface member if appropriate> |

## Operator

The following table provides wording guidelines and boilerplate text for Summary sections in operator pages. For guidelines about documenting overloaded operators, see [Overloaded member](#overloaded-member).

| Item | Wording | Examples |
|------|---------|----------|
| Unary/binary operator; for example, + operator | \<Begin with a present-tense verb.> | ***Unit*** *+ operator summary:*<br />Adds a value to a **Unit**. |
| Conversion operator | Converts a *\<Type>* to a *\<Type>*.<br /><br />**Note:**<br />If one type is a primitive, use the language-neutral phrase for it. | *Decimal to 32-bit integer conversion summary:*<br />Converts a decimal to a 32-bit signed integer. |

## Property

The following table provides wording guidelines and boilerplate text for Summary sections in property pages.

> An indexer is the C# term for an indexed property. An indexer takes a parameter that indexes the value of the property. In C#, an indexer is defined with the **this** keyword. For example: `public string this[int index]`. In Visual Basic, an indexer is equivalent to a default indexed property named Item.

| Item | Wording | Examples |
|------|---------|----------|
| Read/write property or indexer | *Boolean:*<br />Gets or sets a value that indicates whether *\<condition>*.<br />*Other:*<br />Gets or sets *\<summary without specifying the type>*.  | ***Control.AllowDrop*** *property summary:*<br />Gets or sets a value that indicates whether the control can accept data that the user drags onto it.<br /><br />***Control.BackColor*** *property summary:*<br />Gets or sets the background color for the control. |
| Read-only property or indexer | *Boolean:*<br />Gets a value that indicates whether *\<condition>*.<br /><br />Other:<br />Gets *\<summary without specifying the type>*.<br /><br />**Note:**<br />It isn't necessary to say "This property is read-only." | **Type.IsByRef** property summary:<br />Gets a value that indicates whether the **Type** is passed by reference.<br />***Type.DefaultBinder*** *property summary:*<br />Gets the default binder used by the system. |
| Explicit interface property implementation | \<Copy from the interface member if appropriate> | |

## Overloaded member

The following information provides guidelines for writing Summary sections for overloaded constructors, operators, and methods.

For overloaded members, docs.microsoft.com creates an overload list page with a general summary as well as individual pages for each overload. The overload list page provides a general summary that applies to all the overloads followed by a table with specific summaries for each overload. (For an example, see the [System.TimeSpan constructors page](https://docs.microsoft.com/dotnet/api/system.timespan.-ctor).) To write the general summary and the individual summaries, follow the guidelines in this section.

### General summary for an overloaded member

When a class explicitly defines multiple overloads, docs.microsoft.com can display a summary for the entire group of overloads and then a list of the different overloads is listed with the individual summaries. You must write the general summary broadly enough to apply to all the individual overloads. Follow the summary wording guidelines for the particular kind of member you're documenting (for more information, see the relevant subsection in this article), and use text that is programming language-neutral. For an example, see the table in the next section.

### Summaries for individual overloads

Provide a separate summary for each individual overload topic in docs.microsoft.com. Use wording that reflects that overload's parameters and distinguishes that overload from the general summary and from the summaries of other overloads. The summary should provide enough information to help users select the overload that they'd like to call.

For example, here's the general summary and individual overload summaries for the overloaded [System.IO.BinaryReader.Read](https://docs.microsoft.com/dotnet/api/system.io.binaryreader.read?view=netframework-4.8) method.

|   |   |   |
|---|---|---|
| General summary (overload list page) | **System.IO.BinaryReader.Read** | Reads bytes from the underlying stream and advances the current position of the stream. |
| Individual overload summary | **System.IO.BinaryReader.Read ()** | Reads characters from the underlying stream and advances the current position of the stream in accordance with the encoding used and the specific character being read from the stream. |
| Individual overload summary | **System.IO.BinaryReader.Read (Byte[], Int32, Int32)** | Reads the specified number of bytes from the stream, starting from a specified point in the byte array. |
| Individual overload summary | **System.IO.BinaryReader.Read (Char[], Int32, Int32)** | Reads the specified number of characters from the stream, starting from a specified point in the character array.
