---
title: 'Cómo: Agrupar elementos en un control ListView de Windows Forms'
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
ms.openlocfilehash: 1b716498ec5a45fbde499a1f53b2bdccd28a7176
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960165"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="0833d-102">Cómo: Agrupar elementos en un control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0833d-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="0833d-103">Con la característica de agrupación del control <xref:System.Windows.Forms.ListView>, puede mostrar conjuntos de elementos relacionados en grupos.</span><span class="sxs-lookup"><span data-stu-id="0833d-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="0833d-104">Estos grupos se separan en la pantalla por los encabezados de grupo horizontal que contienen los títulos de grupo.</span><span class="sxs-lookup"><span data-stu-id="0833d-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="0833d-105">Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes mediante la agrupación alfabética de elementos, por fecha o cualquier otra agrupación lógica.</span><span class="sxs-lookup"><span data-stu-id="0833d-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="0833d-106">En la imagen siguiente se muestran algunos elementos agrupados.</span><span class="sxs-lookup"><span data-stu-id="0833d-106">The following image shows some grouped items.</span></span>  
  
 ![Captura de pantalla de grupos de ListView pares e impares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="0833d-108">Para habilitar la agrupación, primero debe crear uno o más grupos en el diseñador o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0833d-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="0833d-109">Una vez definido un grupo, puede asignar elementos de <xref:System.Windows.Forms.ListView> a grupos.</span><span class="sxs-lookup"><span data-stu-id="0833d-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="0833d-110">También puede trasladar elementos de un grupo a otro mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0833d-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="0833d-111">Para agregar grupos</span><span class="sxs-lookup"><span data-stu-id="0833d-111">To add groups</span></span>  
  
1. <span data-ttu-id="0833d-112">Use el método <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> de la colección <xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="0833d-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="0833d-113">Para quitar grupos</span><span class="sxs-lookup"><span data-stu-id="0833d-113">To remove groups</span></span>  
  
1. <span data-ttu-id="0833d-114">Use el método <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> de la colección de <xref:System.Windows.Forms.ListView.Groups%2A>.</span><span class="sxs-lookup"><span data-stu-id="0833d-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="0833d-115">El método <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> quita un solo grupo; el método <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> quita todos los grupos de la lista.</span><span class="sxs-lookup"><span data-stu-id="0833d-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0833d-116">Al quitar un grupo no se quitan los elementos de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="0833d-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="0833d-117">Para asignar elementos a grupos o para trasladar elementos entre grupos</span><span class="sxs-lookup"><span data-stu-id="0833d-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="0833d-118">Establezca la propiedad <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> de elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="0833d-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="0833d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0833d-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="0833d-120">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="0833d-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="0833d-121">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="0833d-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="0833d-122">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0833d-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
