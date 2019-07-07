---
title: Código subyacente y XAML en WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 6a47f5a93cb161c9a87df25403cc86247619cd81
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610532"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Código subyacente y XAML en WPF
<a name="introduction"></a> Código subyacente es un término que se usa para describir el código que se une con objetos definidos por marcado, cuando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página está compilado por marcado. En este tema se describe los requisitos para el código subyacente, así como un mecanismo de código insertado alternativo para el código en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
- [Requisitos previos](#Prerequisites)  
  
- [Código subyacente y el lenguaje XAML](#codebehind_and_the_xaml_language)  
  
- [Código subyacente, controlador de eventos y los requisitos de la clase parcial de WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [Limitaciones del código insertado](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se da por supuesto que ha leído el [información general sobre XAML (WPF)](xaml-overview-wpf.md) y tiene conocimientos básicos de la [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y la programación orientada a objetos.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Código subyacente y el lenguaje XAML  
 El lenguaje XAML incluye características de nivel de lenguaje que permiten asociar archivos de código con archivos de marcado, desde el lado del archivo de marcado. En concreto, el lenguaje XAML define las características del lenguaje [x: Class directiva](../../xaml-services/x-class-directive.md), [x: Subclass (directiva)](../../xaml-services/x-subclass-directive.md), y [x: ClassModifier Directive](../../xaml-services/x-classmodifier-directive.md). Exactamente cómo se debe generar el código y cómo integrar el marcado y código, no forma parte de lo que especifica el lenguaje XAML. Se deja de marcos como WPF para determinar cómo integrar el código, cómo usar XAML en la aplicación y los modelos de programación y la compilación acciones u otros admiten que todo esto requiere.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Código subyacente, controlador de eventos y los requisitos de la clase parcial de WPF  
  
- La clase parcial debe derivarse el tipo que respalda el elemento raíz.  
  
- Tenga en cuenta que en el comportamiento predeterminado de las acciones de compilación marcado, puede dejar la derivación en blanco en la definición de clase parcial en el lado de código subyacente. El resultado compilado supondrá que tipo de respaldo de la raíz de la página para ser la base de la clase parcial, incluso si no ha especificado. Sin embargo, confiar en este comportamiento no es una práctica recomendada.  
  
- Los controladores de eventos que se escribe en el código subyacente deben ser métodos de instancia y no pueden ser métodos estáticos. Estos métodos deben definirse mediante la clase parcial en el espacio de nombres CLR identificado por `x:Class`. No se puede calificar el nombre de un controlador de eventos para indicar a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador para buscar un controlador de eventos para la conexión de eventos en un ámbito de clase diferente.  
  
- El controlador debe coincidir con el delegado para el evento correspondiente en el sistema de tipos de respaldo.  
  
- Para el idioma de Microsoft Visual Basic en concreto, puede usar específico del lenguaje `Handles` palabra clave para asociar controladores a instancias y eventos en la declaración del controlador, en lugar de asociar controladores con atributos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Sin embargo, esta técnica tiene algunas limitaciones porque la `Handles` palabra clave no es compatible con todas las características específicas de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de eventos, por ejemplo, determinados enruta los escenarios de eventos o eventos adjuntos. Para obtener más información, consulte [Visual Basic y control de eventos de WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x:Code  
 [x: Code](../../xaml-services/x-code-intrinsic-xaml-type.md) se define un elemento de la directiva en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un `x:Code` directiva elemento puede contener código de programación en línea. El código que se definen en línea puede interactuar con el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en la misma página. El ejemplo siguiente muestra código C# en línea. Tenga en cuenta que el código está dentro de la `x:Code` elemento y que el código debe estar entrecomillado `<CDATA[`... `]]>` para anular el contenido para [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], de modo que un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador (interpretar cualquiera el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esquema o la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esquema) no intenta interpretar el contenido literalmente como [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Limitaciones del código insertado  
 Debe considerar el evitar o limitar el uso de código en línea. En términos de arquitectura y la filosofía de codificación, mantener una separación entre el marcado y código subyacente mantiene las funciones de diseñador y desarrollador distintos mucho más. En un nivel más técnico, el código que se escribe para el código insertado puede ser incómodo de escribir, porque siempre se escriben en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] clase parcial generada y solo se pueden usar las asignaciones de espacio de nombres XML predeterminado. Dado que no se puede agregar `using` instrucciones, debe calificar totalmente muchas de las llamadas de API que realice. El valor predeterminado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asignaciones incluyen más pero no todos los [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] espacios de nombres que se encuentran en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ensamblados; tendrá que completar llamadas a tipos y miembros contenidos en los otros espacios de nombres CLR. También se no se puede definir cualquier cosa más allá de la clase parcial en el código en línea, y todas las entidades de código de usuario que se hace referencia deben existir como un miembro o una variable dentro de la clase parcial generada. Otras características programación específica del lenguaje, como las macros o `#ifdef` frente a las variables globales o las variables de compilación, tampoco están disponibles. Para obtener más información, consulte [x: Code tipo XAML intrínseco](../../xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [x:Code (Tipo XAML intrínseco)](../../xaml-services/x-code-intrinsic-xaml-type.md)
- [Compilar una aplicación de WPF](../app-development/building-a-wpf-application-wpf.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
