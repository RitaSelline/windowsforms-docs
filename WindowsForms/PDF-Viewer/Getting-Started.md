---
layout: post
title: Getting-Started | Windows Forms | Syncfusion
description: This section describes about how to create PdfViewer control in Windows Forms application.
platform: windowsforms
control: PdfViewerControl
documentation: ug
---

# Getting Started

## Adding reference to PdfViewerControl and dependent assemblies

Refer to the [Control Dependencies](https://help.syncfusion.com/windowsforms/control-dependencies#pdf-viewer) section to get the list of assemblies.

### Installing NuGet packages

Adding reference to Syncfusion assemblies through NuGet packages is illustrated in the [NuGet Packages](https://help.syncfusion.com/windowsforms/nuget-packages) section. 

N> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [this link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Windows Forms application to use our components.

### Adding from the installed location

The PdfViewerControl and dependent assemblies can be found from the below location in your machine. 

system drive:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\precompiledassemblies\{{ site.releaseversion }}\

## Adding PdfViewerControl to an Application

### Adding in designer


1) Open your form in the designer. Add the Syncfusion controls to your .NET toolbox in Visual Studio if you haven't done so already (the install would have automatically done this unless you selected not to complete toolbox integration during installation).
   
   ![Windows forms pdfviewer drag and drop from toolbox](Getting-Started_images/Getting-Started_img1.png)





2) Drag the PdfViewerControl from the toolbox onto the form.



   Appearance and behavior related aspects of the PdfViewerControl can be controlled by setting the appropriate properties through the properties grid. 

   ![Windows forms pdfviewer displays properties window of control](Getting-Started_images/Getting-Started_img2.png)
   

3) This will add the instance 'pdfViewerControl1' to the Designer cs file. The PDF can be loaded in the Form cs file using the [Load](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.PdfViewer.Windows~Syncfusion.Windows.Forms.PdfViewer.PdfViewerControl~Load(String).html) method. 

{% tabs %}
{% highlight c# %}

//Loading the document in the PdfViewerControl
pdfViewerControl1.Load("Sample.pdf");

{% endhighlight %}
{% highlight vb %}

'Loading the document in the PdfViewerControl
pdfViewerControl1.Load("Sample.pdf")

{% endhighlight %}
{% endtabs %}
	
### Adding manually in code

1) Add Syncfusion.Windows.Forms.PdfViewer namespace.

{% tabs %}
{% highlight c# %}

using Syncfusion.Windows.Forms.PdfViewer;

{% endhighlight %}
{% highlight vb %}

Imports Syncfusion.Windows.Forms.PdfViewer

{% endhighlight %}
{% endtabs %}
		
		
2) Create PdfViewerControl instance and load the PDF

{% tabs %}
{% highlight c# %}

//Initializing the PdfViewerControl
PdfViewerControl pdfViewerControl1 = new PdfViewerControl();

//Loading the document in the PdfViewerControl
pdfViewerControl1.Load("Sample.pdf");

//Add PdfViewerControl to the Form
Controls.Add(pdfViewerControl1);

{% endhighlight %}
{% highlight vb %}

'Initializing the PdfViewerControl
Dim pdfViewerControl1 As PdfViewerControl = New PdfViewerControl()

'Loading the document in the PdfViewerControl
pdfViewerControl1.Load("Sample.pdf")

'Add PdfViewerControl to the Form
Controls.Add(pdfViewerControl1)

{% endhighlight %}
{% endtabs %}
   
   Refer to [Viewing PDF files](/windowsforms/pdfviewer/working-with-pdf-viewer#viewing-pdf-files) for more information.

## Appearance and Structure of the Control

The following screenshot depicts different sections of the PdfViewerControl.

![Windows forms pdfviewer displays different section of control](Getting-Started_images/Getting-Started_img3.png)


### Toolbar

![Windows forms pdfviewer displays the toolbar](Getting-Started_images/Getting-Started_img4.png)



1. Open file
2. Bookmark 
3. Save document
4. Print PDF
5. Go to first page
6. Go to previous page
7. Page indicator
8. Go to next page
9. Go to last page
10. Preset magnification
11. Decrease magnification
12. Increase magnification
13. Fill window
14. Fit page to window