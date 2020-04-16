---
title: Convertidores de tipos y extensiones de marcado para XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converter services
- XAML [XAML Services], value converters
- XAML [XAML Services], markup extension services
- value converters for XAML [XAML Services]
- XAML [XAML Services], service context
ms.assetid: db07a952-05ce-4aa4-b6f9-aac7397d0326
ms.openlocfilehash: bee94b03d4fd6e6f5ef8571e83f554b381dd6582
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432891"
---
# <a name="type-converters-and-markup-extensions-for-xaml"></a>Convertidores de tipos y extensiones de marcado para XAML

Los convertidores de tipos y extensiones de marcado son dos técnicas que los sistemas de tipos XAML y escritores de XAML utilizan para generar componentes de gráfico de objeto. Aunque comparten algunas características, los convertidores de tipos y las extensiones de marcado se representan de forma diferente en una secuencia de nodo XAML. En este conjunto de documentación, en ocasiones nos referimos colectivamente a los convertidores de tipos, las extensiones de marcado y construcciones similares como convertidores de valores.

## <a name="value-converters"></a>Convertidores de valores

En XAML, los convertidores de valores se utilizan para varios escenarios. La lista siguiente muestra los distintos tipos de convertidores de valores en XAML:

- Convertidor de tipos

- Extensión de marcado

- Serializador de valor

- Clase relacionada o clase de compatibilidad que proporciona la lógica para una sintaxis de texto XAML

## <a name="type-converters"></a>Convertidores de tipos

En la definición de servicios XAML de .NET, los convertidores de tipos son clases que derivan de la clase CLR. <xref:System.ComponentModel.TypeConverter> <xref:System.ComponentModel.TypeConverter>es una clase que estaba en .NET antes de que existiera XAML. Su propósito original era admitir ventanas de propiedades y metáforas de edición basadas en texto similares para propiedades IDE. La introducción de XAML <xref:System.ComponentModel.TypeConverter> a .NET usa para convertir una sintaxis de texto (como se encuentra en un valor de atributo o un nodo de valor XAML) en un objeto. <xref:System.ComponentModel.TypeConverter> también se puede utilizar para serializar el valor de un objeto en sintaxis de texto. <xref:System.ComponentModel.TypeConverter>también se usó en implementaciones XAML específicas del marco de trabajo anteriores en Windows Presentation Foundation (WPF) y Windows Communication Foundation (WCF). Para más información sobre <xref:System.ComponentModel.TypeConverter> en XAML, vea [Type Converters for XAML Overview](type-converters-overview.md).

## <a name="markup-extensions"></a>Extensiones de marcado

