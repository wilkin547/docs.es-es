---
title: Ordenar y filtrar datos ADO.NET con el componente BindingSource
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
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742978"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="56cfa-102">Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56cfa-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="56cfa-103">Puede exponer la funcionalidad de ordenación y filtrado de <xref:System.Windows.Forms.BindingSource> control a través de las propiedades <xref:System.Windows.Forms.BindingSource.Sort%2A> y <xref:System.Windows.Forms.BindingSource.Filter%2A>.</span><span class="sxs-lookup"><span data-stu-id="56cfa-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="56cfa-104">Puede aplicar una ordenación simple cuando el origen de datos subyacente es un <xref:System.ComponentModel.IBindingList>y puede aplicar filtrado y ordenación avanzada cuando el origen de datos es un <xref:System.ComponentModel.IBindingListView>.</span><span class="sxs-lookup"><span data-stu-id="56cfa-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="56cfa-105">La propiedad <xref:System.Windows.Forms.BindingSource.Sort%2A> requiere la sintaxis estándar de ADO.NET: una cadena que representa el nombre de una columna de datos en el origen de datos seguida de `ASC` o `DESC` para indicar si la lista debe ordenarse en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="56cfa-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="56cfa-106">Puede establecer la ordenación avanzada o la ordenación de varias columnas separando cada columna con un separador de coma.</span><span class="sxs-lookup"><span data-stu-id="56cfa-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="56cfa-107">La propiedad <xref:System.Windows.Forms.BindingSource.Filter%2A> toma una expresión de cadena.</span><span class="sxs-lookup"><span data-stu-id="56cfa-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56cfa-108">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="56cfa-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="56cfa-109">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="56cfa-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="56cfa-110">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="56cfa-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="56cfa-111">Para filtrar datos con BindingSource</span><span class="sxs-lookup"><span data-stu-id="56cfa-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="56cfa-112">Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Filter%2A> en la expresión que desee.</span><span class="sxs-lookup"><span data-stu-id="56cfa-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="56cfa-113">En el ejemplo de código siguiente, la expresión es un nombre de columna seguido por el valor que desea para la columna.</span><span class="sxs-lookup"><span data-stu-id="56cfa-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="56cfa-114">Para ordenar los datos con BindingSource</span><span class="sxs-lookup"><span data-stu-id="56cfa-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="56cfa-115">Establezca la propiedad <xref:System.Windows.Forms.BindingSource.Sort%2A> en el nombre de columna que desee seguido de `ASC` o `DESC` para indicar el orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="56cfa-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="56cfa-116">Separe varias columnas con una coma.</span><span class="sxs-lookup"><span data-stu-id="56cfa-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="56cfa-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56cfa-117">Example</span></span>  
 <span data-ttu-id="56cfa-118">En el ejemplo de código siguiente se cargan datos de la tabla Customers de la base de datos de ejemplo Northwind en un control <xref:System.Windows.Forms.DataGridView>, y se filtran y se ordenan los datos mostrados.</span><span class="sxs-lookup"><span data-stu-id="56cfa-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56cfa-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="56cfa-119">Compiling the Code</span></span>  
 <span data-ttu-id="56cfa-120">Para ejecutar este ejemplo, pegue el código en un formulario que contenga una <xref:System.Windows.Forms.BindingSource> denominada `BindingSource1` y una <xref:System.Windows.Forms.DataGridView> denominada `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="56cfa-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="56cfa-121">Controle el evento <xref:System.Windows.Forms.Form.Load> del formulario y llame a `InitializeSortedFilteredBindingSource` en el método de control de eventos Load.</span><span class="sxs-lookup"><span data-stu-id="56cfa-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cfa-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56cfa-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="56cfa-123">[Cómo: Instalar bases de datos de ejemplo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="56cfa-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="56cfa-124">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="56cfa-124">BindingSource Component</span></span>](bindingsource-component.md)
