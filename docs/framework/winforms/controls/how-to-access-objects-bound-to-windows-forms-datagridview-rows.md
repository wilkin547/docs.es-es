---
title: Filtrar para obtener acceso a objetos enlazados a filas DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 50882ab9a1a498bf8f76381e3f4aac53876abbb8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217411"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="8c7a2-102">Filtrar para obtener acceso a objetos enlazados a filas DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c7a2-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="8c7a2-103">A veces resulta útil mostrar una tabla de información almacenada en una colección de objetos comerciales.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="8c7a2-104">Al enlazar un control <xref:System.Windows.Forms.DataGridView> a este tipo de colección, cada propiedad pública se muestra en su propia columna a menos que la propiedad se haya marcado como no examinable con un <xref:System.ComponentModel.BrowsableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="8c7a2-105">Por ejemplo, una colección de objetos `Customer` tendría columnas como **Nombre** y **Dirección**.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="8c7a2-106">Si estos objetos contienen información adicional y código al que quiere acceder, puede llegar a él a través de los objetos de fila.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="8c7a2-107">En el siguiente ejemplo de código, los usuarios pueden seleccionar varias filas y hacer clic en un botón para enviar una factura a cada uno de los clientes correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="8c7a2-108">Para acceder a objetos enlazados a fila</span><span class="sxs-lookup"><span data-stu-id="8c7a2-108">To access row-bound objects</span></span>  
  
-   <span data-ttu-id="8c7a2-109">Utilice la propiedad <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="8c7a2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c7a2-110">Example</span></span>  
 <span data-ttu-id="8c7a2-111">El ejemplo de código completo incluye una implementación sencilla `Customer` y enlaza la <xref:System.Windows.Forms.DataGridView> a una <xref:System.Collections.ArrayList> que contiene algunos objetos `Customer`.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="8c7a2-112">El controlador de eventos <xref:System.Windows.Forms.Control.Click> del <xref:System.Windows.Forms.Button?displayProperty=nameWithType> debe acceder a los objetos `Customer` a través de las filas porque la colección del cliente no es accesible fuera del controlador de eventos <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c7a2-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8c7a2-113">Compiling the Code</span></span>  
 <span data-ttu-id="8c7a2-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8c7a2-114">This example requires:</span></span>  
  
-   <span data-ttu-id="8c7a2-115">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8c7a2-116">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8c7a2-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8c7a2-117">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c7a2-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7a2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c7a2-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8c7a2-119">Mostrar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c7a2-119">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8c7a2-120">Filtrar para enlazar objetos a controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c7a2-120">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)
