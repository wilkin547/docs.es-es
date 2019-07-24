---
title: Código subyacente y XAML en WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: acd8c9ff0a4ff718dba272958a3e63820bcf1354
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401611"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Código subyacente y XAML en WPF
<a name="introduction"></a>El código subyacente es un término que se usa para describir el código que se une con objetos definidos por el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cuando una página está compilada por marcado. En este tema se describen los requisitos para el código subyacente, así como un mecanismo de código en línea [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]alternativo para el código de.  
  
 Este tema contiene las siguientes secciones:  
  
- [Requisitos previos](#Prerequisites)  
  
- [Código subyacente y lenguaje XAML](#codebehind_and_the_xaml_language)  
  
- [Código subyacente, controladores de eventos y requisitos de clase parcial en WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [Limitaciones de código en línea](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se da por supuesto que ha leído la [información general de XAML (WPF)](xaml-overview-wpf.md) y tiene conocimientos básicos de CLR y la programación orientada a objetos.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Código subyacente y lenguaje XAML  
 El lenguaje XAML incluye características de nivel de lenguaje que permiten asociar archivos de código con archivos de marcado, desde el lado del archivo de marcado. En concreto, el lenguaje XAML define las características de lenguaje [X:Class Directive](../../xaml-services/x-class-directive.md), la [Directiva X:Subclass](../../xaml-services/x-subclass-directive.md)y la [Directiva x:ClassModifier (](../../xaml-services/x-classmodifier-directive.md). Exactamente cómo se debe generar el código y cómo integrar el marcado y el código, no es parte de lo que especifica el lenguaje XAML. Se deja en marcos como WPF para determinar cómo integrar el código, cómo usar XAML en los modelos de aplicación y programación, y las acciones de compilación u otra compatibilidad que todo esto requiere.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Código subyacente, controladores de eventos y requisitos de clase parcial en WPF  
  
- La clase parcial debe derivar del tipo que respalda el elemento raíz.  
  
- Tenga en cuenta que en el comportamiento predeterminado de las acciones de compilación de la compilación de marcado, puede dejar la derivación en blanco en la definición de clase parcial en el lado del código subyacente. El resultado compilado asumirá que el tipo de respaldo de la raíz de la página es la base para la clase parcial, aunque no se haya especificado. Sin embargo, no se recomienda confiar en este comportamiento.  
  
- Los controladores de eventos que escriba en el código subyacente deben ser métodos de instancia y no pueden ser métodos estáticos. Estos métodos deben definirse mediante la clase parcial dentro del espacio de nombres CLR `x:Class`identificado por. No se puede calificar el nombre de un controlador de eventos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para indicar a un procesador que busque un controlador de eventos para la conexión de eventos en un ámbito de clase diferente.  
  
- El controlador debe coincidir con el delegado para el evento adecuado en el sistema de tipos de respaldo.  
  
- Para el lenguaje Microsoft Visual Basic específicamente, puede usar la palabra clave específica `Handles` del lenguaje para asociar controladores a instancias y eventos en la declaración del controlador, en lugar de adjuntar controladores con atributos en. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Sin embargo, esta técnica tiene algunas limitaciones, ya `Handles` que la palabra clave no admite todas las características específicas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del sistema de eventos, como ciertos escenarios de eventos enrutados o eventos adjuntos. Para obtener más información, vea [control de eventos de Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x:Code  
 [x:Code](../../xaml-services/x-code-intrinsic-xaml-type.md) es un elemento de directiva definido [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]en. Un `x:Code` elemento de Directiva puede contener código de programación en línea. El código definido [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en línea puede interactuar con en la misma página. En el ejemplo siguiente se muestra el C# código en línea. Observe que el código está dentro del `x:Code` elemento y que el código debe estar rodeado por `<CDATA[`... [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para escapar el contenido de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], de modo que un procesador (que interprete el esquema o el esquema) no intente interpretar el contenido literalmente como. `]]>`  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Limitaciones de código en línea  
 Considere la posibilidad de evitar o limitar el uso de código en línea. En lo que se refiere a la arquitectura y la filosofía de codificación, mantener una separación entre el marcado y el código subyacente mantiene el diseñador y los roles de desarrollador mucho más distintos. En un nivel más técnico, el código que se escribe para el código en línea puede resultar complicado de escribir, porque siempre se escribe en la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] clase parcial generada y solo puede usar las asignaciones de espacio de nombres XML predeterminadas. Dado que no puede `using` agregar instrucciones, debe calificar totalmente muchas de las llamadas API que realice. Entre las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asignaciones predeterminadas se encuentran la mayoría de los espacios de nombres CLR que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se encuentran en los ensamblados, pero no todos ellos; tendrá que calificar totalmente las llamadas a los tipos y miembros incluidos en los otros espacios de nombres CLR. Tampoco se puede definir nada más allá de la clase parcial en el código insertado y todas las entidades de código de usuario a las que se hace referencia deben existir como miembro o variable dentro de la clase parcial generada. Otras características de programación específicas del lenguaje, como macros `#ifdef` o variables globales o variables de compilación, tampoco están disponibles. Para obtener más información, vea [tipo XAML intrínseco de x:Code](../../xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [x:Code (Tipo XAML intrínseco)](../../xaml-services/x-code-intrinsic-xaml-type.md)
- [Compilar una aplicación de WPF](../app-development/building-a-wpf-application-wpf.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
