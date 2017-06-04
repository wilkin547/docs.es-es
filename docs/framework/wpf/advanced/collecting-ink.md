---
title: "Recopilaci&#243;n de entradas manuscritas | Microsoft Docs"
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
  - "recopilación de entrada manuscrita"
  - "DefaultDrawingAttributes (propiedad)"
  - "entrada manuscrita digital, recopilar"
  - "DrawingAttributes (propiedad)"
  - "entrada manuscrita, recopilar"
  - "InkCanvas (elemento)"
  - "propiedades, DefaultDrawingAttributes"
  - "propiedades, DrawingAttributes"
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Recopilaci&#243;n de entradas manuscritas
La plataforma [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) recopila las entradas de lápiz digitales como parte básica de su funcionalidad.  En este tema se tratan los métodos para la recopilación de entradas de lápiz en [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
## Requisitos previos  
 Para utilizar los ejemplos siguientes, debe instalar primero [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] y [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].  También debe comprender la escritura de aplicaciones para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información acerca de cómo empezar con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Utilizar el elemento InkCanvas  
 El elemento <xref:System.Windows.Controls.InkCanvas> proporciona la manera más fácil de recopilar entradas de lápiz en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El elemento <xref:System.Windows.Controls.InkCanvas> es similar al objeto <xref:Microsoft.Ink.InkOverlay> de [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] y de versiones anteriores.  
  
 Utilice un elemento <xref:System.Windows.Controls.InkCanvas> para recibir y mostrar la entrada de entradas de lápiz.  Normalmente, la entrada de entradas de lápiz se efectúa mediante un lápiz óptico, que interactúa con un digitalizador para generar los trazos de las entradas de lápiz.  También puede utilizarse un mouse en lugar de un lápiz óptico.  Los trazos creados se representan como objetos <xref:System.Windows.Ink.Stroke> y se pueden manipular, tanto mediante programación como por acciones del usuario.  <xref:System.Windows.Controls.InkCanvas> permite al usuario seleccionar, modificar o eliminar un objeto <xref:System.Windows.Ink.Stroke> existente.  
  
 XAML puede utilizarse para configurar la recopilación de entradas de lápiz con la misma facilidad que se agrega un elemento `InkCanvas` al árbol.  En el ejemplo siguiente se agrega un elemento <xref:System.Windows.Controls.InkCanvas> a un proyecto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminado creado en [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
 [!code-xml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 El elemento `InkCanvas` también puede contener elementos secundarios que permiten agregar funciones de entrada de lápiz a casi todos los tipos de elementos XAML.  Por ejemplo, para agregar funciones de escritura a mano a un elemento de texto, basta con convertirlo en un elemento secundario de <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 Agregar compatibilidad para marcar una imagen con una entrada de lápiz resulta igual de sencillo.  
  
 [!code-xml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### Modos de InkCollection  
 <xref:System.Windows.Controls.InkCanvas> proporciona compatibilidad con varios modos de entrada mediante su propiedad <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.  
  
### Manipular las entradas de lápiz  
 <xref:System.Windows.Controls.InkCanvas> admite numerosas operaciones de edición de entradas de lápiz.  Por ejemplo, <xref:System.Windows.Controls.InkCanvas> admite el borrado inmediato sin que se requiera ningún código adicional para agregar la funcionalidad al elemento.  
  
#### Selection  
 Configurar el modo de selección es tan sencillo como establecer la propiedad <xref:System.Windows.Controls.InkCanvasEditingMode> en **Select**.  El código siguiente configura el modo de edición según el valor de <xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### DrawingAttributes  
 Utilice la propiedad <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> para cambiar la apariencia de los trazos de las entradas de lápiz.  Por ejemplo, el miembro <xref:System.Windows.Ink.DrawingAttributes.Color%2A> de <xref:System.Windows.Ink.DrawingAttributes> establece el color de <xref:System.Windows.Ink.Stroke> representado.  En el ejemplo siguiente se cambia el color de los trazos seleccionados a rojo.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### DefaultDrawingAttributes  
 La propiedad <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proporciona acceso a propiedades tales como el alto, ancho y color de los trazos que se van a crear en un elemento <xref:System.Windows.Controls.InkCanvas>.  Cuando se cambia <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, todos los trazos futuros que se escriben en <xref:System.Windows.Controls.InkCanvas> se representan con los nuevos valores de propiedad.  
  
 Además de modificar la propiedad <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> en el archivo de código subyacente, puede utilizar la sintaxis XAML para especificar las propiedades <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>.  En el ejemplo de código XAML siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Ink.DrawingAttributes.Color%2A>.  Para usar este código, cree un nuevo proyecto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamado "HelloInkCanvas" en Visual Studio 2005.  Reemplace el código del archivo Window1.xaml con el código siguiente.  
  
 [!code-xml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 A continuación, agregue los controladores de eventos de botón siguientes al archivo de código subyacente, dentro de la clase Window1.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 Después de copiar el código, presione **F5** en Microsoft Visual Studio 2005 para ejecutar el programa en el depurador.  
  
 Observe cómo <xref:System.Windows.Controls.StackPanel> coloca los botones encima de <xref:System.Windows.Controls.InkCanvas>.  Si intenta realizar entradas de lápiz sobre la parte superior de los botones, <xref:System.Windows.Controls.InkCanvas> las recolecciona y representa detrás de los botones.  Esto se debe a que los botones están en el mismo nivel que <xref:System.Windows.Controls.InkCanvas>, no son elementos secundarios.  Además, los botones ocupan niveles superiores en el orden z, por lo que la entrada de lápiz se representa detrás de ellos.  
  
## Vea también  
 <xref:System.Windows.Ink.DrawingAttributes>   
 <xref:System.Windows.InkCanvas.DefaultDrawingAttributes%2A>   
 <xref:System.Windows.Ink>