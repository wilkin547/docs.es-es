---
title: "C&#243;mo: Realizar pruebas de posicionamiento mediante un contenedor host Win32 | Microsoft Docs"
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
  - "prueba de visitas, utilizar contenedores host Win32"
  - "objetos visuales, pruebas de posicionamiento en"
  - "contenedores host Win32, pruebas de posicionamiento con"
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Realizar pruebas de posicionamiento mediante un contenedor host Win32
Puede crear objetos visuales dentro de una ventana de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] proporcionando un contenedor de ventana host para ellos.  Para proporcionar el control de eventos para los objetos visuales contenidos, se procesan los mensajes que se pasan al bucle de filtro de mensajes del contenedor de ventana host.  Vea [Tutorial: Hospedar objetos visuales en una aplicación Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) para obtener más información sobre cómo hospedar objetos visuales en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
## Ejemplo  
 En el código siguiente se muestra cómo configurar controladores de eventos de mouse para una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] que se utiliza como contenedor host para objetos visuales.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 En el ejemplo siguiente se muestra cómo establecer a una [prueba de posicionamiento](GTMT) en respuesta a la interceptación de eventos de mouse concretos.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 El objeto <xref:System.Windows.Interop.HwndSource> presenta el contenido de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]. El valor de la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource> representa el nodo de nivel superior en la jerarquía de [árbol visual](GTMT).  
  
 Para obtener el ejemplo completo sobre cómo realizar pruebas de posicionamiento de objetos mediante un contenedor host de Win32, vea [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
## Vea también  
 <xref:System.Windows.Interop.HwndSource>   
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Tutorial: Hospedar objetos visuales en una aplicación Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)