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
ms.openlocfilehash: c8baefbf01467a65626a77f300f34a145d5c7281
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962871"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Tutorial: Hospedar objetos visuales en una aplicación Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] código, podría ser más eficaz agregar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funcionalidad a la aplicación en lugar de volver a escribir el código. Para [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] proporcionar compatibilidad con los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subsistemas de gráficos y utilizados simultáneamente en una aplicación, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un mecanismo para hospedar objetos en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] una ventana.  
  
 En este tutorial se describe cómo escribir una aplicación de ejemplo, una [prueba de posicionamiento con el ejemplo](https://go.microsoft.com/fwlink/?LinkID=159995)de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] interoperación de Win32 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , que hospeda objetos visuales en una ventana.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos  
 En este tutorial se da por supuesto un conocimiento básico de la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Para obtener una introducción básica [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la programación [, vea Tutorial: Mi primera aplicación](../getting-started/walkthrough-my-first-wpf-desktop-application.md)de escritorio WPF. Para obtener una introducción [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] a la programación, consulte cualquiera de los numerosos libros sobre el tema, en determinadas *ventanas de programación* , de Charles Petzold.  
  
> [!NOTE]
> En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Para obtener el código de ejemplo completo, vea [prueba de posicionamiento con el ejemplo de interoperación de Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Crear la ventana host de Win32  
 La clave para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos en una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana es <xref:System.Windows.Interop.HwndSource> la clase. Esta clase ajusta los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos en una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, lo que permite que se incorporen en [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] su como una ventana secundaria.  
  
 En el ejemplo siguiente se muestra el código para <xref:System.Windows.Interop.HwndSource> crear el objeto [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] como la ventana contenedor de los objetos visuales. Para establecer el estilo, la posición y otros parámetros de la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, use el <xref:System.Windows.Interop.HwndSourceParameters> objeto.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> El valor de la <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> propiedad no se puede establecer en WS_EX_TRANSPARENT. Esto significa que la ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] host no puede ser transparente. Por esta razón, el color de fondo de la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana host se establece en el mismo color de fondo que su ventana primaria.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Agregar objetos visuales a la ventana host de Win32  
 Una vez que haya creado una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana contenedora de host para los objetos visuales, puede agregarle objetos visuales. Querrá asegurarse de que las transformaciones de los objetos visuales, como las animaciones, no se extienden más allá de los límites del rectángulo delimitador de la ventana host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] .  
  
 En el ejemplo siguiente se muestra el código para <xref:System.Windows.Interop.HwndSource> crear el objeto y agregarle objetos visuales.  
  
> [!NOTE]
> La <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] del objeto se establece en el primer objeto visual agregado a la ventana host. <xref:System.Windows.Interop.HwndSource> El objeto visual raíz define el nodo de nivel superior del árbol de objetos visuales. Los objetos visuales subsiguientes agregados [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] a la ventana host se agregan como objetos secundarios.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementar el filtro de mensajes de Win32  
 La ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] host de los objetos visuales requiere un procedimiento de filtro de mensajes de ventana para controlar los mensajes que se envían a la ventana desde la cola de la aplicación. El procedimiento de ventana recibe mensajes del [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] sistema. Pueden ser mensajes de entrada o mensajes de administración de ventanas. Si lo desea, puede administrar un mensaje en el procedimiento de ventana o bien pasar el mensaje al sistema para su procesamiento predeterminado.  
  
 El <xref:System.Windows.Interop.HwndSource> objeto que ha definido como elemento primario de los objetos visuales debe hacer referencia al procedimiento de filtro de mensajes de ventana que proporcione. Al crear el <xref:System.Windows.Interop.HwndSource> objeto, establezca la <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> propiedad para que haga referencia al procedimiento de ventana.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 En el ejemplo siguiente se muestra el código para controlar los mensajes que se emiten al soltar el botón primario y secundario del ratón. El valor de la coordenada de la posición de posicionamiento del mouse está incluido `lParam` en el valor del parámetro.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Procesar mensajes de Win32  
 El código del ejemplo siguiente muestra cómo se realiza una prueba de posicionamiento en la jerarquía de objetos visuales contenidos en la ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] host. Puede identificar si un punto está dentro de la geometría de un objeto visual, utilizando el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método para especificar el objeto visual raíz y el valor de la coordenada con respecto a la prueba de posicionamiento. En este caso, el objeto visual raíz es el valor de la <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad <xref:System.Windows.Interop.HwndSource> del objeto.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Para obtener más información sobre las pruebas de posicionamiento en objetos visuales, vea [pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Prueba de posicionamiento con el ejemplo de interoperación de Win32](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
