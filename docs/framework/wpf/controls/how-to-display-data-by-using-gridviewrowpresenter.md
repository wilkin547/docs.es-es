---
title: "Cómo: Mostrar datos mediante GridViewRowPresenter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f540ad92c69219a2c22763403ce4ecc734c8e5cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="d98f5-102">Cómo: Mostrar datos mediante GridViewRowPresenter</span><span class="sxs-lookup"><span data-stu-id="d98f5-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="d98f5-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos para mostrar datos en columnas.</span><span class="sxs-lookup"><span data-stu-id="d98f5-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d98f5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d98f5-104">Example</span></span>  
 <span data-ttu-id="d98f5-105">En el ejemplo siguiente se muestra cómo especificar un <xref:System.Windows.Controls.GridViewColumnCollection> que muestra la <xref:System.DateTime.DayOfWeek%2A> y <xref:System.DateTime.Year%2A> de un <xref:System.DateTime> objeto mediante el uso de <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos.</span><span class="sxs-lookup"><span data-stu-id="d98f5-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="d98f5-106">El ejemplo también define un <xref:System.Windows.Style> para el <xref:System.Windows.Controls.GridViewColumn.Header%2A> de un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="d98f5-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="d98f5-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="d98f5-107">See Also</span></span>  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewColumnCollection>  
 [<span data-ttu-id="d98f5-108">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="d98f5-108">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
