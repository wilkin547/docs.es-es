---
title: "Cómo: Agrupar elementos en un control ListView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b12b7126e03f6a6c8363c69a607f4961f13120ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="48a99-102">Cómo: Agrupar elementos en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48a99-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="48a99-103">Con la característica de agrupación de la <xref:System.Windows.Forms.ListView> (control), puede mostrar conjuntos de elementos relacionados en grupos.</span><span class="sxs-lookup"><span data-stu-id="48a99-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="48a99-104">Estos grupos se separan en la pantalla por encabezados de grupo horizontales que contienen los títulos de grupo.</span><span class="sxs-lookup"><span data-stu-id="48a99-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="48a99-105">Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación sea más fácil de listas grandes mediante la agrupación de elementos por orden alfabético, por fecha, o por cualquier otra agrupación lógica.</span><span class="sxs-lookup"><span data-stu-id="48a99-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="48a99-106">La siguiente imagen muestra algunos elementos agrupados.</span><span class="sxs-lookup"><span data-stu-id="48a99-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="48a99-107">![Grupos ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="48a99-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
<span data-ttu-id="48a99-108">Elementos agrupados ListView</span><span class="sxs-lookup"><span data-stu-id="48a99-108">ListView grouped items</span></span>  
  
 <span data-ttu-id="48a99-109">Para habilitar la agrupación, debe crear primero uno o varios grupos en el diseñador o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="48a99-109">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="48a99-110">Una vez definido un grupo, puede asignar <xref:System.Windows.Forms.ListView> elementos a grupos.</span><span class="sxs-lookup"><span data-stu-id="48a99-110">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="48a99-111">También puede mover elementos de un grupo a otro mediante programación.</span><span class="sxs-lookup"><span data-stu-id="48a99-111">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48a99-112"><xref:System.Windows.Forms.ListView>grupos solo están disponibles en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama el <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="48a99-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="48a99-113">En sistemas operativos anteriores, cualquier código relacionado con grupos no tiene ningún efecto y los grupos no aparecerán.</span><span class="sxs-lookup"><span data-stu-id="48a99-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="48a99-114">Para obtener más información, consulta <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="48a99-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="48a99-115">Para agregar grupos</span><span class="sxs-lookup"><span data-stu-id="48a99-115">To add groups</span></span>  
  
1.  <span data-ttu-id="48a99-116">Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A>.</span><span class="sxs-lookup"><span data-stu-id="48a99-116">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="48a99-117">Para quitar grupos</span><span class="sxs-lookup"><span data-stu-id="48a99-117">To remove groups</span></span>  
  
1.  <span data-ttu-id="48a99-118">Use la <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método de la <xref:System.Windows.Forms.ListView.Groups%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="48a99-118">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="48a99-119">El <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> método quita un grupo único; el <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> método quita todos los grupos de la lista.</span><span class="sxs-lookup"><span data-stu-id="48a99-119">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48a99-120">Quitar un grupo no quita los elementos dentro de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="48a99-120">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="48a99-121">Para asignar elementos a grupos o mover elementos entre grupos</span><span class="sxs-lookup"><span data-stu-id="48a99-121">To assign items to groups or move items between groups</span></span>  
  
1.  <span data-ttu-id="48a99-122">Establecer el <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> propiedad de los elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="48a99-122">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="48a99-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="48a99-123">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [<span data-ttu-id="48a99-124">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="48a99-124">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="48a99-125">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="48a99-125">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="48a99-126">Características de Windows XP y controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48a99-126">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="48a99-127">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48a99-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
