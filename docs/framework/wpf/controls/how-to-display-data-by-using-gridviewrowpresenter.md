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
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>Cómo: Mostrar datos mediante GridViewRowPresenter
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos para mostrar datos en columnas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar un <xref:System.Windows.Controls.GridViewColumnCollection> que muestra la <xref:System.DateTime.DayOfWeek%2A> y <xref:System.DateTime.Year%2A> de un <xref:System.DateTime> objeto mediante el uso de <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos. El ejemplo también define un <xref:System.Windows.Style> para el <xref:System.Windows.Controls.GridViewColumn.Header%2A> de un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewColumnCollection>  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
