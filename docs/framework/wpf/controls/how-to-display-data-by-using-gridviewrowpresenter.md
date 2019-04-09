---
title: Filtrar Mostrar datos mediante GridViewRowPresenter
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149154"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="1fe02-102">Filtrar Mostrar datos mediante GridViewRowPresenter</span><span class="sxs-lookup"><span data-stu-id="1fe02-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="1fe02-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos para mostrar datos en columnas.</span><span class="sxs-lookup"><span data-stu-id="1fe02-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fe02-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1fe02-104">Example</span></span>  
 <span data-ttu-id="1fe02-105">El ejemplo siguiente muestra cómo especificar un <xref:System.Windows.Controls.GridViewColumnCollection> que muestra la <xref:System.DateTime.DayOfWeek%2A> y <xref:System.DateTime.Year%2A> de un <xref:System.DateTime> objeto mediante el uso de <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos.</span><span class="sxs-lookup"><span data-stu-id="1fe02-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="1fe02-106">El ejemplo también define un <xref:System.Windows.Style> para el <xref:System.Windows.Controls.GridViewColumn.Header%2A> de un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="1fe02-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="1fe02-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fe02-107">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [<span data-ttu-id="1fe02-108">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="1fe02-108">GridView Overview</span></span>](gridview-overview.md)
