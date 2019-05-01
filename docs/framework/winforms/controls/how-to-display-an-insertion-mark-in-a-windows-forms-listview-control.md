---
title: Procedimiento para mostrar una marca de inserción en un control ListView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: 60b775408f5c43ff08fc5c7de72a8302b20b2264
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969725"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="930bd-102">Procedimiento para mostrar una marca de inserción en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="930bd-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="930bd-103">La marca de inserción del control <xref:System.Windows.Forms.ListView> muestra a los usuarios el punto en el que se insertarán los elementos arrastrados.</span><span class="sxs-lookup"><span data-stu-id="930bd-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="930bd-104">Cuando un usuario arrastra un elemento a un punto entre otros dos elementos, la marca de inserción muestra la nueva ubicación esperada del elemento.</span><span class="sxs-lookup"><span data-stu-id="930bd-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="930bd-105">La característica de marca de inserción solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="930bd-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="930bd-106">En sistemas operativos anteriores, cualquier código relacionado con la marca de inserción no tiene ningún efecto y la marca de inserción no aparecerá.</span><span class="sxs-lookup"><span data-stu-id="930bd-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="930bd-107">Para obtener más información, consulta <xref:System.Windows.Forms.ListViewInsertionMark>.</span><span class="sxs-lookup"><span data-stu-id="930bd-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="930bd-108">La siguiente imagen muestra una marca de inserción:</span><span class="sxs-lookup"><span data-stu-id="930bd-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="930bd-109">![Captura de pantalla que muestra una marca de inserción de ListView. ](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="930bd-109">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="930bd-110">El ejemplo de código siguiente muestra cómo utilizar esta característica.</span><span class="sxs-lookup"><span data-stu-id="930bd-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="930bd-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="930bd-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="930bd-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="930bd-112">Compiling the Code</span></span>  
 <span data-ttu-id="930bd-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="930bd-113">This example requires:</span></span>  
  
- <span data-ttu-id="930bd-114">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="930bd-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="930bd-115">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="930bd-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="930bd-116">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="930bd-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930bd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="930bd-117">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="930bd-118">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="930bd-118">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="930bd-119">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="930bd-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="930bd-120">Tutorial: Realizar una operación de arrastrar y colocar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="930bd-120">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
