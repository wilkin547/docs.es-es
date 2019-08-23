---
title: Usar objetos DrawingVisual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: 4e6fc89b64f7b0acc1a0077708d567eb97e2868e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962827"
---
# <a name="using-drawingvisual-objects"></a>Usar objetos DrawingVisual
En este tema se proporciona información general sobre cómo <xref:System.Windows.Media.DrawingVisual> usar objetos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la capa visual.  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>Objeto DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> Es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto. Esta clase se considera ligera porque no proporciona control de diseño ni control de eventos, lo que mejora su rendimiento. Por esta razón, los dibujos son ideales para fondos e imágenes prediseñadas.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>Contenedor host de objetos DrawingVisual  
 Para usar <xref:System.Windows.Media.DrawingVisual> objetos, debe crear un contenedor host para los objetos. El objeto contenedor host debe derivar de <xref:System.Windows.FrameworkElement> la clase, que proporciona el diseño y la compatibilidad con el <xref:System.Windows.Media.DrawingVisual> control de eventos que la clase no tiene. El objeto contenedor host no muestra ninguna propiedad visible, puesto que su finalidad principal es contener objetos secundarios. Sin embargo, <xref:System.Windows.UIElement.Visibility%2A> la propiedad del contenedor host debe establecerse en <xref:System.Windows.Visibility.Visible>; de lo contrario, ninguno de sus elementos secundarios será visible.  
  
 Cuando se crea un objeto contenedor host para objetos visuales, es necesario almacenar las referencias de objeto visual en un <xref:System.Windows.Media.VisualCollection>. Use el <xref:System.Windows.Media.VisualCollection.Add%2A> método para agregar un objeto visual al contenedor host. En el ejemplo siguiente, se crea un objeto contenedor host y se agregan tres objetos visuales a su <xref:System.Windows.Media.VisualCollection>.  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>Crear objetos DrawingVisual  
 Cuando se crea un <xref:System.Windows.Media.DrawingVisual> objeto, no tiene ningún contenido de dibujo. Puede Agregar texto, gráficos o contenido de imagen recuperando el objeto <xref:System.Windows.Media.DrawingContext> y dibujando en él. Se <xref:System.Windows.Media.DrawingContext> devuelve una <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> llamada al método de un <xref:System.Windows.Media.DrawingVisual> objeto.  
  
 Para dibujar un rectángulo en <xref:System.Windows.Media.DrawingContext>, utilice el <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> método del <xref:System.Windows.Media.DrawingContext> objeto. Existen métodos similares para dibujar otros tipos de contenido. Cuando haya terminado de dibujar el contenido en <xref:System.Windows.Media.DrawingContext>, <xref:System.Windows.Media.DrawingContext.Close%2A> llame al método para cerrar <xref:System.Windows.Media.DrawingContext> y conservar el contenido.  
  
 En el ejemplo siguiente, se <xref:System.Windows.Media.DrawingVisual> crea un objeto y se dibuja un rectángulo en su. <xref:System.Windows.Media.DrawingContext>  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>Crear invalidaciones para los miembros FrameworkElement  
 El objeto contenedor host es responsable de administrar su colección de objetos visuales. Esto requiere que el contenedor host implemente invalidaciones de miembros para <xref:System.Windows.FrameworkElement> la clase derivada.  
  
 En la lista siguiente se describen los dos miembros que debe invalidar:  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Devuelve un elemento secundario en el índice especificado de la colección de elementos secundarios.  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Obtiene el número de elementos secundarios visuales de este elemento.  
  
 En el ejemplo siguiente, se implementan las invalidaciones de los dos <xref:System.Windows.FrameworkElement> miembros.  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>Proporcionar compatibilidad con las pruebas de posicionamiento  
 El objeto contenedor host puede proporcionar control de eventos incluso si no muestra ninguna propiedad visible; sin embargo, su <xref:System.Windows.UIElement.Visibility%2A> propiedad debe establecerse en <xref:System.Windows.Visibility.Visible>. Esto permite crear una rutina de control de eventos para el contenedor host que pueda interceptar los eventos del mouse, tales como soltar el botón izquierdo. La rutina de control de eventos puede, a continuación, implementar la <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> prueba de posicionamiento invocando el método. El parámetro del <xref:System.Windows.Media.HitTestResultCallback> método hace referencia a un procedimiento definido por el usuario que puede usar para determinar la acción resultante de una prueba de posicionamiento.  
  
 En el ejemplo siguiente, se implementa la compatibilidad con las pruebas de posicionamiento para el objeto contenedor host y sus elementos secundarios.  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
