---
title: "Introducción a las entradas manuscritas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74227ebe815e971087569ff39ac0a3479c1b0d14
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="getting-started-with-ink"></a>Introducción a las entradas manuscritas
La incorporación de entrada de lápiz digital en sus aplicaciones es más fácil que nunca. Tinta ha evolucionado ante un corolario al método COM y formularios Windows Forms de la programación para lograr una integración completa en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. No es necesario instalar ningún SDK independiente ni bibliotecas en tiempo de ejecución.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para usar los ejemplos siguientes, primero debe instalar Microsoft Visual Studio 2005 y [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. También debe saber cómo escribir aplicaciones para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para obtener más información acerca de cómo empezar a usar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="quick-start"></a>Inicio rápido  
 Esta sección le ayudará a escribir una sencilla [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación que recopila tinta.  
  
 Si aún no lo ha hecho, instale Microsoft Visual Studio 2005 y [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones normalmente deben compilarse antes de verlos, aunque estas constan únicamente de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Sin embargo, el [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] incluye una aplicación, XamlPad, diseñada para acelerar el proceso de implementar un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-según la interfaz de usuario. Puede utilizar esa aplicación para ver y aprovechar los primeros ejemplos de este documento. El proceso de creación de compila aplicaciones de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se trata más adelante en este documento.  
  
 Para iniciar XAMLPad, haga clic en el **iniciar** menú, elija **todos los programas**, seleccione **Microsoft Windows SDK**, seleccione **herramientas**y haga clic en **XAMLPad**. En el panel de representación, XAMLPad representa el código XAML escrito en el panel de código. Puede editar el código XAML y los cambios aparecen inmediatamente en el panel de representación.  
  
#### <a name="got-ink"></a>¿Se obtuvo tinta?  
 Para iniciar su primer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación que admita tinta:  
  
1.  Open Microsoft Visual Studio 2005  
  
2.  Crear un nuevo **aplicación de Windows (WPF)**  
  
3.  Tipo de `<InkCanvas/>` entre el `<Grid>` etiquetas  
  
4.  Presione **F5** para iniciar la aplicación en el depurador  
  
5.  Con un lápiz o un mouse, escribir **Hola a todos** en la ventana  
  
 Ha escrito el equivalente de tinta de una aplicación "hello world" con tan sólo 12 pulsaciones de teclas.  
  
#### <a name="spice-up-your-application"></a>Animar la aplicación  
 Vamos a aprovechar las ventajas de algunas características de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Reemplace todo entre la apertura \<Ventana > y cerrar \</Window > etiquetas con el código siguiente para obtener un fondo de pincel de degradado en la superficie de escritura a mano.  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a>Uso de animación  
 Para divertirse, vamos a animar los colores del pincel de degradado. Agregue el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] después del cierre `</InkCanvas>` etiqueta pero antes del cierre `</Page>` etiqueta.  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a>Agrega un código detrás de XAML  
 Aunque XAML facilita diseñar la interfaz de usuario, cualquier aplicación del mundo real debe agregar código para controlar los eventos. Este es un ejemplo sencillo que para acercar la tinta en respuesta a un menú contextual de un mouse:  
  
 Establecer el `MouseRightButtonUp` controlador en su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 En el Explorador de soluciones de Visual Studio, expanda Windows1.xaml y abra el archivo de código subyacente, Window1.xaml.cs o Window1.xaml.vb si está utilizando Visual Basic. Agregue el siguiente código de controlador de eventos:  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 Ahora, ejecute la aplicación. Agregar algunas entradas manuscritas y, a continuación, haga clic en con el mouse o realizar un equivalente de presionar y mantener presionado con un lápiz.  
  
#### <a name="using-procedural-code-instead-of-xaml"></a>Usando código de procedimiento en lugar de XAML  
 Puede tener acceso a todas las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características del código de procedimiento. Este es una "tinta aplicación Hola a todos" para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que no usa ningún [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en absoluto. Pegue el código siguiente en una aplicación de consola vacía en Visual Studio. Agregue referencias a los ensamblados de WindowsBase, PresentationCore y PresentationFramework y compile la aplicación presionando **F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Entrada de lápiz digital](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [Recopilación de entradas de lápiz](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [Reconocimiento de escritura a mano](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [Almacenamiento de entradas de lápiz](../../../../docs/framework/wpf/advanced/storing-ink.md)
