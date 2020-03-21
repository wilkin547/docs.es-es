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
ms.openlocfilehash: d04357e0770bbf8eebe8f40a86a19ddc9baae3ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187427"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Tutorial: Hospedar objetos visuales en una aplicación Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, cuando tiene una inversión sustancial en código [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Win32, podría ser más eficaz agregar funcionalidad a la aplicación en lugar de reescribir el código. Para proporcionar compatibilidad con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Win32 y los subsistemas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de gráficos utilizados simultáneamente en una aplicación, proporciona un mecanismo para hospedar objetos en una ventana de Win32.  
  
 En este tutorial se describe cómo escribir una aplicación de ejemplo, [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting), que hospeda objetos visuales [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de Win32.  

<a name="requirements"></a>
## <a name="requirements"></a>Requisitos  
 Este tutorial asume una familiaridad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] básica con la programación de Win32. Para obtener una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] introducción básica a la programación, vea [Tutorial: Mi primera aplicación](../getting-started/walkthrough-my-first-wpf-desktop-application.md)de escritorio WPF . Para una introducción a la programación de Win32, vea cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* de Charles Petzold.  
  
> [!NOTE]
> En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Para obtener el código de ejemplo completo, consulte Prueba de posicionamiento con ejemplo de [interoperación de Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a>Crear la ventana host de Win32  
 La clave [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para hospedar objetos en <xref:System.Windows.Interop.HwndSource> una ventana Win32 es la clase. Esta clase ajusta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los objetos en una ventana de Win32, lo que permite que se incorporen a su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria.  
  
 En el ejemplo siguiente se <xref:System.Windows.Interop.HwndSource> muestra el código para crear el objeto como la ventana contenedora Win32 para los objetos visuales. Para establecer el estilo de ventana, la posición y otros <xref:System.Windows.Interop.HwndSourceParameters> parámetros para la ventana Win32, utilice el objeto.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> El valor <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> de la propiedad no se puede establecer en WS_EX_TRANSPARENT. Esto significa que la ventana de Win32 del host no puede ser transparente. Por este motivo, el color de fondo de la ventana Win32 del host se establece en el mismo color de fondo que su ventana principal.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Agregar objetos visuales a la ventana host de Win32  
 Una vez que haya creado una ventana contenedora de Win32 host para los objetos visuales, puede agregarle objetos visuales. Querrá asegurarse de que las transformaciones de los objetos visuales, como animaciones, no se extiendan más allá de los límites del rectángulo delimitador de la ventana Win32 del host.  
  
 En el ejemplo siguiente se <xref:System.Windows.Interop.HwndSource> muestra el código para crear el objeto y agregarle objetos visuales.  
  
> [!NOTE]
> La <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad <xref:System.Windows.Interop.HwndSource> del objeto se establece en el primer objeto visual agregado a la ventana Win32 host. El objeto visual raíz define el nodo de nivel superior del árbol de objetos visuales. Los objetos visuales posteriores agregados a la ventana Win32 del host se agregan como objetos secundarios.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a>Implementar el filtro de mensajes de Win32  
 La ventana Win32 host para los objetos visuales requiere un procedimiento de filtro de mensajes de ventana para controlar los mensajes que se envían a la ventana desde la cola de aplicaciones. El procedimiento de ventana recibe mensajes del sistema Win32. Pueden ser mensajes de entrada o mensajes de administración de ventanas. Si lo desea, puede administrar un mensaje en el procedimiento de ventana o bien pasar el mensaje al sistema para su procesamiento predeterminado.  
  
 El <xref:System.Windows.Interop.HwndSource> objeto que definió como el elemento primario de los objetos visuales debe hacer referencia al procedimiento de filtro de mensajes de ventana que proporcione. Al crear <xref:System.Windows.Interop.HwndSource> el objeto, <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> establezca la propiedad para hacer referencia al procedimiento de ventana.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 En el ejemplo siguiente se muestra el código para controlar los mensajes que se emiten al soltar el botón primario y secundario del ratón. El valor de coordenadas de la posición de `lParam` posicionamiento del ratón está contenido en el valor del parámetro.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a>Procesar mensajes de Win32  
 El código del ejemplo siguiente muestra cómo se realiza una prueba de posicionación en la jerarquía de objetos visuales contenida en la ventana Win32 del host. Puede identificar si un punto está dentro de la <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> geometría de un objeto visual, utilizando el método para especificar el objeto visual raíz y el valor de coordenadas con el que se va a realizar la prueba de posicionamiento. En este caso, el objeto visual <xref:System.Windows.Interop.HwndSource.RootVisual%2A> raíz es <xref:System.Windows.Interop.HwndSource> el valor de la propiedad del objeto.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Para obtener más información sobre las pruebas de posicionamiento con objetos visuales, consulte Pruebas de [posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Interop.HwndSource>
- [Ejemplo de prueba de posicionamiento de interoperabilidad con Win32](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
