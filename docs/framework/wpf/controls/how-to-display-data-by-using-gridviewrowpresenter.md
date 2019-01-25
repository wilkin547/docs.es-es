---
title: Procedimiento Mostrar datos mediante GridViewRowPresenter
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: b60fe0e78883b166688377c42113a093c78d7751
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607964"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>Procedimiento Mostrar datos mediante GridViewRowPresenter
En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos para mostrar datos en columnas.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo especificar un <xref:System.Windows.Controls.GridViewColumnCollection> que muestra la <xref:System.DateTime.DayOfWeek%2A> y <xref:System.DateTime.Year%2A> de un <xref:System.DateTime> objeto mediante el uso de <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objetos. El ejemplo también define un <xref:System.Windows.Style> para el <xref:System.Windows.Controls.GridViewColumn.Header%2A> de un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
