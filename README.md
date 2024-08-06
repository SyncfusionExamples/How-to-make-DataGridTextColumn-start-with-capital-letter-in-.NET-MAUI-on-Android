# How to make DataGridTextColumn start with capital letter in .NET MAUI on Android
In this article, we will show you how to make DataGridTextColumn start with capital letter in [.Net Maui DataGrid](https://www.syncfusion.com/maui-controls/maui-datagrid) on Android. The soft input keyboard presented when users interact with an Entry can be set programmatically via the Keyboard property. The Keyboard class also has a Create factory method that can be used to customize a keyboard by specifying capitalization, spellcheck, and suggestion behavior. KeyboardFlags enumeration values are specified as arguments to the method, with a customized Keyboard being returned.

Documentation link : [Customize the Keyboard](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/entry?view=net-maui-8.0#customize-the-keyboard)

## C#
The code below illustrates how to make a DataGridTextColumn start with a capital letter in a DataGrid on the Android platform using a CustomTextBox CellRenderer.
```
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            dataGrid.CellRenderers.Remove("Text");
            dataGrid.CellRenderers.Add("Text", new CustomTextRenderer());
        }
    }

    public class CustomTextRenderer : DataGridTextBoxCellRenderer
    {
        public override void OnInitializeEditView(DataColumnBase dataColumn, SfDataGridEntry view)
        {
            base.OnInitializeEditView(dataColumn, view);
            if (view != null && view is Entry entry)
            {
                entry.Keyboard = Keyboard.Create(KeyboardFlags.CapitalizeWord);
            }
        }
    }
```
 ![AndroidKeyboardImg.png](https://support.syncfusion.com/kb/agent/attachment/inline?token=eyJhbGciOiJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzA0L3htbGRzaWctbW9yZSNobWFjLXNoYTI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjI3ODAwIiwib3JnaWQiOiIzIiwiaXNzIjoic3VwcG9ydC5zeW5jZnVzaW9uLmNvbSJ9.4E9iElTsqEfQsp3U-kRDVcA7KraZI5npkdFUURLbGmk)

[View sample in GitHub](https://github.com/SyncfusionExamples/How-to-make-DataGridTextColumn-start-with-capital-letter-in-.NET-MAUI-on-Android)

Take a moment to explore this [documentation](https://help.syncfusion.com/maui/datagrid/overview), where you can find more information about Syncfusion .NET MAUI DataGrid (SfDataGrid) with code examples. Please refer to this [link](https://www.syncfusion.com/maui-controls/maui-datagrid) to learn about the essential features of Syncfusion .NET MAUI DataGrid (SfDataGrid).
 
##### Conclusion
 
I hope you enjoyed learning about how to make DataGridTextColumn start with capital letter in .NET MAUI DataGrid (SfDataGrid) on android platform.
 
You can refer to our [.NET MAUI DataGrid’s feature tour](https://www.syncfusion.com/maui-controls/maui-datagrid) page to learn about its other groundbreaking feature representations. You can also explore our [.NET MAUI DataGrid Documentation](https://help.syncfusion.com/maui/datagrid/getting-started) to understand how to present and manipulate data. 
For current customers, you can check out our .NET MAUI components on the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/maui) to explore our .NET MAUI DataGrid and other .NET MAUI components.
 
If you have any queries or require clarifications, please let us know in the comments below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [Direct-Trac](https://support.syncfusion.com/create) or [feedback portal](https://www.syncfusion.com/feedback/maui?control=sfdatagrid), or the feedback portal. We are always happy to assist you!