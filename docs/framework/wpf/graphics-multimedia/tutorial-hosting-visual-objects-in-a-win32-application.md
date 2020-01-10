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
ms.openlocfilehash: 621684e14f9d1b599c4ef60e3731f0f58f31aacd
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740164"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Tutorial: Hospedar objetos visuales en una aplicación Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en código Win32, podría ser más eficaz agregar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funcionalidad a la aplicación en lugar de volver a escribir el código. Para proporcionar compatibilidad con Win32 y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subsistemas de gráficos utilizados simultáneamente en una aplicación, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un mecanismo para hospedar objetos en una ventana de Win32.  
  
 En este tutorial se describe cómo escribir una aplicación de ejemplo, una [prueba de posicionamiento con el ejemplo de interoperación de Win32](https://go.microsoft.com/fwlink/?LinkID=159995), que hospeda [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos visuales en una ventana de Win32.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos de  
 En este tutorial se da por supuesto que está familiarizado con la programación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y Win32. Para obtener una introducción básica a la programación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Tutorial: mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md). Para ver una introducción a la programación de Win32, consulte cualquiera de los numerosos libros sobre el tema, en determinadas *ventanas de programación* , de Charles Petzold.  
  
> [!NOTE]
> En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Para obtener el código de ejemplo completo, vea [prueba de posicionamiento con el ejemplo de interoperación de Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Crear la ventana host de Win32  
 La clave para hospedar objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de Win32 es la clase <xref:System.Windows.Interop.HwndSource>. Esta clase ajusta el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos en una ventana de Win32, lo que permite que se incorporen en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria.  
  
 En el ejemplo siguiente se muestra el código para crear el objeto <xref:System.Windows.Interop.HwndSource> como la ventana contenedor de Win32 para los objetos visuales. Para establecer el estilo, la posición y otros parámetros de la ventana de Win32, use el objeto <xref:System.Windows.Interop.HwndSourceParameters>.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> No se puede establecer el valor de la propiedad <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> en WS_EX_TRANSPARENT. Esto significa que la ventana de Win32 de host no puede ser transparente. Por esta razón, el color de fondo de la ventana de Win32 del host se establece en el mismo color de fondo que su ventana primaria.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Agregar objetos visuales a la ventana host de Win32  
 Una vez que haya creado una ventana contenedor de Win32 de host para los objetos visuales, puede agregarle objetos visuales. Querrá asegurarse de que las transformaciones de los objetos visuales, como las animaciones, no se extienden más allá de los límites del rectángulo delimitador de la ventana de Win32 del host.  
  
 En el ejemplo siguiente se muestra el código para crear el objeto de <xref:System.Windows.Interop.HwndSource> y agregarle objetos visuales.  
  
> [!NOTE]
> La propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource> se establece en el primer objeto visual agregado a la ventana host de Win32. El objeto visual raíz define el nodo de nivel superior del árbol de objetos visuales. Los objetos visuales subsiguientes agregados a la ventana de Win32 de host se agregan como objetos secundarios.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementar el filtro de mensajes de Win32  
 La ventana host de Win32 para los objetos visuales requiere un procedimiento de filtro de mensajes de ventana para controlar los mensajes que se envían a la ventana desde la cola de la aplicación. El procedimiento de ventana recibe mensajes del sistema Win32. Pueden ser mensajes de entrada o mensajes de administración de ventanas. Si lo desea, puede administrar un mensaje en el procedimiento de ventana o bien pasar el mensaje al sistema para su procesamiento predeterminado.  
  
 El objeto <xref:System.Windows.Interop.HwndSource> que definió como elemento primario de los objetos visuales debe hacer referencia al procedimiento de filtro de mensajes de ventana que proporcione. Al crear el objeto de <xref:System.Windows.Interop.HwndSource>, establezca la propiedad <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> para hacer referencia al procedimiento de ventana.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 En el ejemplo siguiente se muestra el código para controlar los mensajes que se emiten al soltar el botón primario y secundario del ratón. El valor de la coordenada de la posición de posicionamiento del mouse se encuentra en el valor del parámetro `lParam`.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Procesar mensajes de Win32  
 El código del ejemplo siguiente muestra cómo se realiza una prueba de posicionamiento en la jerarquía de objetos visuales contenidos en la ventana host de Win32. Puede identificar si un punto está dentro de la geometría de un objeto visual, utilizando el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> para especificar el objeto visual raíz y el valor de la coordenada con respecto a la prueba de posicionamiento. En este caso, el objeto visual raíz es el valor de la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource>.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Para obtener más información sobre las pruebas de posicionamiento en objetos visuales, vea [pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Prueba de posicionamiento con el ejemplo de interoperación de Win32](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
