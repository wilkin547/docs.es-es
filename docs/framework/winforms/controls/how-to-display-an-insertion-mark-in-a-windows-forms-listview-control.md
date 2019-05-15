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
ms.openlocfilehash: f3dff351052eaaf70737c6410c1367ab568f6fd0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586517"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="e418d-102">Procedimiento para mostrar una marca de inserción en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e418d-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="e418d-103">La marca de inserción del control <xref:System.Windows.Forms.ListView> muestra a los usuarios el punto en el que se insertarán los elementos arrastrados.</span><span class="sxs-lookup"><span data-stu-id="e418d-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="e418d-104">Cuando un usuario arrastra un elemento a un punto entre otros dos elementos, la marca de inserción muestra la nueva ubicación esperada del elemento.</span><span class="sxs-lookup"><span data-stu-id="e418d-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e418d-105">La característica de marca de inserción solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e418d-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e418d-106">En sistemas operativos anteriores, cualquier código relacionado con la marca de inserción no tiene ningún efecto y la marca de inserción no aparecerá.</span><span class="sxs-lookup"><span data-stu-id="e418d-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="e418d-107">Para obtener más información, consulta <xref:System.Windows.Forms.ListViewInsertionMark>.</span><span class="sxs-lookup"><span data-stu-id="e418d-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="e418d-108">La siguiente imagen muestra una marca de inserción:</span><span class="sxs-lookup"><span data-stu-id="e418d-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="e418d-109">![Captura de pantalla que muestra una marca de inserción de ListView. ](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="e418d-109">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="e418d-110">El ejemplo de código siguiente muestra cómo utilizar esta característica.</span><span class="sxs-lookup"><span data-stu-id="e418d-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e418d-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e418d-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e418d-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e418d-112">Compiling the Code</span></span>  
 <span data-ttu-id="e418d-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e418d-113">This example requires:</span></span>  
  
- <span data-ttu-id="e418d-114">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e418d-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e418d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e418d-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="e418d-116">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="e418d-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="e418d-117">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="e418d-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="e418d-118">Tutorial: Realizar una operación de arrastrar y colocar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e418d-118">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
