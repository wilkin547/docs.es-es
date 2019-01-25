---
title: Procedimiento Búsqueda de datos en un Control DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 514e72afc9570071f57e385574456ff7d716bad7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654391"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="68b6b-102">Procedimiento Búsqueda de datos en un Control DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="68b6b-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="68b6b-103">Cuando se usa un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control que contiene el número de registros, desea que los usuarios busquen un registro específico.</span><span class="sxs-lookup"><span data-stu-id="68b6b-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="68b6b-104">En lugar de buscar los datos en el propio control, puede implementar una búsqueda mediante la consulta subyacente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="68b6b-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="68b6b-105">Si se encuentra el elemento, puede usar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> propiedad para seleccionar el elemento y se desplace en la vista.</span><span class="sxs-lookup"><span data-stu-id="68b6b-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="68b6b-106">Para implementar la búsqueda</span><span class="sxs-lookup"><span data-stu-id="68b6b-106">To implement search</span></span>  
  
1.  <span data-ttu-id="68b6b-107">Arrastre un control <xref:System.Windows.Forms.TextBox> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="68b6b-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="68b6b-108">En la ventana Propiedades, cambie la propiedad **Name** a **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="68b6b-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="68b6b-109">Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="68b6b-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="68b6b-110">En la ventana Propiedades, cambie la propiedad **Name** a **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="68b6b-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="68b6b-111">Cambie la propiedad **Text** a **Search**.</span><span class="sxs-lookup"><span data-stu-id="68b6b-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="68b6b-112">Haga doble clic en el control <xref:System.Windows.Forms.Button> para abrir el Editor de código y agregue el código siguiente al controlador de eventos `SearchButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="68b6b-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="68b6b-113">Reemplace *ProductsBindingSource* con el nombre de la <xref:System.Windows.Forms.BindingSource> para su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>y reemplace *ProductID* con el nombre del campo que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="68b6b-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b6b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="68b6b-114">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="68b6b-115">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="68b6b-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="68b6b-116">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="68b6b-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="68b6b-117">Cómo: Cambiar la apariencia de un Control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="68b6b-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
