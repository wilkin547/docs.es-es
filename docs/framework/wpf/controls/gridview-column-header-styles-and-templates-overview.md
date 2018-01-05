---
title: "Información general sobre plantillas y estilos de encabezado de columna en modo GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 996d6d5f531a866d4fc80acc3848cdf264901032
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="gridview-column-header-styles-and-templates-overview"></a><span data-ttu-id="54422-102">Información general sobre plantillas y estilos de encabezado de columna en modo GridView</span><span class="sxs-lookup"><span data-stu-id="54422-102">GridView Column Header Styles and Templates Overview</span></span>
<span data-ttu-id="54422-103">Esta información general describe el orden de prioridad para las propiedades que se usan para personalizar un encabezado de columna en la <xref:System.Windows.Controls.GridView> modo de vista de un <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="54422-103">This overview discusses the order of precedence for properties that you use to customize a column header in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="customizing-a-column-header-in-a-gridview"></a><span data-ttu-id="54422-104">Personalizar un encabezado de columna en un control GridView</span><span class="sxs-lookup"><span data-stu-id="54422-104">Customizing a Column Header in a GridView</span></span>  
 <span data-ttu-id="54422-105">Las propiedades que definen el contenido, el diseño y el estilo de un encabezado de columna en un <xref:System.Windows.Controls.GridView> se encuentran en muchas clases relacionadas.</span><span class="sxs-lookup"><span data-stu-id="54422-105">The properties that define the content, layout, and style of a column header in a <xref:System.Windows.Controls.GridView> are found on many related classes.</span></span> <span data-ttu-id="54422-106">Algunas de estas propiedades tienen funcionalidad similar o al mismo.</span><span class="sxs-lookup"><span data-stu-id="54422-106">Some of these properties have functionality that is similar or the same.</span></span>  
  
 <span data-ttu-id="54422-107">Las filas en la tabla siguiente muestran los grupos de propiedades que realizan la misma función.</span><span class="sxs-lookup"><span data-stu-id="54422-107">The rows in the following table show groups of properties that perform the same function.</span></span> <span data-ttu-id="54422-108">Puede utilizar estas propiedades para personalizar los encabezados de columna en un <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="54422-108">You can use these properties to customize the column headers in a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="54422-109">El orden de prioridad de las propiedades relacionadas es de derecha a izquierda donde la propiedad de la columna derecha más lejano tiene la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="54422-109">The order of precedence for related properties is from right to left where the property in the farthest right column has the highest precedence.</span></span> <span data-ttu-id="54422-110">Por ejemplo, si un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> está establecido en el <xref:System.Windows.Controls.GridViewColumnHeader> objeto y el <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> está establecido en el asociado <xref:System.Windows.Controls.GridViewColumn>, el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="54422-110">For example, if a <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> is set on the <xref:System.Windows.Controls.GridViewColumnHeader> object and the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> is set on the associated <xref:System.Windows.Controls.GridViewColumn>, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> takes precedence.</span></span> <span data-ttu-id="54422-111">En este escenario, la <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="54422-111">In this scenario, the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> has no effect.</span></span>  
  
 <span data-ttu-id="54422-112">**Propiedades relacionadas para los encabezados de columna en un control GridView**</span><span class="sxs-lookup"><span data-stu-id="54422-112">**Related properties for column headers in a GridView**</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="54422-113">**Clases**</span><span class="sxs-lookup"><span data-stu-id="54422-113">**Classes**</span></span>|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|<span data-ttu-id="54422-114">**Propiedades del menú contextual**</span><span class="sxs-lookup"><span data-stu-id="54422-114">**Context Menu Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|<span data-ttu-id="54422-115">No es aplicable</span><span class="sxs-lookup"><span data-stu-id="54422-115">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|<span data-ttu-id="54422-116">**ToolTip**</span><span class="sxs-lookup"><span data-stu-id="54422-116">**ToolTip**</span></span><br /><br /> <span data-ttu-id="54422-117">**Propiedades**</span><span class="sxs-lookup"><span data-stu-id="54422-117">**Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|<span data-ttu-id="54422-118">No es aplicable</span><span class="sxs-lookup"><span data-stu-id="54422-118">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|<span data-ttu-id="54422-119">**Plantilla de encabezado**</span><span class="sxs-lookup"><span data-stu-id="54422-119">**Header Template**</span></span><br /><br /> <span data-ttu-id="54422-120">**Propiedades**</span><span class="sxs-lookup"><span data-stu-id="54422-120">**Properties**</span></span>|<span data-ttu-id="54422-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="54422-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<span data-ttu-id="54422-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="54422-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<span data-ttu-id="54422-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="54422-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|<span data-ttu-id="54422-124">**Propiedades de estilo**</span><span class="sxs-lookup"><span data-stu-id="54422-124">**Style Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <span data-ttu-id="54422-125"><sup>1</sup>para **propiedades de la plantilla de encabezado**, si establece la plantilla y propiedades de selector de plantilla, la propiedad de plantilla tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="54422-125"><sup>1</sup>For **Header Template Properties**, if you set both the template and template selector properties, the template property takes precedence.</span></span> <span data-ttu-id="54422-126">Por ejemplo, si establece tanto la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> propiedades, la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="54422-126">For example, if you set both the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> properties, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54422-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="54422-127">See Also</span></span>  
 [<span data-ttu-id="54422-128">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="54422-128">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="54422-129">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="54422-129">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="54422-130">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="54422-130">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
