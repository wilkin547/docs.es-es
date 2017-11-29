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
ms.openlocfilehash: ad0f7cacc8256e060bb12611bd1818b694e1e6dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>Información general sobre plantillas y estilos de encabezado de columna en modo GridView
Esta información general describe el orden de prioridad para las propiedades que se usan para personalizar un encabezado de columna en la <xref:System.Windows.Controls.GridView> modo de vista de un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>Personalizar un encabezado de columna en un control GridView  
 Las propiedades que definen el contenido, el diseño y el estilo de un encabezado de columna en un <xref:System.Windows.Controls.GridView> se encuentran en muchas clases relacionadas. Algunas de estas propiedades tienen funcionalidad similar o al mismo.  
  
 Las filas en la tabla siguiente muestran los grupos de propiedades que realizan la misma función. Puede utilizar estas propiedades para personalizar los encabezados de columna en un <xref:System.Windows.Controls.GridView>. El orden de prioridad de las propiedades relacionadas es de derecha a izquierda donde la propiedad de la columna derecha más lejano tiene la prioridad más alta. Por ejemplo, si un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> está establecido en el <xref:System.Windows.Controls.GridViewColumnHeader> objeto y el <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> está establecido en el asociado <xref:System.Windows.Controls.GridViewColumn>, el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> tiene prioridad. En este escenario, la <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> no tiene ningún efecto.  
  
 **Propiedades relacionadas para los encabezados de columna en un control GridView**  
  
|||||  
|-|-|-|-|  
|**Clases**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Propiedades del menú contextual**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|No es aplicable|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **Propiedades**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|No es aplicable|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Plantilla de encabezado**<br /><br /> **Propiedades**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Propiedades de estilo**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>para **propiedades de la plantilla de encabezado**, si establece la plantilla y propiedades de selector de plantilla, la propiedad de plantilla tiene prioridad. Por ejemplo, si establece tanto la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> propiedades, la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad tiene prioridad.  
  
## <a name="see-also"></a>Vea también  
 [Temas de procedimientos](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
