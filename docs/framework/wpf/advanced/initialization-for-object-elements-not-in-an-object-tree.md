---
title: "Inicializaci&#243;n de elementos de objeto no incluidos en un &#225;rbol de objetos | Microsoft Docs"
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
  - "elementos, inicializar"
  - "inicializar elementos"
  - "árbol lógico"
  - "árbol visual"
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Inicializaci&#243;n de elementos de objeto no incluidos en un &#225;rbol de objetos
Algunos aspectos de la inicialización de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se difieren a los procesos que suelen basarse en que ese elemento esté conectado al [árbol lógico](GTMT) o al [árbol visual](GTMT).  En este tema se describen las operaciones que pueden ser necesarias para inicializar un elemento que no está conectado a ninguno de estos árboles.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## Elementos y el árbol lógico  
 Al crear una instancia de una clase [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] en código, debe tener en cuenta que hay varios aspectos de la inicialización de objetos para una clase de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] que deliberadamente no forman parte del código que se ejecuta al llamar al constructor de la clase.  Concretamente para una clase de control, el constructor no define la mayoría de la representación visual de ese control.  En cambio, la representación visual la define la plantilla del control.  La plantilla puede proceder de varios orígenes, pero lo más habitual es que se obtenga de los estilos de tema.  En la práctica, el enlace de las plantillas se efectúa en tiempo de ejecución; la plantilla necesaria no se asocia al control correspondiente hasta que éste está para el diseño.  Y el control no está listo para el diseño hasta que se asocia a un árbol lógico conectado a una superficie de la representación en la raíz.  Este elemento del nivel de la raíz es el que inicia la representación de todos sus elementos secundarios definidos en el árbol lógico.  
  
 El árbol visual también participa en este proceso.  Las instancias de los elementos que forman parte del árbol visual a través de las plantillas tampoco se crean totalmente hasta que se conectan.  
  
 Como consecuencia de este comportamiento, algunas operaciones que se basan en las características visuales completadas de un elemento requieren operaciones adicionales.  Un ejemplo de ello es el caso en que se intenta obtener las características visuales de una clase que se construyó pero todavía no está asociada a un árbol.  Por ejemplo, si desea llamar a <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> para <xref:System.Windows.Media.Imaging.RenderTargetBitmap> y el objeto visual que se pasa es un elemento no conectado a un árbol, ese elemento no estará completo visualmente hasta que se completen las operaciones de inicialización adicionales.  
  
### Utilizar BeginInit y EndInit para inicializar el elemento  
 Varias clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementan la interfaz <xref:System.ComponentModel.ISupportInitialize>.  Los métodos <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> y <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> de la interfaz se utilizan para indicar una zona del código que contiene las operaciones de inicialización \(tales como establecer los valores de propiedad que afectan a la representación\).  Una vez se llama a <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> en la secuencia, el sistema del diseño puede procesar el elemento y comenzar a buscar un estilo implícito.  
  
 Si el elemento cuyas propiedades se establecen es una clase derivada de <xref:System.Windows.FrameworkElement> o de <xref:System.Windows.FrameworkContentElement>, entonces puede llamar a las versiones de las clases <xref:System.Windows.FrameworkElement.BeginInit%2A> y <xref:System.Windows.FrameworkElement.EndInit%2A>, en lugar de efectuar una conversión a <xref:System.ComponentModel.ISupportInitialize>.  
  
### Código de ejemplo  
 A continuación se muestra un ejemplo de código para una aplicación de consola que utiliza [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de representación y el método <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=fullName> de un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico para mostrar la posición correcta de <xref:System.Windows.FrameworkElement.BeginInit%2A> y <xref:System.Windows.FrameworkElement.EndInit%2A> en torno a otras llamadas de [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] que ajustan las propiedades que afectan a la representación.  
  
 En el ejemplo sólo se muestra la función principal.  Las funciones `Rasterize` y `Save` \(no mostradas\) son funciones de utilidad que se encargan del procesamiento de imágenes y de E\/S.  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## Vea también  
 [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)   
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)