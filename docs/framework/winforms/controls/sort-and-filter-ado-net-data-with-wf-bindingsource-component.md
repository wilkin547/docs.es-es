---
title: Procedimiento para ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms
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
ms.openlocfilehash: ae331ca9e3fd2aed654659e11434454874eff8fa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960428"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="5597f-102">Procedimiento para ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5597f-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="5597f-103">Puede exponer la funcionalidad de ordenación y filtrado del <xref:System.Windows.Forms.BindingSource> control a través <xref:System.Windows.Forms.BindingSource.Sort%2A> de <xref:System.Windows.Forms.BindingSource.Filter%2A> las propiedades y.</span><span class="sxs-lookup"><span data-stu-id="5597f-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="5597f-104">Puede aplicar una ordenación simple cuando el origen de datos subyacente es <xref:System.ComponentModel.IBindingList>un y puede aplicar el filtrado y la ordenación avanzada cuando el origen de datos <xref:System.ComponentModel.IBindingListView>es un.</span><span class="sxs-lookup"><span data-stu-id="5597f-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="5597f-105">La <xref:System.Windows.Forms.BindingSource.Sort%2A> propiedad requiere la sintaxis estándar de ADO.net: una cadena que representa el nombre de una columna de datos en el origen `ASC` de `DESC` datos seguido de o para indicar si la lista se debe ordenar en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="5597f-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="5597f-106">Puede establecer la ordenación avanzada o la ordenación de varias columnas separando cada columna con un separador de coma.</span><span class="sxs-lookup"><span data-stu-id="5597f-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="5597f-107">La <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedad toma una expresión de cadena.</span><span class="sxs-lookup"><span data-stu-id="5597f-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5597f-108">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5597f-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="5597f-109">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="5597f-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="5597f-110">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="5597f-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="5597f-111">Para filtrar datos con BindingSource</span><span class="sxs-lookup"><span data-stu-id="5597f-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="5597f-112">Establezca la <xref:System.Windows.Forms.BindingSource.Filter%2A> propiedad en la expresión que desee.</span><span class="sxs-lookup"><span data-stu-id="5597f-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="5597f-113">En el ejemplo de código siguiente, la expresión es un nombre de columna seguido por el valor que desea para la columna.</span><span class="sxs-lookup"><span data-stu-id="5597f-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="5597f-114">Para ordenar los datos con BindingSource</span><span class="sxs-lookup"><span data-stu-id="5597f-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="5597f-115">Establezca la <xref:System.Windows.Forms.BindingSource.Sort%2A> propiedad en el nombre de columna que desee seguido de `ASC` o `DESC` para indicar el orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="5597f-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="5597f-116">Separe varias columnas con una coma.</span><span class="sxs-lookup"><span data-stu-id="5597f-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="5597f-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5597f-117">Example</span></span>  
 <span data-ttu-id="5597f-118">En el ejemplo de código siguiente se cargan datos de la tabla Customers de la <xref:System.Windows.Forms.DataGridView> base de datos de ejemplo Northwind en un control y se filtran y se ordenan los datos mostrados.</span><span class="sxs-lookup"><span data-stu-id="5597f-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5597f-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5597f-119">Compiling the Code</span></span>  
 <span data-ttu-id="5597f-120">Para ejecutar este ejemplo, pegue el código en un formulario que contenga <xref:System.Windows.Forms.BindingSource> un `BindingSource1` denominado y <xref:System.Windows.Forms.DataGridView> un `dataGridView1`denominado.</span><span class="sxs-lookup"><span data-stu-id="5597f-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="5597f-121">Controle <xref:System.Windows.Forms.Form.Load> el evento para el formulario y `InitializeSortedFilteredBindingSource` llame a en el método de control de eventos Load.</span><span class="sxs-lookup"><span data-stu-id="5597f-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5597f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5597f-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="5597f-123">[Cómo: Instalar bases de datos de ejemplo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="5597f-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="5597f-124">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="5597f-124">BindingSource Component</span></span>](bindingsource-component.md)
