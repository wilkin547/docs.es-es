---
title: '{}Secuencia de escape - Extensión de marcado'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432969"
---
# <a name="-escape-sequence--markup-extension"></a>{}Secuencia de escape / extensión de marcado

Proporciona la secuencia de escape XAML para los valores de atributo. La secuencia de escape permite que los valores subsiguientes del atributo se interpreten como un literal.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a>Uso de elementos de propiedad XAML

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|*literalValue*|Cadena literal que sigue a la secuencia de escape. Normalmente, esta cadena contiene una llave abierta o cercana (o .|

## <a name="remarks"></a>Observaciones

La secuencia{}de escape ( ) se usa para que se pueda usar una llave abierta (-) como un carácter literal en XAML.

Los lectores XAML suelen usar la llave abierta para denotar el punto de entrada de una extensión de marcado; sin embargo, primero comprueban el siguiente carácter para determinar si se trata de una llave de cierre. Sólo cuando las dos{}llaves ( ) son adyacentes, se consideran una secuencia de escape.

Si se encuentra la secuencia de escape, el lector XAML debe procesar el resto de la cadena como una cadena. Sin embargo, si la secuencia de escape se aplica a un miembro que tiene un convertidor de tipos, la cadena podría someterse a la conversión de tipos cuando la interpreta un escritor XAML.

La secuencia de escape no es una extensión de marcado y no está respaldada por una clase. Sin embargo, es una convención que los lectores XAML (incluidos los lectores XAML personalizados) deben respetar.

Una comilla (") no se puede utilizar como secuencia de escape de esta manera. Si necesita establecer una comilla como un valor de propiedad para una propiedad noncontent, utilice la sintaxis del elemento de propiedad y coloque la comilla como una cadena dentro del elemento de propiedad o utilice una entidad de caracteres XML. Para una propiedad de contenido, la comilla puede ser todo el contenido.

La secuencia{}de escape ( ) es frecuentemente necesaria al especificar un tipo XML que debe incluir un calificador de espacio de nombres en una ubicación donde puede aparecer una extensión de marcado XAML. Esta ubicación incluye el inicio de un valor de atributo XAML y en una extensión de marcado inmediatamente después de un signo igual ( . En el ejemplo siguiente se muestran las secuencias de escape de un espacio de nombres XML que aparece al principio de un valor de atributo XAML.

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a>Consulte también

- [Convertidores de tipos y extensiones de marcado para XAML](type-converters-and-markup-extensions.md)
- [Entidades de caracteres XML y XAML](xml-character-entities.md)
