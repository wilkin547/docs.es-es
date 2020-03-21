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
ms.openlocfilehash: 9d67fbc0d9716c9df3935232c6c7e579b50d55bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148327"
---
# <a name="using-drawingvisual-objects"></a>Usar objetos DrawingVisual
En este tema se proporciona <xref:System.Windows.Media.DrawingVisual> información [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] general sobre cómo utilizar objetos en la capa visual.  
  
<a name="drawingvisual_object"></a>
## <a name="drawingvisual-object"></a>Objeto DrawingVisual  
 Es <xref:System.Windows.Media.DrawingVisual> una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto. Esta clase se considera ligera porque no proporciona control de diseño ni evento, lo que mejora su rendimiento. Por esta razón, los dibujos son ideales para fondos e imágenes prediseñadas.  
  
<a name="drawingvisual_host_container"></a>
## <a name="drawingvisual-host-container"></a>Contenedor host de objetos DrawingVisual  
 Para utilizar <xref:System.Windows.Media.DrawingVisual> objetos, debe crear un contenedor host para los objetos. El objeto contenedor host <xref:System.Windows.FrameworkElement> debe derivar de la clase, que <xref:System.Windows.Media.DrawingVisual> proporciona la compatibilidad de diseño y control de eventos que carece la clase. El objeto contenedor host no muestra ninguna propiedad visible, puesto que su finalidad principal es contener objetos secundarios. Sin <xref:System.Windows.UIElement.Visibility%2A> embargo, la propiedad del <xref:System.Windows.Visibility.Visible>contenedor host debe establecerse en ; de lo contrario, ninguno de sus elementos secundarios será visible.  
  
 Al crear un objeto contenedor host para objetos visuales, <xref:System.Windows.Media.VisualCollection>debe almacenar las referencias de objetos visuales en un archivo . Utilice <xref:System.Windows.Media.VisualCollection.Add%2A> el método para agregar un objeto visual al contenedor host. En el ejemplo siguiente, se crea un objeto contenedor host <xref:System.Windows.Media.VisualCollection>y se agregan tres objetos visuales a su archivo .  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
<a name="creating_drawingvisual_objects"></a>
## <a name="creating-drawingvisual-objects"></a>Crear objetos DrawingVisual  
 Al crear <xref:System.Windows.Media.DrawingVisual> un objeto, no tiene contenido de dibujo. Puede añadir texto, gráficos o contenido de imagen <xref:System.Windows.Media.DrawingContext> recuperando el objeto y dibujando en él. A <xref:System.Windows.Media.DrawingContext> se devuelve <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> llamando al <xref:System.Windows.Media.DrawingVisual> método de un objeto.  
  
 Para dibujar un <xref:System.Windows.Media.DrawingContext>rectángulo en <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> el <xref:System.Windows.Media.DrawingContext> , utilice el método del objeto. Existen métodos similares para dibujar otros tipos de contenido. Cuando haya terminado de <xref:System.Windows.Media.DrawingContext>dibujar contenido <xref:System.Windows.Media.DrawingContext.Close%2A> en el <xref:System.Windows.Media.DrawingContext> , llame al método para cerrar y conservar el contenido.  
  
 En el ejemplo <xref:System.Windows.Media.DrawingVisual> siguiente, se crea un objeto <xref:System.Windows.Media.DrawingContext>y se dibuja un rectángulo en su archivo .  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>
## <a name="creating-overrides-for-frameworkelement-members"></a>Crear invalidaciones para los miembros FrameworkElement  
 El objeto contenedor host es responsable de administrar su colección de objetos visuales. Esto requiere que el contenedor host implemente invalidaciones de miembro para la clase derivada. <xref:System.Windows.FrameworkElement>  
  
 En la lista siguiente se describen los dos miembros que debe invalidar:  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: devuelve un elemento secundario en el índice especificado de la colección de elementos secundarios.  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Obtiene el número de elementos secundarios visuales dentro de este elemento.  
  
 En el ejemplo siguiente, se <xref:System.Windows.FrameworkElement> implementan las invalidaciones de los dos miembros.  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>
## <a name="providing-hit-testing-support"></a>Proporcionar compatibilidad con las pruebas de posicionamiento  
 El objeto contenedor host puede proporcionar control de eventos incluso si <xref:System.Windows.UIElement.Visibility%2A> no muestra <xref:System.Windows.Visibility.Visible>ninguna propiedad visible, sin embargo, su propiedad debe establecerse en . Esto permite crear una rutina de control de eventos para el contenedor host que pueda interceptar los eventos del mouse, tales como soltar el botón izquierdo. A continuación, la rutina de control <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> de eventos puede implementar pruebas de posicionación invocando el método. El parámetro <xref:System.Windows.Media.HitTestResultCallback> del método hace referencia a un procedimiento definido por el usuario que puede usar para determinar la acción resultante de una prueba de posicionamiento.  
  
 En el ejemplo siguiente, se implementa la compatibilidad con las pruebas de posicionamiento para el objeto contenedor host y sus elementos secundarios.  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
