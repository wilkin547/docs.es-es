---
title: "Introducci&#243;n a las entradas manuscritas | Microsoft Docs"
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
  - "animación, colores del pincel de degradado"
  - "pinceles, animar los colores de"
  - "pincel de degradado, animar los colores de"
  - "código de procedimientos en lugar de XAML"
  - "XAML, código de procedimientos en lugar de"
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Introducci&#243;n a las entradas manuscritas
Incorporar las entradas de lápiz digitales a sus aplicaciones es más fácil que nunca.  Las entradas de lápiz han evolucionado desde ser una consecuencia natural del método de programación de COM y de formularios Windows Forms hasta lograr la integración plena en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  No es necesario instalar ningún SDK independiente ni bibliotecas en tiempo de ejecución.  
  
## Requisitos previos  
 Para utilizar los ejemplos siguientes, debe instalar primero Microsoft Visual Studio 2005 y [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].  También debe comprender la escritura de aplicaciones para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información acerca de cómo empezar con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Tutorial  
 Esta sección le ayuda a escribir una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sencilla que recopila entradas de lápiz.  
  
 Si aún no lo ha hecho, instale Microsoft Visual Studio 2005 y [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].  Normalmente, es necesario compilar las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para poder verlas, aunque consistan en su totalidad en código [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Sin embargo, [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] incluye una aplicación, XamlPad, diseñada para acelerar el proceso de implementar una interfaz de usuario basada en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Puede utilizar esa aplicación para ver y aprovechar los primeros ejemplos de este documento.  El proceso de crear aplicaciones compiladas a partir de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se aborda más adelante en este documento.  
  
 Para iniciar XAMLPad, haga clic en el menú **Inicio**, seleccione **Todos los programas**, **Microsoft Windows SDK**, **Herramientas** y haga clic en **XAMLPad**.  En el panel de representación, XAMLPad representa el código XAML escrito en el panel de código.  Puede editar el código XAML; los cambios aparecerán inmediatamente en el panel de representación.  
  
#### ¿Necesita entradas de lápiz?  
 Para iniciar su primera aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que admite las entradas de lápiz:  
  
1.  Abra Microsoft Visual Studio 2005.  
  
2.  Cree una nueva **aplicación para Windows \(WPF\)**.  
  
3.  Escriba `<InkCanvas/>` entre las etiquetas `<Grid>`.  
  
4.  Presione **F5** para iniciar la aplicación en el depurador.  
  
5.  Mediante un lápiz óptico o con el mouse, escriba hello world \(hola a todos\) en la ventana.  
  
 ¡Ha escrito el equivalente de entrada de lápiz de una aplicación "Hello World" con tan sólo 12 pulsaciones de tecla\!  
  
#### Mejorar la aplicación  
 Ahora, vamos a aprovechar algunas características del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Reemplace todo lo que aparece entre las etiquetas \<Window\> de apertura y \<\/Window\> de cierre con el marcado siguiente, para obtener un fondo de pincel de degradado en la superficie de escritura a mano.  
  
 [!code-xml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### Usar la animación  
 Para que sea más divertido, vamos a animar los colores del pincel de degradado.  Agregue el código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] siguiente después de la etiqueta `</InkCanvas>` de cierre, pero antes de la etiqueta `</Page>` de cierre.  
  
 [!code-xml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### Agregar código subyacente al código XAML  
 Aunque XAML facilita en gran medida el diseño de la interfaz de usuario, es preciso agregar código a las aplicaciones reales para que puedan administrar los eventos.  A continuación se muestra un ejemplo sencillo que acerca las entradas de lápiz en respuesta a un clic con el botón secundario de un mouse:  
  
 Establezca el controlador `MouseRightButtonUp` en el código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 En el Explorador de soluciones de Visual Studio, expanda Windows1.xaml y abra el archivo de código subyacente, Window1.xaml.cs o Window1.xaml.vb si usa Visual Basic.  Agregue el código de controlador de eventos siguiente:  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 Ahora, ejecute la aplicación.  Agregue una entrada de lápiz y, a continuación, haga clic con el botón secundario del mouse o realice la acción equivalente de presionar y mantener presionado con un lápiz óptico.  
  
#### Usar código de procedimientos en lugar de XAML  
 Puede tener acceso a todas las características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a partir del código de procedimientos.  A continuación se muestra una aplicación "Hello Ink World" \(Hola a todos los que realizan entradas de lápiz\) para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que no usa ningún código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Pegue el código siguiente en una aplicación de consola vacía en Visual Studio.  Agregue referencias a los ensamblados PresentationCore, PresentationFramework y WindowsBase. A continuación, presione **F5** para compilar la aplicación:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## Vea también  
 [Entrada manuscrita digital](../../../../docs/framework/wpf/advanced/digital-ink.md)   
 [Recopilación de entradas manuscritas](../../../../docs/framework/wpf/advanced/collecting-ink.md)   
 [Reconocimiento de entradas manuscritas](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)   
 [Almacenar entradas manuscritas](../../../../docs/framework/wpf/advanced/storing-ink.md)