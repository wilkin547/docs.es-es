---
title: Procedimiento para enlazar el control DataGrid de formularios Windows Forms a un origen de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666435"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="e78be-102">Procedimiento para enlazar el control DataGrid de formularios Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="e78be-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
>  <span data-ttu-id="e78be-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="e78be-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="e78be-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="e78be-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="e78be-105">Los formularios de Windows <xref:System.Windows.Forms.DataGrid> control está diseñado específicamente para mostrar información de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e78be-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="e78be-106">Enlazar el control en tiempo de ejecución mediante una llamada a la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e78be-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="e78be-107">Aunque se pueden mostrar datos desde una variedad de orígenes de datos, los orígenes más habituales son las vistas de datos y conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="e78be-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="e78be-108">Para enlazar el control DataGrid mediante programación</span><span class="sxs-lookup"><span data-stu-id="e78be-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="e78be-109">Escribir código para llenar el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e78be-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="e78be-110">Si el origen de datos es un conjunto de datos o una vista de datos basado en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e78be-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="e78be-111">El código exacto que utilice depende de donde obtiene datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e78be-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="e78be-112">Si el conjunto de datos se rellena directamente desde una base de datos, normalmente se invoca el `Fill` método de un adaptador de datos, como se muestra en el ejemplo siguiente, que rellena un conjunto de datos denominado `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="e78be-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="e78be-113">Si se llena el conjunto de datos desde un servicio Web XML, normalmente se crea una instancia del servicio en el código y, a continuación, llame a uno de sus métodos devuelvan un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e78be-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="e78be-114">A continuación, combina el conjunto de datos desde el servicio Web XML en el conjunto de datos local.</span><span class="sxs-lookup"><span data-stu-id="e78be-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="e78be-115">El ejemplo siguiente muestra cómo puede crear una instancia de un servicio Web XML denominado `CategoriesService`, llame a su `GetCategories` método y mezcla el conjunto de datos resultante en un conjunto de datos local llamado `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="e78be-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="e78be-116">Llame a la <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método y pásele el origen de datos y un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="e78be-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="e78be-117">Si no es necesario pasar explícitamente un miembro de datos, pase una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e78be-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e78be-118">Si va a enlazar la cuadrícula por primera vez, puede establecer el control <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="e78be-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="e78be-119">Sin embargo, no se puede restablecer estas propiedades una vez que se han establecido.</span><span class="sxs-lookup"><span data-stu-id="e78be-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="e78be-120">Por lo tanto, se recomienda usar siempre el <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e78be-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="e78be-121">El ejemplo siguiente muestra cómo se puede enlazar mediante programación a la tabla Customers en un conjunto de datos denominado `DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="e78be-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="e78be-122">Si la tabla Customers es la única tabla en el conjunto de datos, también puede enlazar la cuadrícula de esta manera:</span><span class="sxs-lookup"><span data-stu-id="e78be-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="e78be-123">(Opcional) Agregar los estilos de tabla adecuada y estilos de columna a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e78be-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="e78be-124">Si no hay ningún estilo de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.</span><span class="sxs-lookup"><span data-stu-id="e78be-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78be-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e78be-125">See also</span></span>

- [<span data-ttu-id="e78be-126">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="e78be-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="e78be-127">Cómo: Agregar tablas y columnas al Control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e78be-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="e78be-128">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="e78be-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="e78be-129">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e78be-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
