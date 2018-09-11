---
title: 'Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 932d30d356225d88d7ef149561cc4c5cc8ac4dd0
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271054"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="03a16-102">Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03a16-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="03a16-103">Puede exponer la ordenación y filtrado de capacidad de <xref:System.Windows.Forms.BindingSource> controlar a través de la <xref:System.Windows.Forms.BindingSource.Sort%2A> y <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="03a16-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="03a16-104">Puede aplicar la ordenación simple si el origen de datos subyacente es un <xref:System.ComponentModel.IBindingList>, y puede aplicar el filtrado y ordenación cuando el origen de datos es avanzada un <xref:System.ComponentModel.IBindingListView>.</span><span class="sxs-lookup"><span data-stu-id="03a16-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="03a16-105">El <xref:System.Windows.Forms.BindingSource.Sort%2A> propiedad requiere estándar [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] sintaxis: una cadena que representa el nombre de una columna de datos del origen de datos seguida `ASC` o `DESC` para indicar si la lista debe ordenarse en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="03a16-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="03a16-106">Puede establecer la ordenación avanzada o varias columnas de ordenación separando cada columna con un separador de coma.</span><span class="sxs-lookup"><span data-stu-id="03a16-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="03a16-107">El <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedad toma una expresión de cadena.</span><span class="sxs-lookup"><span data-stu-id="03a16-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03a16-108">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03a16-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="03a16-109">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="03a16-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="03a16-110">Para más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="03a16-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="03a16-111">Para filtrar los datos con el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="03a16-111">To filter data with the BindingSource</span></span>  
  
-   <span data-ttu-id="03a16-112">Establecer el <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedad a la expresión que desea.</span><span class="sxs-lookup"><span data-stu-id="03a16-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="03a16-113">En el ejemplo de código siguiente, la expresión es un nombre de columna seguido de valor que desee para la columna.</span><span class="sxs-lookup"><span data-stu-id="03a16-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="03a16-114">Para ordenar los datos con el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="03a16-114">To sort data with the BindingSource</span></span>  
  
1.  <span data-ttu-id="03a16-115">Establecer el <xref:System.Windows.Forms.BindingSource.Sort%2A> propiedad en el nombre de columna que desee seguido `ASC` o `DESC` para indicar el orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="03a16-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2.  <span data-ttu-id="03a16-116">Separe varias columnas con una coma.</span><span class="sxs-lookup"><span data-stu-id="03a16-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="03a16-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03a16-117">Example</span></span>  
 <span data-ttu-id="03a16-118">El siguiente ejemplo de código carga los datos de la tabla Customers de la base de datos de ejemplo Northwind en un <xref:System.Windows.Forms.DataGridView> controlar y filtra y ordena los datos mostrados.</span><span class="sxs-lookup"><span data-stu-id="03a16-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03a16-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="03a16-119">Compiling the Code</span></span>  
 <span data-ttu-id="03a16-120">Para ejecutar este ejemplo, pegue el código en un formulario que contenga un <xref:System.Windows.Forms.BindingSource> denominado `BindingSource1` y un <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="03a16-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="03a16-121">Controlar la <xref:System.Windows.Forms.Form.Load> eventos para el formulario y llame a `InitializeSortedFilteredBindingSource` en el método de controlador de eventos de carga.</span><span class="sxs-lookup"><span data-stu-id="03a16-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a16-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="03a16-122">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [<span data-ttu-id="03a16-123">Cómo: Instalar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="03a16-123">How to: Install Sample Databases</span></span>](https://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [<span data-ttu-id="03a16-124">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="03a16-124">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
