---
title: "Tutorial: Crear su primera aplicaci&#243;n t&#225;ctil | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "crear una aplicación de pantalla táctil [WPF]"
  - "crear una aplicación sensible al tacto [WPF]"
  - "aplicaciones de pantalla táctil [WPF], crear"
  - "aplicaciones sensibles al tacto [WPF], crear"
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Tutorial: Crear su primera aplicaci&#243;n t&#225;ctil
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite que las aplicaciones respondan a la entrada táctil.  Por ejemplo, puede interactuar con una aplicación usando uno o más dedos en un dispositivo sensible al tacto, como una pantalla táctil. Este tutorial crea una aplicación que permite al usuario mover, cambiar el tamaño o girar un único objeto utilizando una entrada táctil.  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Un dispositivo que acepte la entrada táctil, como una pantalla táctil, compatible con Windows Touch.  
  
 Además, debe tener conocimientos básicos de cómo crear una aplicación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especialmente cómo suscribirse a un evento y controlarlo.  Para obtener más información, vea [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Crear la aplicación  
  
#### Para crear la aplicación  
  
1.  Cree un nuevo proyecto de aplicación de WPF en Visual Basic o en Visual C\# denominado `BasicManipulation`.  Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/es-es/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Reemplace el contenido de MainWindow.xaml con el código XAML siguiente.  
  
     Este marcado crea una aplicación sencilla que contiene un <xref:System.Windows.Shapes.Rectangle> rojo en un <xref:System.Windows.Controls.Canvas>.  La propiedad <xref:System.Windows.UIElement.IsManipulationEnabled%2A> de <xref:System.Windows.Shapes.Rectangle> está establecida en true, por lo que recibirá los eventos de manipulación.  La aplicación se suscribe a los eventos <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationInertiaStarting> y <xref:System.Windows.UIElement.ManipulationDelta>.  Estos eventos contienen la lógica para mover <xref:System.Windows.Shapes.Rectangle> cuando el usuario lo manipule.  
  
     [!code-xml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Si usa Visual Basic, en la primera línea de MainWindow.xaml, reemplace `x:Class="BasicManipulation.MainWindow"` con `x:Class="MainWindow"`.  
  
4.  En la clase `MainWindow`, agregue el controlador de eventos <xref:System.Windows.UIElement.ManipulationStarting> siguiente.  
  
     El evento <xref:System.Windows.UIElement.ManipulationStarting> se produce cuando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detecta que la entrada táctil empieza a manipular un objeto.  El código especifica que la posición de la manipulación debe ser relativa a <xref:System.Windows.Window> estableciendo la propiedad <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  En la clase `MainWindow`, agregue el controlador de eventos <xref:System.Windows.Input.ManipulationDelta> siguiente.  
  
     El evento <xref:System.Windows.Input.ManipulationDelta> se produce cuando la entrada táctil cambia de posición y puede producirse varias veces durante una manipulación.  El evento también se puede producir después de que se haya levantado un dedo.  Por ejemplo, si el usuario arrastra un dedo por una pantalla, el evento <xref:System.Windows.Input.ManipulationDelta> se produce varias veces a medida que el dedo se mueve.  Cuando el usuario levanta un dedo de la pantalla, el evento <xref:System.Windows.Input.ManipulationDelta> sigue produciéndose para simular la inercia.  
  
     El código aplica la propiedad <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> de <xref:System.Windows.Shapes.Rectangle> para moverlo a medida que el usuario mueve la entrada táctil.  También comprueba si <xref:System.Windows.Shapes.Rectangle> está fuera de los límites de <xref:System.Windows.Window> cuando el evento se produce durante la inercia.  Si lo está, la aplicación llama al método <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=fullName> para finalizar la manipulación.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  En la clase `MainWindow`, agregue el controlador de eventos <xref:System.Windows.UIElement.ManipulationInertiaStarting> siguiente.  
  
     El evento <xref:System.Windows.UIElement.ManipulationInertiaStarting> se produce cuando el usuario levanta todos los dedos de la pantalla.  El código establece la velocidad inicial y la desaceleración para el movimiento, expansión y giro del rectángulo.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  Compile y ejecute el proyecto.  
  
     Debe ver que aparece un cuadrado rojo en la ventana.  
  
## Probar la aplicación  
 Para probar la aplicación, intente realizar las manipulaciones siguientes:  Tenga en cuenta que puede realizar más de una de las acciones siguientes al mismo tiempo.  
  
-   Para mover <xref:System.Windows.Shapes.Rectangle>, ponga un dedo en <xref:System.Windows.Shapes.Rectangle> y mueva el dedo por la pantalla.  
  
-   Para cambiar el tamaño de <xref:System.Windows.Shapes.Rectangle>, ponga dos dedos en <xref:System.Windows.Shapes.Rectangle> y acerque o aparte los dedos.  
  
-   Para girar <xref:System.Windows.Shapes.Rectangle>, ponga dos dedos en <xref:System.Windows.Shapes.Rectangle> y gire los dedos uno alrededor del otro.  
  
 Para producir inercia, levante rápidamente los dedos de la pantalla mientras realiza las manipulaciones anteriores.  <xref:System.Windows.Shapes.Rectangle> se seguirá moviendo, cambiando de tamaño o girando durante unos segundos antes de detenerse.  
  
## Vea también  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=fullName>   
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=fullName>