---
title: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: f91e2ea01ef4a52dd649efed70319017efb8368a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740595"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="5e916-102">Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5e916-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="5e916-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="5e916-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="5e916-104">Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5e916-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="5e916-105">Después de crear un Windows Forms <xref:System.Windows.Forms.DataGrid> mediante las características de tiempo de diseño, puede que también desee cambiar dinámicamente los elementos del objeto <xref:System.Data.DataSet> de la cuadrícula en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5e916-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="5e916-106">Esto puede incluir cambios en los valores individuales de la tabla o en cambiar el origen de datos enlazado al control de <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="5e916-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="5e916-107">Los cambios en los valores individuales se realizan a través del objeto <xref:System.Data.DataSet>, no del control <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="5e916-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="5e916-108">Para cambiar los datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="5e916-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="5e916-109">Especifique la tabla deseada del objeto <xref:System.Data.DataSet> y la fila y el campo deseados de la tabla y establezca la celda igual al nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="5e916-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5e916-110">Para especificar la primera tabla del <xref:System.Data.DataSet> o de la primera fila de la tabla, use 0.</span><span class="sxs-lookup"><span data-stu-id="5e916-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="5e916-111">En el ejemplo siguiente se muestra cómo cambiar la segunda entrada de la primera fila de la primera tabla de un conjunto de filas haciendo clic en `Button1`.</span><span class="sxs-lookup"><span data-stu-id="5e916-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="5e916-112">Los <xref:System.Data.DataSet> (`ds`) y las tablas (`0` y `1`) se crearon previamente.</span><span class="sxs-lookup"><span data-stu-id="5e916-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="5e916-113">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5e916-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="5e916-114">En tiempo de ejecución, puede utilizar el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> para enlazar el control de <xref:System.Windows.Forms.DataGrid> a un origen de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="5e916-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="5e916-115">Por ejemplo, puede tener varios controles de datos ADO.NET, cada uno conectado a una base de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="5e916-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="5e916-116">Para cambiar el origen de los código mediante programación</span><span class="sxs-lookup"><span data-stu-id="5e916-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="5e916-117">Establezca el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> en el nombre del origen de datos y la tabla a la que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e916-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="5e916-118">En el ejemplo siguiente se muestra cómo cambiar el origen de fecha mediante el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> a un control de datos ADO.NET (adoPubsAuthors) que está conectado a la tabla authors en la base de datos pubs.</span><span class="sxs-lookup"><span data-stu-id="5e916-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5e916-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e916-119">See also</span></span>

- [<span data-ttu-id="5e916-120">Objetos DataSet de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5e916-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="5e916-121">Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5e916-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="5e916-122">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5e916-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="5e916-123">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="5e916-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
