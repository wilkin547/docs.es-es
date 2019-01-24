---
title: Procedimiento Enlazar objetos a controles DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: 0e69e67201d95b912467ccfd74bc5fb08196f11d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614672"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="d2ee6-102">Procedimiento Enlazar objetos a controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2ee6-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="d2ee6-103">El ejemplo de código siguiente muestra cómo enlazar una colección de objetos a un control <xref:System.Windows.Forms.DataGridView> de modo que cada objeto se muestre como una fila independiente.</span><span class="sxs-lookup"><span data-stu-id="d2ee6-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="d2ee6-104">En este ejemplo también se explica cómo mostrar una propiedad con un tipo de enumeración en <xref:System.Windows.Forms.DataGridViewComboBoxColumn> para que la lista desplegable del cuadro combinado contenga los valores de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="d2ee6-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2ee6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2ee6-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2ee6-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d2ee6-106">Compiling the Code</span></span>  
 <span data-ttu-id="d2ee6-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d2ee6-107">This example requires:</span></span>  
  
-   <span data-ttu-id="d2ee6-108">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d2ee6-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d2ee6-109">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d2ee6-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d2ee6-110">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2ee6-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="d2ee6-111">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="d2ee6-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ee6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2ee6-112">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d2ee6-113">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2ee6-113">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d2ee6-114">Cómo: Obtener acceso a objetos enlazados a Windows Forms filas DataGridView</span><span class="sxs-lookup"><span data-stu-id="d2ee6-114">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
