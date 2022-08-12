<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/522844306/22.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T1108444)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
# Rich Edit for Blazor - How to export a document to a file in HTML format

This example adds a custom button to the **Download** menu on the **File** tab. Click this button to export an open document to a file in HTML format and save it in the project folder.

![Blazor DxRichEdit export a document to the HTML](/images/export-to-html.png)

Currently, the [Rich Text Editor](https://docs.devexpress.com/Blazor/401891/rich-text-editor) does not support the HTML format. You can use the [RichEditDocumentServer](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer) component to import and export documents in HTML format. To add this component to your application, install the [DevExpress.RichEdit.Core](https://nuget.devexpress.com/packages/DevExpress.RichEdit.Core/) package.

The [CustomizeRibbon](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.CustomizeRibbon) event allows you to access and customize the built-in ribbon UI. Call the [AddCustomButton](https://docs.devexpress.com/Blazor/DevExpress.Blazor.Office.BarItemCollection.AddCustomButton(System.String-System.Func-System.Threading.Tasks.Task-)) in the event handler to add a custom button to the ribbon. Perform the following actions in response to a click on this button to export an open document to a file in HTML format:

1. [Save](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.SaveDocumentAsync(System.Threading.CancellationToken)) the open document's content.
2. Initialize a new instance of the [RichEditDocumentServer](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer) class.
3. [Load](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer.LoadDocument(System.Byte--)) the document content to the document server.
4. *(Optional)* Customize the document server's [export options](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditControlOptionsBase.Export).
5. [Save](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer.SaveDocument(DevExpress.XtraRichEdit.DocumentFormat)) the document to a file in HTML format.

## Files to Look At

- [Index.razor](./CS/ExportToHtml/Pages/Index.razor)

## Documentation

- [Document Management in the Rich Text Editor](https://docs.devexpress.com/Blazor/403344/rich-edit/document-management)
- [Rich Text Editor Examples](https://docs.devexpress.com/Blazor/403343/rich-edit/examples)
- [Word Processing Document API](https://docs.devexpress.com/OfficeFileAPI/17488/word-processing-document-api)
 