En la implementación de Servicios XAML de <xref:System.Windows.Markup.MarkupExtension> .NET, las extensiones de marcado son clases que derivan de la clase. Las extensiones de marcado son un concepto se origina con esta forma en el lenguaje XAML. Puede pensar en una extensión de marcado como algo similar a una secuencia de escape extensible que llama a una clase de servicio para que proporcione su lógica. En términos de marcado, los procesadores de XAML reconocen universalmente una extensión de marcado mediante una secuencia de texto que comienza con una llave de apertura ({) en una cadena de texto.

Las extensiones de marcado difieren de los convertidores de tipos. Los convertidores de tipos se suelen asociados a tipos o miembros. Se invocan cuando la creación de un gráfico de objeto o una serialización encuentran sintaxis de texto que está asociada a esas entidades.

Las extensiones de marcado están asociadas con una sola clase de servicio de compatibilidad, pero se pueden aplicar para cualquier valor de miembro. (Sin embargo, puede implementar la extensión de marcado para restringir deliberadamente su uso a determinados miembros o tipos de destino, mediante el uso de contexto de servicio.) Las extensiones de marcado pueden invalidar una asociación de convertidor de tipos. También puede utilizarlas para especificar un valor de atributo para los miembros que, de otra forma, no admitirían una sintaxis de texto.

Para más información sobre el patrón de implementación de extensión de marcado para XAML, vea [Markup Extensions for XAML Overview](markup-extensions-overview.md).

## <a name="value-serializers"></a>Serializadores de valor

Un <xref:System.Windows.Markup.ValueSerializer> es un convertidor de tipos especializado que está optimiza para convertir un objeto en una cadena. Un <xref:System.Windows.Markup.ValueSerializer> para XAML podría no implementar el método `ConvertFrom` en absoluto. Una implementación de <xref:System.Windows.Markup.ValueSerializer> obtiene los servicios de tal manera que es como una implementación de <xref:System.ComponentModel.TypeConverter> . Los métodos virtuales proporcionan un parámetro `context` de entrada. El parámetro `context` es de tipo <xref:System.Windows.Markup.IValueSerializerContext>, que hereda de la interfaz <xref:System.IServiceProvider> y tiene un método <xref:System.IServiceProvider.GetService%2A> .

En el sistema de tipos XAML y para las implementaciones de sistema de escritura XAML que usan el procesamiento de bucle de nodo XAML para la serialización, un convertidor de valores que está asociado a un tipo o miembro se notifica mediante su propia propiedad <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> . El significado para los sistemas de escritura XAML que realizan la serialización es que, si existen <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> y <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> , se debe usar el convertidor de tipos para la ruta de acceso de carga y se debe usar el serializador de valor para la ruta de acceso de guardado. Si <xref:System.Xaml.XamlType.TypeConverter%2A?displayProperty=nameWithType> existe pero <xref:System.Xaml.XamlType.ValueSerializer%2A?displayProperty=nameWithType> es `null`, el convertidor de tipos también se utiliza para la ruta de acceso de guardado.

## <a name="other-value-converters"></a>Otros convertidores de valores

Un convertidor de valores es extensible más allá de los modelos concretos de un convertidor de tipos o una extensión de marcado. Sin embargo, esta personalización también requeriría la redefinición del sistema de tipos XAML según lo proporcionado por los servicios XAML de .NET. El sistema de tipos XAML existente tiene representaciones y sistemas de notificación para convertidores de tipos, extensiones de marcado y serializadores de valor, pero no para formas personalizadas de conversión de valor. Si desea crear convertidores de valores personalizados, use el tipo <xref:System.Xaml.Schema.XamlValueConverter%601> .

## <a name="type-converters-and-markup-extensions-in-combination"></a>Convertidores de tipos y extensiones de marcado en combinación

Las extensiones de marcado y los convertidores de tipos se utilizan para diferentes situaciones en XAML. Aunque el contexto está disponible para los usos de la extensión de marcado, en las implementaciones de extensión de marcado no se suele comprobar el comportamiento de conversión de tipos de aquellas propiedades en las que una extensión de marcado proporciona un valor. En otras palabras, aunque una extensión de marcado devuelva una cadena de texto como salida de `ProvideValue` , no se invoca el comportamiento de conversión de tipos en esa cadena al aplicarla a una propiedad determinada o a un tipo de valor de propiedad determinado. Por lo general, el propósito de una extensión de marcado es procesar una cadena y devolver un objeto sin ningún convertidor de tipos implicado.

## <a name="service-context-for-a-value-converter"></a>Contexto de servicio para un convertidor de valores

Cuando se implementa un convertidor de valores, suele ser necesario acceder a un contexto en el que se aplica el convertidor de valores. Este contexto se conoce como el contexto de servicio. El contexto de servicio puede incluir información como el contexto de esquema XAML activo, acceso al sistema de asignación de tipos que proporcionan el contexto de esquema XAML y el escritor de objetos XAML, etc. Para más información sobre los contextos de servicio disponibles para un convertidor de valores y cómo acceder a los servicios que un contexto de servicio puede proporcionar, consulte [Service Contexts Available to Type Converters and Markup Extensions](service-contexts-with-type-converters-and-markup-extensions.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Markup.MarkupExtension>
- <xref:System.Xaml.XamlObjectWriter>
- [Información general sobre las extensiones de marcado para el lenguaje XAML](markup-extensions-overview.md)
- [Información general sobre los convertidores de tipos para XAML](type-converters-overview.md)
- [Contextos de servicio disponibles para los convertidores de tipos y las extensiones de marcado](service-contexts-with-type-converters-and-markup-extensions.md)
