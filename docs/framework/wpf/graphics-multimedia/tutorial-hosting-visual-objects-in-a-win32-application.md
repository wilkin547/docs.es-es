---
title: 'Tutorial: Hospedar objetos visuales en una aplicación Win32'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: cc78dfd22b0ad2726ce8870a4e03f539ec691d85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Tutorial: Hospedar objetos visuales en una aplicación Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] código, puede que sea más eficaz agregar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funcionalidad a la aplicación en lugar de volver a escribir el código. Para proporcionar compatibilidad con [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subsistemas de gráficos que usan simultáneamente en una aplicación, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un mecanismo para alojar objetos en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana.  
  
 Este tutorial describe cómo escribir una aplicación de ejemplo, [Hit Test with Win32 interoperación Sample](http://go.microsoft.com/fwlink/?LinkID=159995), que hosts [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos visual en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana.  
  

  
<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos  
 En este tutorial se da por supuesto un conocimiento básico de la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Para obtener una introducción básica a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de programación, vea [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md). Para obtener una introducción a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de programación, vea cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* por Charles Petzold.  
  
> [!NOTE]
>  En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Para el código de ejemplo completo, vea [Hit Test with Win32 interoperación Sample](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Crear la ventana host de Win32  
 La clave para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana es la <xref:System.Windows.Interop.HwndSource> clase. Esta clase se ajusta a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, permitiéndoles incorporarse a su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria.  
  
 En el ejemplo siguiente se muestra el código para crear el <xref:System.Windows.Interop.HwndSource> objeto como el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana contenedora para los objetos visuales. Para establecer el estilo de ventana, posición y otros parámetros para el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, utilice la <xref:System.Windows.Interop.HwndSourceParameters> objeto.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  El valor de la <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> no se puede establecer la propiedad en WS_EX_TRANSPARENT. Esto significa que el host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana no puede ser transparente. Por esta razón, el color de fondo del host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana se establece en el mismo color de fondo que su ventana primaria.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Agregar objetos visuales a la ventana host de Win32  
 Una vez haya creado un host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana contenedora para los objetos visuales, puede agregar objetos visuales a él. Desea asegurarse de que las transformaciones de los objetos visuales, como las animaciones, no se extienden más allá de los límites del host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana del rectángulo delimitador.  
  
 En el ejemplo siguiente se muestra el código para crear el <xref:System.Windows.Interop.HwndSource> de objetos y agregarle objetos visuales.  
  
> [!NOTE]
>  El <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de la <xref:System.Windows.Interop.HwndSource> objeto se establece en el primer objeto visual que se agrega al host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana. El objeto visual raíz define el nodo de nivel superior del árbol de objetos visuales. Los objetos visuales subsiguientes agregados al host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana se agregan como objetos secundarios.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementar el filtro de mensajes de Win32  
 El host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana para los objetos visuales requiere un procedimiento de filtro de mensajes de ventana para controlar los mensajes que se envían a la ventana de la cola de aplicación. El procedimiento de ventana recibe mensajes desde el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] sistema. Pueden ser mensajes de entrada o mensajes de administración de ventanas. Si lo desea, puede administrar un mensaje en el procedimiento de ventana o bien pasar el mensaje al sistema para su procesamiento predeterminado.  
  
 La <xref:System.Windows.Interop.HwndSource> objeto que define como el elemento primario de los objetos visuales debe hacer referencia el procedimiento de filtro de mensajes de ventana que proporcione. Cuando se crea el <xref:System.Windows.Interop.HwndSource> objeto, establezca el <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> propiedad para hacer referencia al procedimiento de ventana.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 En el ejemplo siguiente se muestra el código para controlar los mensajes que se emiten al soltar el botón primario y secundario del ratón. El valor de la coordenada del mouse aciertos de posición se encuentra en el valor de la `lParam` parámetro.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Procesar mensajes de Win32  
 El código en el ejemplo siguiente muestra cómo se realiza una prueba de posicionamiento en la jerarquía de objetos visuales contenida en el host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana. Puede identificar si un punto está dentro de la geometría de un objeto visual, mediante la <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método para especificar el objeto visual raíz y el valor de coordenadas para la prueba de posicionamiento. En este caso, el objeto visual raíz es el valor de la <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de la <xref:System.Windows.Interop.HwndSource> objeto.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Para obtener más información sobre la prueba de posicionamiento en objetos visuales, vea [Hit Testing en la capa Visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Interop.HwndSource>  
 [Realizar pruebas con el ejemplo de interoperación de Win32 de posicionamiento](http://go.microsoft.com/fwlink/?LinkID=159995)  
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
