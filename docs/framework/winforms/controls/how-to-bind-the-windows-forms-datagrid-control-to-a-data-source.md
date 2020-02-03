---
title: Enlazar el control DataGrid a un origen de datos
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
ms.openlocfilehash: 2634a6bd8ace36bcf7a49120162474a8c04b2b83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746692"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="73735-102">Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="73735-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="73735-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="73735-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="73735-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="73735-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="73735-105">El control <xref:System.Windows.Forms.DataGrid> de Windows Forms está diseñado específicamente para mostrar información de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="73735-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="73735-106">Puede enlazar el control en tiempo de ejecución llamando al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="73735-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="73735-107">Aunque puede mostrar los datos de diversos orígenes de datos, los orígenes más habituales son los conjuntos de datos y las vistas de datos.</span><span class="sxs-lookup"><span data-stu-id="73735-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="73735-108">Para enlazar datos mediante programación al control DataGrid</span><span class="sxs-lookup"><span data-stu-id="73735-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="73735-109">Escriba código para rellenar el conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="73735-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="73735-110">Si el origen de datos es un conjunto de datos o una vista de datos basada en una tabla de conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="73735-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="73735-111">El código exacto que se utiliza depende de la ubicación del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="73735-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="73735-112">Si el conjunto de datos se rellena directamente desde una base de datos, normalmente se llama al método `Fill` de un adaptador de datos, como en el ejemplo siguiente, que rellena un conjunto de datos denominado `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="73735-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="73735-113">Si el conjunto de resultados se rellena desde un servicio Web XML, normalmente se crea una instancia del servicio en el código y, a continuación, se llama a uno de sus métodos para devolver un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="73735-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="73735-114">A continuación, combine el conjunto de DataSet del servicio Web XML en el conjunto de DataSet local.</span><span class="sxs-lookup"><span data-stu-id="73735-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="73735-115">En el ejemplo siguiente se muestra cómo se puede crear una instancia de un servicio Web XML denominado `CategoriesService`, llamar a su método `GetCategories` y combinar el conjunto de resultados en un conjunto de elementos local denominado `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="73735-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
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
  
2. <span data-ttu-id="73735-116">Llame al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del control <xref:System.Windows.Forms.DataGrid>, pasándole el origen de datos y un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="73735-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="73735-117">Si no necesita pasar explícitamente un miembro de datos, pase una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="73735-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="73735-118">Si enlaza la cuadrícula por primera vez, puede establecer las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> del control.</span><span class="sxs-lookup"><span data-stu-id="73735-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="73735-119">Sin embargo, no puede restablecer estas propiedades una vez que se han establecido.</span><span class="sxs-lookup"><span data-stu-id="73735-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="73735-120">Por lo tanto, se recomienda usar siempre el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="73735-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="73735-121">En el ejemplo siguiente se muestra cómo se puede enlazar mediante programación a la tabla Customers en un conjunto de elementos denominado `DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="73735-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="73735-122">Si la tabla Customers es la única tabla del conjunto de elementos, puede enlazar la cuadrícula como alternativa de esta manera:</span><span class="sxs-lookup"><span data-stu-id="73735-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="73735-123">Opta Agregue los estilos de tabla y de columna correspondientes a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="73735-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="73735-124">Si no hay ningún estilo de tabla, verá la tabla, pero con el formato mínimo y con todas las columnas visibles.</span><span class="sxs-lookup"><span data-stu-id="73735-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73735-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73735-125">See also</span></span>

- [<span data-ttu-id="73735-126">Información general del control DataGrid</span><span class="sxs-lookup"><span data-stu-id="73735-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="73735-127">Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73735-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="73735-128">DataGrid (control)</span><span class="sxs-lookup"><span data-stu-id="73735-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="73735-129">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73735-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
