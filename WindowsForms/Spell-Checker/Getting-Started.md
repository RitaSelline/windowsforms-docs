---
layout: post
title: Getting-Started | SpellCheckerAdv | WindowsForms | Syncfusion
description: gettingstarted
platform: WindowsForms
control: SpellCheckerAdv
documentation: ug
---

# Getting started

This section describes how to add a [SpellCheckerAdv](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Tools.Windows~Syncfusion.Windows.Forms.Tools.SpellCheckerAdv.html) control in a Windows Forms application and overview of its basic functionalities.

## Assembly deployment

Refer [control dependencies](https://help.syncfusion.com/windowsforms/control-dependencies#spellchecker) section to get the list of assemblies or NuGet package needs to be added as reference to use the control in any application.
 
Please find more details regarding how to install the nuget packages in windows form application in the below link:
 
[How to install nuget packages](https://help.syncfusion.com/windowsforms/nuget-packages)

## Creating simple application with SpellCheckerAdv

You can create the Windows Forms application with SpellCheckerAdv control as follows:

1. [Creating project](#creating-the-project)
2. [Add control via designer](#add-control-via-designer)
3. [Add control manually using Code](#add-control-manually-using-code)
4. [Configuring SpellCheckerAdv into RichTextBox control](#configuring-spellCheckerAdv-into-RichTextBox-control)
5. [Applying Dictionary](#applying-dictionary)
6. [Applying Custom Dictionary](#applying-custom-dictionary)
7. [Configuring VisualStyle](#configuring-VisualStyle)

### Creating the project

Create a new Windows Forms project in the Visual Studio to display the SpellCheckerAdv with basic information.

## Add control via designer

SpellCheckerAdv control can be added to the application by dragging it from the toolbox and dropping it in a designer view. The following required assembly references will be added automatically:

* Syncfusion.Grid.Base.dll
* Syncfusion.Grid.Windows.dll
* Syncfusion.Shared.Base.dll
* Syncfusion.Shared.Windows.dll
* Syncfusion.SpellChecker.Base.dll
* Syncfusion.Tools.Base.dll
* Syncfusion.Tools.Windows.dll

![Search SpellCheckerAdv in Toolbox](Getting-Started_images/ToolBox.png)

![SpellCheckerAdv control added in designer](Getting-Started_images/SpellCheckerAdv-img2.png)

## Add control manually using Code

To add control manually in C#, follow the given steps:

**Step 1** : Add the following required assembly references to the project:

 * Syncfusion.Tools.Base.dll
 * Syncfusion.Tools.Windows.dll
 * Syncfusion.Shared.Base.dll
 * Syncfusion.Shared.Windows.dll
 * Syncfusion.SpellChecker.Base.dll
 * Syncfusion.Grid.Base.dll
 * Syncfusion.Grid.Windows.dll

**Step 2** : Include the namespaces **Syncfusion.Windows.Forms.Tools**.

{% tabs %}

{% highlight C# %}

using Syncfusion.Windows.Forms.Tools;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.Windows.Forms.Tools

{% endhighlight %}

{% endtabs %}

**Step 3** :  Create `SpellCheckerAdv` control instance.

{% tabs %}

{% highlight C# %}

SpellCheckerAdv spellCheckerAdv1 = new SpellCheckerAdv();

{% endhighlight %}

{% highlight VB %}

Dim spellCheckerAdv1 As SpellCheckerAdv = New SpellCheckerAdv

{% endhighlight %}

{% endtabs %}

## Configuring SpellCheckerAdv into RichTextBox control

**Step 1** : Create a class implementing [ISpellCheckerAdvEditorTools](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Tools.Windows~Syncfusion.Windows.Forms.Tools.ISpellCheckerAdvEditorTools.html) interface as shown below.

{% tabs %}

{% highlight C# %}

  class TextBoxSpellEditor : ISpellCheckerAdvEditorTools
    {
        /// <summary>
        /// Initializes the TextBoxBase control.
        /// </summary>
        private TextBoxBase textBox;
        /// <summary>
        /// Initializes the new instance of the TextBoxSpellEditor class.
        /// </summary>
        /// <param name="control"></param>
        public TextBoxSpellEditor(Control control)
        {
            Control = control;
        }
        /// <summary>
        /// Gets or sets the Control whose Text is to be spell checked.
        /// </summary>
        public Control Control
        {
            get
            {
                return textBox;
            }
            set
            {
                textBox = value as TextBoxBase;
            }
        }
        /// <summary>
        /// Gets or sets the current misspelled word.
        /// </summary>
        public string CurrentWord
        {
            get
            {
                return textBox.Text;
            }
            set
            {
                textBox.Text = value;
            }
        }
        /// <summary>
        /// Gets or sets the Text to be spell checked by the <see cref="SpellCheckerAdv"/>
        /// </summary>
        public string Text
        {
            get
            {
                return textBox.Text;
            }
            set
            {
                textBox.Text = value;
            }
        }
        /// <summary>
        /// Gets or sets the Control whose Text is to be spell checked.
        /// </summary>
        public Control ControlToCheck
        {
            get
            {
                return textBox;
            }
            set
            {
                textBox = value as TextBoxBase;
            }
        }
        /// <summary>
        ///  Selects the word specified by the index.
        /// </summary>
        /// <param name="selectionStart">Zero based index of the word on the Text.</param>
        /// <param name="selectionLength">length of the word to be selected.</param>
        public void SelectText(int selectionStart, int selectionLength)
        {
            textBox.Select(selectionStart, selectionLength);
        }
    }

{% endhighlight %}

{% highlight VB %}

class TextBoxSpellEditor
           Implements ISpellCheckerAdvEditorTools
        ''' <summary>
        ''' Initializes the TextBoxBase control.
        ''' </summary>
        Private textBox As TextBoxBase;
        ''' <summary>
        ''' Initializes the new instance of the TextBoxSpellEditor class.
        ''' </summary>
        ''' <param name="control"></param>
       Public Sub New(control__1 As Control)
		Control = control__1
	End Sub
    ''' <summary>
	''' Gets or sets the Control whose Text is to be spell checked.
	''' </summary>
	Public Property Control() As Control
		Get
			Return textBox
		End Get
		Set
			textBox = TryCast(value, TextBoxBase)
		End Set
	End Property
	''' <summary>
	''' Gets or sets the current misspelled word.
	''' </summary>
	Public Property CurrentWord() As String
		Get
			Return textBox.Text
		End Get
		Set
			textBox.Text = value
		End Set
	End Property
        ''' <summary>
	''' Gets or sets the Control whose Text is to be spell checked.
	''' </summary>
	Public Property ControlToCheck() As Control
		Get
			Return textBox
		End Get
		Set
			textBox = value as TextBoxBase
		End Set
	End Property
	''' <summary>
	''' Gets or sets the Text to be spell checked by the <see cref="SpellCheckerAdv"/>
	''' </summary>
	Public Property Text() As String
		Get
			Return textBox.Text
		End Get
		Set
			textBox.Text = value
		End Set
	End Property
	''' <summary>
	'''  Selects the word specified by the index.
	''' </summary>
	''' <param name="selectionStart">Zero based index of the word on the Text.</param>
	''' <param name="selectionLength">length of the word to be selected.</param>
	Public Sub SelectText(selectionStart As Integer, selectionLength As Integer)
		textBox.[Select](selectionStart, selectionLength)
	End Sub
End Class

{% endhighlight %}

{% endtabs %}

**Step 2** - Create instances `RichTextBox` (Editor Control to be spell checked) and `Button` and add it to the form.

{% tabs %}

{% highlight C# %}

RichTextBox richTextBox1 = new RichTextBox();
Button button1 = new Button();

this.richTextBox1.Text = resources.GetString("richTextBox1.Text");
this.button1.Text="Spell Check";

this.Controls.Add(this.button1);
this.Controls.Add(this.richTextBox1);

{% endhighlight %}

{% highlight VB %}

Dim richTextBox1 As RichTextBox = New RichTextBox
Dim button1 As Button = New Button

Me.richTextBox1.Text = resources.GetString("richTextBox1.Text")
Me.button1.Text="Spell Check"

Me.Controls.Add(Me.button1)
Me.Controls.Add(Me.richTextBox1)

{% endhighlight %}

{% endtabs %}

![Spell checker](Getting-Started_images/SpellCheckerAdv-img1.png)

**Step 3** - Create an instance of the `TextBoxSpellEditor` class by having `RichTextBox` as its Control and it to `SpellCheckerAdv` using [PerformSpellCheckForControl](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Tools.Windows~Syncfusion.Windows.Forms.Tools.SpellCheckerAdv~PerformSpellCheckForControl.html) method.

{% tabs %}

{% highlight C# %}

TextBoxSpellEditor TextEditor = new TextBoxSpellEditor(this.richTextBox1);

this.spellCheckerAdv1.PerformSpellCheckForControl(TextEditor);

{% endhighlight %}

{% highlight VB %}

Dim TextEditor As New TextBoxSpellEditor(Me.richTextBox1)

Me.spellCheckerAdv1.PerformSpellCheckForControl(TextEditor)

{% endhighlight %}

{% endtabs %}

**Step 4** - Finally trigger `SpellCheckerAdv` through an event such as `Click` of the button as given below.

{% tabs %}

{% highlight C# %}

private void buttonAdv1_Click(object sender, EventArgs e)
{
  this.spellCheckerAdv1.SpellCheck(new SpellCheckerAdvEditorWrapper(this.richTextBox1));
}

{% endhighlight %}

{% highlight VB %}

Private Sub buttonAdv1_Click(sender As Object, e As EventArgs)
	Me.spellCheckerAdv1.SpellCheck(New SpellCheckerAdvEditorWrapper(Me.richTextBox1))
End Sub

{% endhighlight %}

{% endtabs %}

![SpellChecking for loaded text](Getting-Started_images/GettingStarted2.png)

## Applying dictionary

SpellCheckerAdv provide built-in dictionary whose Path can be set using [DictionaryPath](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Tools.Windows~Syncfusion.Windows.Forms.Tools.SpellCheckerAdv~DictionaryPath.html) property in SpellCheckerAdv.

{% tabs %}

{% highlight C# %}

this.spellCheckerAdv1.DictionaryPath = "Syncfusion_en_us.dic";

{% endhighlight %}

{% highlight VB %}

Me.spellCheckerAdv1.DictionaryPath = "Syncfusion_en_us.dic"

{% endhighlight %}

{% endtabs %}


## Applying custom dictionary

SpellCheckerAdv provides built-in dictionary for English Language and also helps to configure based on your own language, using its Custom Dictionary option. Custom Dictionary can be added using [CustomDictionaryPath](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Tools.Windows~Syncfusion.Windows.Forms.Tools.SpellCheckerAdv~CustomDictionaryPath.html) property.

{% tabs %}

{% highlight C# %}

private static String DEF_CUSTOM_DIC_PATH = Application.CommonAppDataPath + Path.DirectorySeparatorChar + "Custom_Dictionary.dic";

this.spellCheckerAdv1.CustomDictionaryPath = DEF_CUSTOM_DIC_PATH;

{% endhighlight %}

{% highlight VB %}

Private static DEF_CUSTOM_DIC_PATH As String = Application.CommonAppDataPath + Path.DirectorySeparatorChar & "Custom_Dictionary.dic"

Me.spellCheckerAdv1.CustomDictionaryPath = DEF_CUSTOM_DIC_PATH

{% endhighlight %}

{% endtabs %}

## Configuring VisualStyle

Look and feel of the SpellCheckerAdv can be customize using [VisualStyle](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Tools.Windows~Syncfusion.Windows.Forms.Tools.SpellCheckerAdv~VisualStyle.html) property.

{% tabs %}

{% highlight C# %}

this.spellCheckerAdv1.VisualStyle = SpellCheckerAdvStyle.Office2016Colorful;

{% endhighlight %}

{% highlight VB %}

Me.spellCheckerAdv1.VisualStyle = SpellCheckerAdvStyle.Office2016Colorful

{% endhighlight %}

{% endtabs %}

![SpellCheckerAdv style](Getting-Started_images/GettingStarted2.png)