---
title: Información general sobre plantillas y estilos de encabezado de columna en modo GridView
ms.date: 03/30/2017
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
ms.openlocfilehash: 83643d8acea706bad439683702e4228d240b97bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090327"
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>Información general sobre plantillas y estilos de encabezado de columna en modo GridView
Esta introducción describe el orden de prioridad para las propiedades que usa para personalizar un encabezado de columna en la <xref:System.Windows.Controls.GridView> modo de vista de un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>Personalización de un encabezado de columna en un control GridView  
 Las propiedades que definen el contenido, diseño y estilo de un encabezado de columna en un <xref:System.Windows.Controls.GridView> se encuentran en muchas clases relacionadas. Algunas de estas propiedades tienen funcionalidad similar o al mismo.  
  
 Las filas en la tabla siguiente muestran grupos de propiedades que realizan la misma función. Puede usar estas propiedades para personalizar los encabezados de columna en un <xref:System.Windows.Controls.GridView>. El orden de prioridad para las propiedades relacionadas es de derecha a izquierda, donde la propiedad en la columna derecha más lejana tiene la prioridad más alta. Por ejemplo, si un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> se establece en el <xref:System.Windows.Controls.GridViewColumnHeader> objeto y el <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> está establecido en el asociado <xref:System.Windows.Controls.GridViewColumn>, el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> tiene prioridad. En este escenario, la <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> no tiene ningún efecto.  
  
 **Propiedades relacionadas para los encabezados de columna en un control GridView**  
  
|||||  
|-|-|-|-|  
|**Clases**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Propiedades del menú contextual**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|No es aplicable|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**Información sobre herramientas**<br /><br /> **Propiedades**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|No es aplicable|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Plantilla de encabezado**<br /><br /> **Propiedades**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Propiedades de estilo**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>para **propiedades de la plantilla de encabezado**, si se establece la plantilla y las propiedades del selector de plantilla, la propiedad de plantilla tiene prioridad. Por ejemplo, si establece tanto la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> propiedades, la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> propiedad tiene prioridad.  
  
## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](listview-how-to-topics.md)
- [Información general sobre ListView](listview-overview.md)
- [Información general sobre GridView](gridview-overview.md)
