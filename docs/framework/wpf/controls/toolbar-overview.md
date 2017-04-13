---
title: "Informaci&#243;n general sobre controles ToolBar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles, ToolBar"
  - "ToolBar (control)"
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Informaci&#243;n general sobre controles ToolBar
Los controles <xref:System.Windows.Controls.ToolBar> son contenedores para un grupo de comandos o controles que suelen tener funciones relacionadas.  <xref:System.Windows.Controls.ToolBar> suele contener botones que invocan comandos.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="ToolBarControl"></a>   
## Control ToolBar  
 El control <xref:System.Windows.Controls.ToolBar> toma su nombre del hecho de que los botones u otros controles se organizan en forma de barra, en una sola fila o columna.  Los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar> proporcionan un mecanismo de desbordamiento que coloca en un área de desbordamiento especial todos aquellos elementos que no caben de manera natural en un objeto <xref:System.Windows.Controls.ToolBar>.  Además, los controles <xref:System.Windows.Controls.ToolBar> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se suelen usar con el control <xref:System.Windows.Controls.ToolBarTray> relacionado, que proporciona comportamiento de diseño especial y compatibilidad con el cambio de tamaño y la organización de barras de herramientas por parte del usuario.  
  
<a name="Creating_ToolBars"></a>   
## Especificar la posición de los controles ToolBar en un control ToolBarTray  
 Utilice las propiedades <xref:System.Windows.Controls.ToolBar.Band%2A> y <xref:System.Windows.Controls.ToolBar.BandIndex%2A> para colocar <xref:System.Windows.Controls.ToolBar> en <xref:System.Windows.Controls.ToolBarTray>.  <xref:System.Windows.Controls.ToolBar.Band%2A> indica la posición en la que se coloca <xref:System.Windows.Controls.ToolBar> dentro de su control <xref:System.Windows.Controls.ToolBarTray> primario.  <xref:System.Windows.Controls.ToolBar.BandIndex%2A> indica el orden en el que se coloca <xref:System.Windows.Controls.ToolBar> dentro de su banda.  En el ejemplo siguiente se muestra cómo utilizar esta propiedad para colocar controles <xref:System.Windows.Controls.ToolBar> dentro de <xref:System.Windows.Controls.ToolBarTray>.  
  
 [!code-xml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## Controles ToolBar con elementos de desbordamiento  
 A menudo, los controles <xref:System.Windows.Controls.ToolBar> contienen más elementos de los que caben en el tamaño de la barra de herramientas.  Cuando esto sucede, <xref:System.Windows.Controls.ToolBar> muestra un botón de desbordamiento.  Para ver los elementos de desbordamiento, el usuario hace clic en el botón de desbordamiento y los elementos se muestran en una ventana emergente debajo de <xref:System.Windows.Controls.ToolBar>.  En la ilustración siguiente se muestra un objeto <xref:System.Windows.Controls.ToolBar> con elementos de desbordamiento.  
  
 ![ToolBar con desbordamiento](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
Barra de herramientas con elementos de desbordamiento  
  
 Puede especificar cuándo se coloca un elemento de una barra de herramientas en el panel de desbordamiento estableciendo la propiedad adjunta <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=fullName> en <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName>, <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName> o <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName>.  En el ejemplo siguiente se especifica que los cuatro últimos botones de la barra de herramientas siempre deben estar en el panel de desbordamiento.  
  
 [!code-xml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar> utiliza un objeto <xref:System.Windows.Controls.Primitives.ToolBarPanel> y un objeto <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> en su <xref:System.Windows.Controls.ControlTemplate>.  <xref:System.Windows.Controls.Primitives.ToolBarPanel> es responsable del diseño de los elementos en la barra de herramientas.  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> es responsable del diseño de los elementos que no caben en <xref:System.Windows.Controls.ToolBar>.  Para obtener un ejemplo de <xref:System.Windows.Controls.ControlTemplate> para un objeto <xref:System.Windows.Controls.ToolBar>, consulte  
  
 [Estilos y plantillas de ToolBar](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).  
  
## Vea también  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>   
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>   
 [Aplicar estilo a controles en un elemento toolbar](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)   
 [Ejemplo WPF Controls Gallery](http://go.microsoft.com/fwlink/?LinkID=160053)