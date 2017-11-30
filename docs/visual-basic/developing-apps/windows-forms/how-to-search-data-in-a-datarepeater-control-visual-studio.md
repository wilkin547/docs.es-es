---
title: "Cómo: Buscar datos en un control DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3ed7138c142a83584ecd19ccaebe0e31e421ce3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="a1471-102">Cómo: Buscar datos en un control DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="a1471-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="a1471-103">Cuando se usa un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control que contiene el número de registros, puede que desee que los usuarios busquen un registro específico.</span><span class="sxs-lookup"><span data-stu-id="a1471-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="a1471-104">En lugar de buscar los datos en el propio control, puede implementar una búsqueda consultando subyacente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="a1471-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="a1471-105">Si se encuentra el elemento, a continuación, puede usar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> propiedad para seleccionar el elemento y desplazar en la vista.</span><span class="sxs-lookup"><span data-stu-id="a1471-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="a1471-106">Para implementar la búsqueda</span><span class="sxs-lookup"><span data-stu-id="a1471-106">To implement search</span></span>  
  
1.  <span data-ttu-id="a1471-107">Arrastre un control <xref:System.Windows.Forms.TextBox> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a1471-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="a1471-108">En la ventana Propiedades, cambie la propiedad **Name** a **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="a1471-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="a1471-109">Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a1471-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="a1471-110">En la ventana Propiedades, cambie la propiedad **Name** a **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="a1471-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="a1471-111">Cambie la propiedad **Text** a **Search**.</span><span class="sxs-lookup"><span data-stu-id="a1471-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="a1471-112">Haga doble clic en el control <xref:System.Windows.Forms.Button> para abrir el Editor de código y agregue el código siguiente al controlador de eventos `SearchButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="a1471-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="a1471-113">Reemplace *ProductsBindingSource* con el nombre de la <xref:System.Windows.Forms.BindingSource> para su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>y reemplace *ProductID* con el nombre del campo que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a1471-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1471-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1471-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="a1471-115">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a1471-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a1471-116">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a1471-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a1471-117">Cambiar la apariencia de un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a1471-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
