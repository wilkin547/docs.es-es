---
title: Código subyacente y XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 32283d5b81bf92999a97711ded13a8b533ae3028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145350"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Código subyacente y XAML en WPF
<a name="introduction"></a>Código subyacente es un término que se usa para describir el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] código que se une con objetos definidos por marcado, cuando se compila una página. En este tema se describen los requisitos para el código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]subyacente, así como un mecanismo de código en línea alternativo para el código en .  
  
 Este tema contiene las siguientes secciones:  
  
- [Requisitos previos](#Prerequisites)  
  
- [Code-Behind y el lenguaje XAML](#codebehind_and_the_xaml_language)  
  
- [Requisitos de código subyacente, controlador de eventos y clase parcial en WPFWPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Código](#x_Code)  
  
- [Limitaciones de código en línea](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que ha leído la información general de [XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) y tiene algunos conocimientos básicos de la programación CLR y orientada a objetos.  
  
<a name="codebehind_and_the_xaml_language"></a>
## <a name="code-behind-and-the-xaml-language"></a>Code-Behind y el lenguaje XAML  
 El lenguaje XAML incluye características de nivel de lenguaje que permiten asociar archivos de código con archivos de marcado, desde el lado del archivo de marcado. En concreto, el lenguaje XAML define las características de lenguaje [x:Class Directive](../../../desktop-wpf/xaml-services/xclass-directive.md), [x:Subclass Directive](../../../desktop-wpf/xaml-services/xsubclass-directive.md)y [x:ClassModifier Directive](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md). Exactamente cómo se debe generar el código y cómo integrar el marcado y el código, no forma parte de lo que especifica el lenguaje XAML. Se deja en cuenta marcos como WPFWPF para determinar cómo integrar el código, cómo usar XAML en la aplicación y los modelos de programación y las acciones de compilación u otra compatibilidad que todo esto requiere.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Requisitos de código subyacente, controlador de eventos y clase parcial en WPFWPF  
  
- La clase parcial debe derivar del tipo que respalda el elemento raíz.  
  
- Tenga en cuenta que en el comportamiento predeterminado de las acciones de compilación de compilación de marcado, puede dejar la derivación en blanco en la definición de clase parcial en el lado de código subyacente. El resultado compilado asumirá que el tipo de respaldo de la raíz de la página es la base de la clase parcial, incluso si no se especificó. Sin embargo, confiar en este comportamiento no es una práctica recomendada.  
  
- Los controladores de eventos que escriba en el código subyacente deben ser métodos de instancia y no pueden ser métodos estáticos. Estos métodos deben definirse mediante la clase `x:Class`parcial dentro del espacio de nombres CLR identificado por . No puede calificar el nombre de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un controlador de eventos para indicar a un procesador que busque un controlador de eventos para el cableado de eventos en un ámbito de clase diferente.  
  
- El controlador debe coincidir con el delegado para el evento adecuado en el sistema de tipos de respaldo.  
  
- Para el lenguaje Microsoft Visual Basic específicamente, `Handles` puede usar la palabra clave específica del lenguaje para asociar controladores con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]instancias y eventos en la declaración de controlador, en lugar de adjuntar controladores con atributos en . Sin embargo, esta técnica tiene `Handles` algunas limitaciones porque la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] palabra clave no puede admitir todas las características específicas del sistema de eventos, como determinados escenarios de eventos enrutados o eventos adjuntos. Para obtener más información, vea Control de eventos de [Visual Basic y WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>
## <a name="xcode"></a>x:Código  
 [x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) es un elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]de directiva definido en . Un `x:Code` elemento de directiva puede contener código de programación en línea. El código que se define en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] línea puede interactuar con el en la misma página. En el ejemplo siguiente se muestra el código de C- en línea. Observe que el código `x:Code` está dentro del elemento `<CDATA[`y que el código debe estar rodeado por ... `]]>` para escapar del contenido de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] XML, de modo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un procesador (interpretando el esquema o el esquema) no intentará interpretar el contenido literalmente como XML.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>
## <a name="inline-code-limitations"></a>Limitaciones de código en línea  
 Debe considerar evitar o limitar el uso de código en línea. En términos de arquitectura y filosofía de codificación, mantener una separación entre el marcado y el código subyacente mantiene los roles de diseñador y desarrollador mucho más distintos. En un nivel más técnico, el código que se escribe para el código en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] línea puede ser incómodo de escribir, porque siempre se escribe en la clase parcial generada y solo puede usar las asignaciones de espacio de nombres XML predeterminadas. Dado que `using` no puede agregar instrucciones, debe calificar completamente muchas de las llamadas a la API que realice. Las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asignaciones predeterminadas incluyen la mayoría de los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espacios de nombres CLR, pero no todos los que están presentes en los ensamblados; tendrá que calificar completamente las llamadas a tipos y miembros contenidos en los otros espacios de nombres CLR. Tampoco puede definir nada más allá de la clase parcial en el código en línea y todas las entidades de código de usuario a las que haga referencia deben existir como miembro o variable dentro de la clase parcial generada. Otras características de programación específicas del lenguaje, como macros o `#ifdef` contra variables globales o variables de compilación, tampoco están disponibles. Para obtener más información, vea [x:Code Intrinsic XAML Type](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [x:Code (Tipo XAML intrínseco)](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [Compilar una aplicación WPF](../app-development/building-a-wpf-application-wpf.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
