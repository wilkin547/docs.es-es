---
title: Agrupar elementos en ListView Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141996"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="b3132-102">Cómo: Agrupar elementos en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3132-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="b3132-103">Con la característica <xref:System.Windows.Forms.ListView> de agrupación del control, puede mostrar conjuntos de elementos relacionados en grupos.</span><span class="sxs-lookup"><span data-stu-id="b3132-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="b3132-104">Estos grupos están separados en la pantalla por encabezados de grupo horizontales que contienen los títulos de grupo.</span><span class="sxs-lookup"><span data-stu-id="b3132-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="b3132-105">Puede utilizar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes agrupando elementos alfabéticamente, por fecha o por cualquier otra agrupación lógica.</span><span class="sxs-lookup"><span data-stu-id="b3132-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="b3132-106">La siguiente imagen muestra algunos elementos agrupados.</span><span class="sxs-lookup"><span data-stu-id="b3132-106">The following image shows some grouped items.</span></span>  
  
 ![Captura de pantalla de grupos ListView impares e pares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 <span data-ttu-id="b3132-108">Para habilitar la agrupación, primero debe crear uno o varios grupos en el diseñador o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b3132-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="b3132-109">Una vez definido un grupo, <xref:System.Windows.Forms.ListView> puede asignar artículos a grupos.</span><span class="sxs-lookup"><span data-stu-id="b3132-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="b3132-110">También puede mover elementos de un grupo a otro mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b3132-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="b3132-111">Para añadir grupos</span><span class="sxs-lookup"><span data-stu-id="b3132-111">To add groups</span></span>  
  
1. <span data-ttu-id="b3132-112">Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="b3132-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="b3132-113">Para eliminar grupos</span><span class="sxs-lookup"><span data-stu-id="b3132-113">To remove groups</span></span>  
  
1. <span data-ttu-id="b3132-114">Utilice <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método <xref:System.Windows.Forms.ListView.Groups%2A> o de la colección.</span><span class="sxs-lookup"><span data-stu-id="b3132-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="b3132-115">El <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> método quita un solo grupo; el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método quita todos los grupos de la lista.</span><span class="sxs-lookup"><span data-stu-id="b3132-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b3132-116">La eliminación de un grupo no quita los elementos de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="b3132-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="b3132-117">Para asignar artículos a grupos o mover elementos entre grupos</span><span class="sxs-lookup"><span data-stu-id="b3132-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="b3132-118">Establezca <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> la propiedad de elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="b3132-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="b3132-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3132-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="b3132-120">Control ListView</span><span class="sxs-lookup"><span data-stu-id="b3132-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="b3132-121">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="b3132-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="b3132-122">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3132-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
