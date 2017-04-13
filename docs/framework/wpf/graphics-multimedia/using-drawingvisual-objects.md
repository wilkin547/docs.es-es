---
title: "Usar objetos DrawingVisual | Microsoft Docs"
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
  - "DrawingVisual (objetos) en la capa visual"
  - "capa visual, DrawingVisual (objetos)"
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Usar objetos DrawingVisual
En este tema se proporciona información general sobre cómo utilizar los objetos <xref:System.Windows.Media.DrawingVisual> en la capa visual de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Este tema contiene las secciones siguientes.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Objeto DrawingVisual](#drawing_visual_object)  
  
-   [Contenedor host de DrawingVisual](#drawingvisual_host_container)  
  
-   [Crear objetos DrawingVisual](#creating_drawingvisual_objects)  
  
-   [Crear invalidaciones para miembros de FrameworkElement](#creating_overrides)  
  
-   [Proporcionar compatibilidad con las pruebas de posicionamiento](#providing_hit_testing_support)  
  
-   [Temas relacionados](#seeAlsoToggle)  
  
<a name="drawingvisual_object"></a>   
## Objeto DrawingVisual  
 <xref:System.Windows.Media.DrawingVisual> es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto.  Esta clase se considera ligera porque no proporciona administración del diseño ni control de eventos, lo que mejora su rendimiento.  Por esta razón, los dibujos son idóneos para fondos e imágenes prediseñadas.  
  
<a name="drawingvisual_host_container"></a>   
## Contenedor host de DrawingVisual  
 A fin de usar los objetos <xref:System.Windows.Media.DrawingVisual>, debe crear un contenedor host para ellos.  El objeto contenedor host debe derivarse de la clase <xref:System.Windows.FrameworkElement>, que proporciona el diseño y la compatibilidad con el control de eventos que la clase <xref:System.Windows.Media.DrawingVisual> no tiene.  El objeto contenedor host no muestra ninguna propiedad visible, puesto que su finalidad principal es contener objetos secundarios.  Sin embargo, la propiedad <xref:System.Windows.UIElement.Visibility%2A> del contenedor host debe estar establecida en <xref:System.Windows.Visibility>; de lo contrario, ninguno de sus elementos secundarios estará visible.  
  
 Cuando se crea un objeto contenedor host para objetos visuales, es preciso almacenar las referencias a objeto visuales en <xref:System.Windows.Media.VisualCollection>.  Utilice el método <xref:System.Windows.Media.VisualCollection.Add%2A> para agregar un objeto visual al contenedor host.  En el ejemplo siguiente, se crea un objeto contenedor host y se agregan tres objetos visuales a su colección <xref:System.Windows.Media.VisualCollection>.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  Para obtener el ejemplo de código completo del que se ha extraído el ejemplo de código anterior, vea [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## Crear objetos DrawingVisual  
 Al crear un objeto <xref:System.Windows.Media.DrawingVisual>, no tiene contenido de dibujo.  Puede agregar contenidos de texto, gráficos o imágenes recuperando el objeto <xref:System.Windows.Media.DrawingContext> del objeto y dibujando en él.  Para devolver un contexto de dibujo \(<xref:System.Windows.Media.DrawingContext>\), se llama al método <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> de un objeto <xref:System.Windows.Media.DrawingVisual>.  
  
 Para dibujar un rectángulo en <xref:System.Windows.Media.DrawingContext>, utilice el método <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> del objeto <xref:System.Windows.Media.DrawingContext>.  Existen métodos similares para dibujar otros tipos de contenido.  Cuando haya terminado de dibujar contenido en <xref:System.Windows.Media.DrawingContext>, llame al método <xref:System.Windows.Media.DrawingContext.Close%2A> para cerrar el <xref:System.Windows.Media.DrawingContext> y conservar el contenido.  
  
 En el ejemplo siguiente, se crea un objeto <xref:System.Windows.Media.DrawingVisual> y se dibuja un rectángulo en <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## Crear invalidaciones para miembros de FrameworkElement  
 El objeto contenedor host es responsable de administrar su colección de objetos visuales.  Para ello, el contenedor host debe implementar invalidaciones de miembros para la clase <xref:System.Windows.FrameworkElement> derivada.  
  
 En la lista siguiente se describen los dos miembros que se deben invalidar:  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: devuelve un elemento secundario en el índice especificado de la colección de elementos secundarios.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: obtiene el número de elementos secundarios visuales de este elemento.  
  
 En el ejemplo siguiente, se implementan invalidaciones para los dos miembros de <xref:System.Windows.FrameworkElement>.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## Proporcionar compatibilidad con las pruebas de posicionamiento  
 El objeto contenedor host puede proporcionar control de eventos aunque no muestre ninguna propiedad visible. Sin embargo, su propiedad <xref:System.Windows.UIElement.Visibility%2A> debe estar establecida en <xref:System.Windows.Visibility>.  Esto permite crear una rutina de control de eventos para el contenedor host capaz de interceptar los eventos del mouse, tales como soltar el botón primario.  A continuación, la rutina de control de eventos puede implementar pruebas de posicionamiento invocando el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  El parámetro <xref:System.Windows.Media.HitTestResultCallback> del método hace referencia a un procedimiento definido por el usuario que puede utilizar para determinar la acción resultante de una prueba de posicionamiento.  
  
 En el ejemplo siguiente, se implementa la compatibilidad con las pruebas de posicionamiento del objeto contenedor host y sus elementos secundarios.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## Vea también  
 <xref:System.Windows.Media.DrawingVisual>   
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>   
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)