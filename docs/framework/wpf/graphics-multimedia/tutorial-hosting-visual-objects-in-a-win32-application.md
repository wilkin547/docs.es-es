---
title: "Tutorial: Hospedar objetos visuales en una aplicaci&#243;n Win32 | Microsoft Docs"
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
  - "hospedaje, objetos visuales en código Win32"
  - "objetos visuales en código Win32"
  - "código Win32, objetos visuales en"
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Tutorial: Hospedar objetos visuales en una aplicaci&#243;n Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno enriquecido para la creación de aplicaciones.  Sin embargo, cuando ya se tiene una inversión sustancial en código de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], puede ser más eficaz agregar la funcionalidad de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación en lugar de volver a escribir el código.  Para proporcionar la compatibilidad con los subsistemas de gráficos de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se utilizan de manera simultánea en una aplicación, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un mecanismo para hospedar objetos en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 Este tutorial describe cómo escribir una aplicación de ejemplo, [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995), que hospeda objetos visuales de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
   
  
<a name="requirements"></a>   
## Requisitos  
 En este tutorial se da por hecho que está familiarizado con la programación básica en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Para obtener una introducción básica a la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  Para obtener una introducción a la programación en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], vea cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* escrito por Charles Petzold.  
  
> [!NOTE]
>  En este tutorial se incluyen varios ejemplos de código del ejemplo asociado.  Sin embargo, para facilitar la legibilidad, no se incluye el código de ejemplo completo.  Para obtener el ejemplo de código completo, vea [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## Crear la ventana host de Win32  
 La clave para hospedar objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] es la clase <xref:System.Windows.Interop.HwndSource>.  Esta clase ajusta los objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], con lo que permite incorporarlos a la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria.  
  
 En el ejemplo siguiente se muestra el código utilizado para crear el objeto <xref:System.Windows.Interop.HwndSource> como la ventana contenedora de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para los objetos visuales.  Para establecer el estilo, la posición y otros parámetros de la ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, utilice el objeto <xref:System.Windows.Interop.HwndSourceParameters>.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  El valor de la propiedad <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> no se puede establecer en WS\_EX\_TRANSPARENT.  Esto significa que la ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] no puede ser transparente.  Por esta razón, el color de fondo de la ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] está establecido en el mismo color de fondo que su ventana primaria.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## Agregar objetos visuales a la ventana host de Win32  
 Una vez creada la ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenedora para los objetos visuales, puede agregarle los objetos visuales.  Es conveniente asegurarse de que ninguna transformación de los objetos visuales, como las animaciones, se extienda más allá de los límites del rectángulo delimitador de la ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 En el ejemplo siguiente se muestra el código utilizado para crear el objeto <xref:System.Windows.Interop.HwndSource> y agregarle objetos visuales.  
  
> [!NOTE]
>  La propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource> se establece en el primer objeto visual agregado a la ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  El objeto visual raíz define el nodo de nivel superior del árbol de objetos visuales.  Todos los objetos visuales subsiguientes se agregan a la ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] como objetos secundarios.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## Implementar el filtro de mensajes de Win32  
 La ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para los objetos visuales requiere un procedimiento de filtro de mensaje de ventana que administre los mensajes que se envían a la ventana desde la cola de la aplicación.  El procedimiento de ventana recibe los mensajes del sistema de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Éstos pueden ser mensajes de entrada o de administración de ventanas.  Si lo desea, puede administrar un mensaje en el procedimiento de ventana o pasárselo al sistema para que se efectúe el procesamiento predeterminado.  
  
 El objeto <xref:System.Windows.Interop.HwndSource> que definió como elemento primario para los objetos visuales debe hacer referencia al procedimiento de filtro de mensajes de ventana que proporcione.  Al crear el objeto <xref:System.Windows.Interop.HwndSource>, establezca la <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> de tal forma que haga referencia al procedimiento de ventana.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 En el ejemplo siguiente se muestra el código para administrar los mensajes que se emiten al soltar el botón primario y secundario del mouse.  El valor del parámetro `lParam` contiene el valor de las coordenadas de la posición donde se hace clic con el mouse.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## Procesar mensajes de Win32  
 En el código del ejemplo siguiente se muestra cómo se efectúa una prueba de posicionamiento con respecto a la jerarquía de objetos visuales contenida en la ventana host de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Puede identificar si un punto está dentro de la geometría de un objeto visual utilizando el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> para especificar el objeto visual raíz y el valor de las coordenadas con las que se comparará la prueba de posicionamiento.  En este caso, el objeto visual raíz es el valor de la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource>.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Para obtener más información sobre las pruebas de posicionamiento con respecto a objetos visuales, vea [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
## Vea también  
 <xref:System.Windows.Interop.HwndSource>   
 [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995)   
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)