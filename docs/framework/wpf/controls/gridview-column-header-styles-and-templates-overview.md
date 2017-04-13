---
title: "Informaci&#243;n general sobre plantillas y estilos de encabezado de columna en modo GridView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "encabezados de columna, personalizar"
  - "controles, ListView"
  - "modo de vista para GridView, personalizar encabezados de columna"
  - "encabezados, personalizar"
  - "ListView (controles) [WPF], estilos de encabezado de columna de GridView"
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre plantillas y estilos de encabezado de columna en modo GridView
En este tema se analiza el orden de prioridad de las propiedades que se usan para personalizar un encabezado de columna en el modo de vista <xref:System.Windows.Controls.GridView> de un control <xref:System.Windows.Controls.ListView>.  
  
## Personalización de un encabezado de columna en modo GridView  
 Las propiedades que definen el contenido, diseño y estilo de un encabezado de columna en <xref:System.Windows.Controls.GridView> se encuentran en muchas clases relacionadas.  Algunas de estas propiedades tienen la misma funcionalidad o una funcionalidad similar.  
  
 Las filas de la tabla siguiente muestran grupos de propiedades que realizan la misma función.  Puede usar estas propiedades para personalizar los encabezados de columna en <xref:System.Windows.Controls.GridView>.  El orden de prioridad de las propiedades relacionadas es de derecha a izquierda; la propiedad de la última columna de la derecha es la que tiene mayor prioridad.  Por ejemplo, si <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> se establece en el objeto <xref:System.Windows.Controls.GridViewColumnHeader> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> se establece en el objeto <xref:System.Windows.Controls.GridViewColumn>asociado, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> tiene prioridad.  En este escenario, <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> no tiene ningún efecto.  
  
 **Propiedades relacionadas para los encabezados de columna en GridView**  
  
|||||  
|-|-|-|-|  
|**Clases**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Propiedades de menú contextual**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|No es aplicable|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **Propiedades**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|No es aplicable|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Plantilla de encabezado**<br /><br /> **Propiedades**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Propiedades de estilo**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>En el caso de **Propiedades de plantilla de encabezado**, si establece las propiedades de plantilla y de selector de plantilla, la propiedad de plantilla tendrá prioridad.  Por ejemplo, si establece las propiedades <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>, tendrá prioridad la propiedad <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.  
  
## Vea también  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)