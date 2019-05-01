---
title: Procedimiento para cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms
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
ms.openlocfilehash: 60ba1e9304320346d505f3f73e1ba93ff6edab63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961660"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="76851-102">Procedimiento para cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76851-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="76851-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="76851-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="76851-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="76851-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="76851-105">Después de haber creado un formulario Windows Forms <xref:System.Windows.Forms.DataGrid> con las características de tiempo de diseño, es posible que también desee cambiar dinámicamente los elementos de la <xref:System.Data.DataSet> objeto de la cuadrícula en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76851-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="76851-106">Esto puede incluir los cambios realizados en valores individuales de la tabla o cambiar el origen de datos se enlaza a la <xref:System.Windows.Forms.DataGrid> control.</span><span class="sxs-lookup"><span data-stu-id="76851-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="76851-107">Los cambios realizados en los valores individuales se realizan a través de la <xref:System.Data.DataSet> objeto, no el <xref:System.Windows.Forms.DataGrid> control.</span><span class="sxs-lookup"><span data-stu-id="76851-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="76851-108">Para cambiar datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="76851-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="76851-109">Especifique la tabla deseada desde la <xref:System.Data.DataSet> objeto y la fila y el campo de la tabla y establece la celda igual que el nuevo valor deseado.</span><span class="sxs-lookup"><span data-stu-id="76851-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="76851-110">Para especificar la primera tabla de la <xref:System.Data.DataSet> o la primera fila de la tabla, utilice 0.</span><span class="sxs-lookup"><span data-stu-id="76851-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="76851-111">El ejemplo siguiente muestra cómo cambiar la segunda entrada de la primera fila de la primera tabla de un conjunto de datos, haga clic en `Button1`.</span><span class="sxs-lookup"><span data-stu-id="76851-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="76851-112">El <xref:System.Data.DataSet> (`ds`) y las tablas (`0` y `1`) fueron creados previamente.</span><span class="sxs-lookup"><span data-stu-id="76851-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="76851-113">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="76851-113">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="76851-114">En puede usar el tiempo de ejecución el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método para enlazar el <xref:System.Windows.Forms.DataGrid> control a un origen de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="76851-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="76851-115">Por ejemplo, pueden tener varios [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] controles de datos, cada uno conectado a una base de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="76851-115">For example, you may have several [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="76851-116">Para cambiar el origen de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="76851-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="76851-117">Establecer el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método en el nombre del origen de datos y la tabla que desea enlazar a.</span><span class="sxs-lookup"><span data-stu-id="76851-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="76851-118">El ejemplo siguiente muestra cómo cambiar el origen de fecha mediante el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método a un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] control de datos (adoPubsAuthors) que está conectado a la tabla Authors de la base de datos Pubs.</span><span class="sxs-lookup"><span data-stu-id="76851-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76851-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="76851-119">See also</span></span>

- [<span data-ttu-id="76851-120">Objetos DataSet de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="76851-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="76851-121">Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76851-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="76851-122">Cómo: Agregar tablas y columnas al Control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76851-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="76851-123">Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="76851-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
