---
title: 'Optimizar el rendimiento: Presentación y diseño'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
ms.openlocfilehash: c5dd567fa9f5db69c52072a1cc67b5c574f8e1f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623877"
---
# <a name="optimizing-performance-layout-and-design"></a>Optimizar el rendimiento: Presentación y diseño
El diseño de su aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede afectar a su rendimiento si se crea una sobrecarga innecesaria al calcular el diseño y validar las referencias de objeto. La construcción de objetos, especialmente en tiempo de ejecución, puede afectar a las características de rendimiento de la aplicación.  
  
 En este tema se proporcionan recomendaciones de rendimiento para estas áreas.  
  
## <a name="layout"></a>Diseño  
 El término "pase de diseño" describe el proceso de medir y organizar los miembros de un <xref:System.Windows.Controls.Panel>-derivados de la colección de elementos secundarios y, a continuación, dibújelos en la pantalla del objeto. El pase de diseño es un proceso matemáticamente intensivo: cuanto mayor sea el número de elementos secundarios de la colección, mayor es el número de cálculos necesarios. Por ejemplo, cada vez que un elemento secundario <xref:System.Windows.UIElement> objeto de la colección cambia de posición, tiene potencial para desencadenar un nuevo pase por el sistema de diseño. Debido a la estrecha relación entre las características del objeto y el comportamiento de diseño, es importante conocer el tipo de eventos que puede invocar el sistema de diseño. La aplicación funcionará mejor si se reduce tanto como sea posible cualquier invocación innecesaria del pase de diseño.  
  
 El sistema de diseño completa dos pases por cada miembro secundario de una colección: un pase de medición y un pase de organización. Cada objeto secundario proporciona su propia implementación invalidada del <xref:System.Windows.UIElement.Measure%2A> y <xref:System.Windows.UIElement.Arrange%2A> métodos con el fin de proporcionar su propio comportamiento de diseño específico. En su forma más simple, el diseño es un sistema recursivo que permite dibujar y situar un elemento, así como cambiar su tamaño en pantalla.  
  
-   Un elemento secundario <xref:System.Windows.UIElement> objeto comienza el proceso de diseño, se miden las propiedades del núcleo.  
  
-   El objeto <xref:System.Windows.FrameworkElement> propiedades que están relacionadas con el tamaño, como <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, y <xref:System.Windows.FrameworkElement.Margin%2A>, se evalúan.  
  
-   <xref:System.Windows.Controls.Panel>-se aplica la lógica específica, como el <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad de la <xref:System.Windows.Controls.DockPanel>, o el <xref:System.Windows.Controls.StackPanel.Orientation%2A> propiedad de la <xref:System.Windows.Controls.StackPanel>.  
  
-   El contenido se organiza o se sitúa después de haberse medido todos los objetos secundarios.  
  
-   La colección de objetos secundarios se dibuja en la pantalla.  
  
 Se vuelve a invocar el proceso de pase de diseño si se produce alguna de las siguientes acciones:  
  
-   Un objeto secundario se agrega a la colección.  
  
-   Un <xref:System.Windows.FrameworkElement.LayoutTransform%2A> se aplica a los objetos secundarios.  
  
-   El <xref:System.Windows.UIElement.UpdateLayout%2A> se llama al método del objeto secundario.  
  
-   Cuando se produce un cambio en el valor de una propiedad de dependencia que se marca con metadatos que afectan a los pases de medición o de organización.  
  
### <a name="use-the-most-efficient-panel-where-possible"></a>Usar el panel más eficaz cuando sea posible  
 La complejidad del proceso de diseño se basa directamente en el comportamiento de diseño de la <xref:System.Windows.Controls.Panel>-elementos usas derivados. Por ejemplo, un <xref:System.Windows.Controls.Grid> o <xref:System.Windows.Controls.StackPanel> control proporciona mucha más funcionalidad que un <xref:System.Windows.Controls.Canvas> control. El precio de este mayor aumento de funcionalidad es el mayor aumento de los costos de rendimiento. Sin embargo, si no necesita la funcionalidad que un <xref:System.Windows.Controls.Grid> proporciona control, debe usar alternativas menos costosas, como un <xref:System.Windows.Controls.Canvas> o un panel personalizado.  
  
 Para más información, consulte [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md).  
  
### <a name="update-rather-than-replace-a-rendertransform"></a>Actualizar en lugar de reemplazar una propiedad RenderTransform  
 Es posible que pueda actualizar una <xref:System.Windows.Media.Transform> en lugar de reemplazarla como el valor de un <xref:System.Windows.UIElement.RenderTransform%2A> propiedad. Esto es especialmente cierto en escenarios que implican animación. Si actualiza una existente <xref:System.Windows.Media.Transform>, evite iniciar un cálculo de diseño innecesarios.  
  
### <a name="build-your-tree-top-down"></a>Compilar el árbol de arriba a abajo  
 Cuando se agrega o se quita un nodo del árbol lógico, se generan invalidaciones de propiedades en el elemento principal del nodo y en todos sus elementos secundarios. Como resultado, siempre debe seguir un patrón de compilación de arriba a abajo para evitar el costo de invalidaciones innecesarias en los nodos que ya están validados. En la tabla siguiente se muestra la diferencia en la velocidad de ejecución entre la generación de un árbol de arriba a abajo, en lugar de abajo a arriba, donde el árbol tiene 150 niveles de profundidad con un solo <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.DockPanel> en cada nivel.  
  
|**Acción**|**Compilación del árbol (en ms)**|**Representar: incluye la compilación del árbol (en ms)**|  
|----------------|---------------------------------|-------------------------------------------------|  
|De abajo a arriba|366|454|  
|De arriba a abajo|11|96|  
  
 En el siguiente ejemplo de código se muestra cómo crear un árbol de arriba a abajo.  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 Para más información acerca del árbol lógico, consulte [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
## <a name="see-also"></a>Vea también
- [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)
- [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)
- [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)
- [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
- [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
- [Diseño](../../../../docs/framework/wpf/advanced/layout.md)
