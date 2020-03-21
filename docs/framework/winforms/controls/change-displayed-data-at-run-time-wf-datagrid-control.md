---
title: Cambiar los datos mostrados en tiempo de ejecución en DataGrid Control
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142386"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="2ef65-102">Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ef65-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="2ef65-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="2ef65-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="2ef65-104">Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2ef65-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="2ef65-105">Después de crear <xref:System.Windows.Forms.DataGrid> un formulario Windows Forms con las características en tiempo de <xref:System.Data.DataSet> diseño, es posible que también desee cambiar dinámicamente los elementos del objeto de la cuadrícula en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ef65-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="2ef65-106">Esto puede incluir cambios en los valores individuales de <xref:System.Windows.Forms.DataGrid> la tabla o cambiar el origen de datos que está enlazado al control.</span><span class="sxs-lookup"><span data-stu-id="2ef65-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="2ef65-107">Los cambios en los <xref:System.Data.DataSet> valores individuales se realizan a través del objeto, no del <xref:System.Windows.Forms.DataGrid> control.</span><span class="sxs-lookup"><span data-stu-id="2ef65-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="2ef65-108">Para cambiar los datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="2ef65-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="2ef65-109">Especifique la tabla <xref:System.Data.DataSet> deseada del objeto y la fila y el campo deseados de la tabla y establezca la celda igual al nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2ef65-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2ef65-110">Para especificar la primera <xref:System.Data.DataSet> tabla de la o la primera fila de la tabla, utilice 0.</span><span class="sxs-lookup"><span data-stu-id="2ef65-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="2ef65-111">En el ejemplo siguiente se muestra cómo cambiar la segunda entrada de `Button1`la primera fila de la primera tabla de un conjunto de datos haciendo clic en .</span><span class="sxs-lookup"><span data-stu-id="2ef65-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="2ef65-112">Se <xref:System.Data.DataSet> `ds`crearon anteriormente las tablas ( y ) (`0` y `1`).</span><span class="sxs-lookup"><span data-stu-id="2ef65-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="2ef65-113">(Visual C, Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="2ef65-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="2ef65-114">En tiempo de ejecución, puede usar el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método para enlazar el <xref:System.Windows.Forms.DataGrid> control a un origen de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="2ef65-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="2ef65-115">Por ejemplo, puede tener varios controles de datos ADO.NET, cada uno conectado a una base de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="2ef65-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="2ef65-116">Para cambiar el DataSource mediante programación</span><span class="sxs-lookup"><span data-stu-id="2ef65-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="2ef65-117">Establezca <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> el método en el nombre del origen de datos y la tabla a la que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="2ef65-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="2ef65-118">En el ejemplo siguiente se muestra <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> cómo cambiar el origen de fecha mediante el método a un ADO.NET control de datos (adoPubsAuthors) que está conectado a la authors tabla en el Pubs base de datos.</span><span class="sxs-lookup"><span data-stu-id="2ef65-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ef65-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ef65-119">See also</span></span>

- [<span data-ttu-id="2ef65-120">Objetos DataSet de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2ef65-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="2ef65-121">Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ef65-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="2ef65-122">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ef65-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="2ef65-123">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="2ef65-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
