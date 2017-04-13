---
title: "C&#243;digo subyacente y XAML en WPF | Microsoft Docs"
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
  - "archivos de código subyacente, XAML"
  - "XAML, código subyacente"
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;digo subyacente y XAML en WPF
<a name="introduction"></a> Código subyacente es un término empleado para describir el código unido con objetos definidos por marcado cuando una página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se compila por marcado.  En este tema se describen los requisitos para el código subyacente, así como un mecanismo de código insertado alternativo para el código en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
-   [Requisitos previos](#Prerequisites)  
  
-   [Código subyacente y el lenguaje XAML](#codebehind_and_the_xaml_language)  
  
-   [Requisitos del código subyacente, los controladores de eventos y las clases parciales en WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [x:Code](#x_Code)  
  
-   [Limitaciones del código insertado](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## Requisitos previos  
 En este tema se da por hecho que ha leído [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) y que cuenta con conocimientos básicos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y de programación orientada a objetos.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## Código subyacente y el lenguaje XAML  
 El lenguaje XAML incluye características de nivel de lenguaje que permiten asociar archivos de código a archivos de marcado, desde el lado del archivo de marcado.  En concreto, el lenguaje XAML define las características de lenguaje [x:Class \(Directiva\)](../../../../docs/framework/xaml-services/x-class-directive.md), [x:Subclass \(Directiva\)](../../../../docs/framework/xaml-services/x-subclass-directive.md) y [x:ClassModifier \(Directiva\)](../../../../docs/framework/xaml-services/x-classmodifier-directive.md).  La forma exacta en que se debe generar el código, y cómo integrar el marcado y el código, no forma parte de lo que especifica el lenguaje XAML.  Son los marcos como WPF los que determinan cómo integrar el código, cómo usar XAML en los modelos de programación y aplicaciones, y las acciones de compilación u otras tareas que sean necesarias para todo ello.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## Requisitos del código subyacente, los controladores de eventos y las clases parciales en WPF  
  
-   La clase parcial debe derivarse del tipo que respalda al elemento raíz.  
  
-   Tenga en cuenta que según el comportamiento predeterminado de las acciones de compilación por marcado, puede dejar en blanco la derivación en la definición de clase parcial en el lado del código subyacente.  El resultado compilado supondrá que el tipo de respaldo de la raíz de la página es la base para la clase parcial, aunque no se especifique.  Sin embargo, no se recomienda confiar en este comportamiento.  
  
-   Los controladores de eventos que escribe en el código subyacente deben ser métodos de instancia y no pueden ser métodos estáticos.  La clase parcial debe definir estos métodos dentro del espacio de nombres CLR identificado por `x:Class`.  No se puede calificar el nombre de un controlador de eventos para indicar a un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que lo busque para un evento que se desencadena en otro ámbito de clase.  
  
-   El controlador debe coincidir con el delegado para el evento adecuado en el sistema de tipos de respaldo.  
  
-   En particular para el lenguaje [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)], puede utilizar la palabra clave `Handles` específica del lenguaje para asociar los controladores a instancias y eventos en la declaración del controlador, en lugar de asociar los controladores a los atributos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Sin embargo, esta técnica tiene algunas limitaciones porque la palabra clave `Handles` no puede admitir todas las características específicas del sistema de eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como algunos escenarios de eventos enrutados o eventos adjuntos.  Para obtener información detallada, vea [Control de eventos en Visual Basic y WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## x:Code  
 [x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) es un elemento de directiva definido en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un elemento de directiva `x:Code` puede contener código de programación alineado.  El código insertado que se define puede interactuar con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en la misma página.  En el siguiente ejemplo se ilustra el código insertado [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)].  Observe que el código está dentro del elemento `x:Code` y que el código debe estar entre `<CDATA[`...`]]>`, una secuencia de escape para el contenido en [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], de manera que un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(que interprete el esquema de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o el esquema de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\) no intente interpretar literalmente el contenido como [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## Limitaciones del código insertado  
 Debe evitar o limitar el uso de código alineado.  Por lo que se refiere a la arquitectura y la filosofía de codificación, mantener una separación entre el marcado y el código subyacentes permite diferenciar mucho mejor los roles de programador y diseñador.  En un plano más técnico, la escritura de código alineado puede resultar complicada, ya que siempre se escribe en la clase parcial generada de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], lo que solo permite usar las asignaciones de espacio de nombres XML predeterminadas.  Al no poder agregar instrucciones `using`, debe calificar totalmente muchas de las llamadas a las [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] que se realizan.  Las asignaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminadas incluyen la mayoría de los espacios de nombres [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que se encuentran en los ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], pero no todos; esto le obligará a calificar totalmente las llamadas a los tipos y miembros contenidos dentro de los demás espacios de nombres CLR.  En el código alineado tampoco puede definir nada que no sea la clase parcial. Además, todas las entidades de código de usuario a las que haga referencia deben existir como un miembro o una variable dentro de la clase parcial generada.  Tampoco están disponibles otras características de programación específicas del lenguaje, tales como las macros o las `#ifdef` para variables globales o de compilación.  Para obtener más información, consulte [x:Code \(Tipo XAML intrínseco\)](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md).  
  
## Vea también  
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [x:Code \(Tipo XAML intrínseco\)](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)   
 [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)