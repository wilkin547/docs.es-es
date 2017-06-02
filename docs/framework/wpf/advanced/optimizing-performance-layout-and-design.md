---
title: "Optimizar el rendimiento: Presentaci&#243;n y dise&#241;o | Microsoft Docs"
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
  - "consideraciones de diseño"
  - "pase de diseño"
  - "diseño, optimizar el rendimiento"
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Optimizar el rendimiento: Presentaci&#243;n y dise&#241;o
El diseño de la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede afectar a su rendimiento creando sobrecarga innecesaria para calcular el diseño y validar referencias de objeto.  La construcción de objetos, particularmente en tiempo de ejecución, puede afectar a las características de rendimiento de la aplicación.  
  
 En este tema se proporcionan recomendaciones de rendimiento en estas áreas.  
  
## Diseño  
 El término "paso de diseño" describe el proceso de medir y organizar los miembros de una colección de secundarios del objeto derivado <xref:System.Windows.Controls.Panel> y, a continuación, dibujarlos en la pantalla.  El paso de diseño es un proceso matemáticamente intensivo: cuanto mayor sea el número de elementos secundarios de la colección, mayor será el número de cálculos requeridos.  Por ejemplo, cada vez que un objeto <xref:System.Windows.UIElement> secundario de la colección cambia de posición, puede activar un nuevo paso por el sistema de diseño.  Debido a la estrecha relación entre las características de objeto y el comportamiento de diseño, es importante entender el tipo de eventos que puede invocar el sistema de diseño.  La aplicación rendirá mejor reduciendo tanto como sea posible cualquier invocación innecesaria del paso de diseño.  
  
 El sistema de diseño completa dos pasos por cada miembro secundario de una colección: un paso de medida y paso de organización.  Cada objeto secundario proporciona su propia implementación reemplazada de los métodos <xref:System.Windows.UIElement.Measure%2A> y <xref:System.Windows.UIElement.Arrange%2A> para proporcionar su propio comportamiento de diseño concreto.  En su versión más simple, el diseño es un sistema recursivo que conduce a la configuración del tamaño, posición y representación de un elemento en la pantalla.  
  
-   Un objeto <xref:System.Windows.UIElement> secundario comienza el proceso de diseño con la medición de sus propiedades básicas.  
  
-   Se evalúan las propiedades del objeto <xref:System.Windows.FrameworkElement> relacionadas con el tamaño, tales como <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
-   Se aplica la lógica concreta de <xref:System.Windows.Controls.Panel>, tal como la propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A> de <xref:System.Windows.Controls.DockPanel> o la propiedad <xref:System.Windows.Controls.StackPanel.Orientation%2A> de <xref:System.Windows.Controls.StackPanel>.  
  
-   El contenido se organiza o se coloca una vez medidos todos los objetos secundarios.  
  
-   La colección de objetos secundarios se dibuja en la pantalla.  
  
 Se invoca de nuevo el proceso de paso de diseño si se produce cualquiera de las acciones siguientes:  
  
-   Se agrega un objeto secundario a la colección.  
  
-   Se aplica un objeto <xref:System.Windows.FrameworkElement.LayoutTransform%2A> al objeto secundario.  
  
-   Se llama al método <xref:System.Windows.UIElement.UpdateLayout%2A> para el objeto secundario.  
  
-   Cuando se produce un cambio en el valor de una [propiedad de dependencia](GTMT) marcada con metadatos que afectan a la medida o a los pasos de organización.  
  
### Utilizar el panel más eficaz cuando sea posible  
 La complejidad del proceso del diseño está basada directamente en el comportamiento de diseño de los elementos derivados de <xref:System.Windows.Controls.Panel> que utiliza.  Por ejemplo, un control <xref:System.Windows.Controls.Grid> o <xref:System.Windows.Controls.StackPanel> proporciona mucha más funcionalidad que un control <xref:System.Windows.Controls.Canvas>.  El precio de este mayor aumento de la funcionalidad es un aumento mayor de los costes de rendimiento.  Sin embargo, si no requiere la funcionalidad que proporciona un control <xref:System.Windows.Controls.Grid>, debería utilizar alternativas menos costosas, tales como un control <xref:System.Windows.Controls.Canvas> o un panel personalizado.  
  
 Para obtener más información, vea [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md).  
  
### Actualizar en lugar de reemplazar una propiedad RenderTransform  
 Quizá pueda actualizar un objeto <xref:System.Windows.Media.Transform> en lugar de reemplazarlo como valor de una propiedad <xref:System.Windows.UIElement.RenderTransform%2A>.  Esto es particularmente cierto en escenarios que impliquen animación.  Actualizando un objeto <xref:System.Windows.Media.Transform>existente, evitará iniciar un cálculo de diseño innecesario.  
  
### Compilar un árbol descendente  
 Cuando se agrega o se quita un nodo del [árbol lógico](GTMT), se provocan invalidaciones de propiedad en el elemento primario del nodo y en todos sus elementos secundarios.  Como resultado, siempre debe seguirse un modelo de construcción descendente, para evitar el costo de invalidaciones innecesarias en nodos ya validados.  La tabla siguiente muestra la diferencia en velocidad de ejecución entre la compilación de un árbol descendente frente a uno ascendente, donde el árbol tiene 150 niveles de profundidad con un objeto <xref:System.Windows.Controls.TextBlock> y un objeto <xref:System.Windows.Controls.DockPanel> únicos en cada nivel.  
  
|**Acción**|**Compilación del árbol \(en ms\)**|**Representación: incluye la compilación del árbol \(en ms\)**|  
|----------------|-----------------------------------------|--------------------------------------------------------------------|  
|Ascendente|366|454|  
|Descendente|11|96|  
  
 En el siguiente ejemplo de código se muestra cómo crear un árbol descendente.  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 Para obtener más información sobre el árbol lógico, vea [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
## Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Recursos de aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)