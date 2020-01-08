---
title: Documentación XML
description: Obtenga información sobre la F# compatibilidad de para generar documentación a partir de comentarios.
ms.date: 05/16/2016
ms.openlocfilehash: 0a87915c361fc88f0c05264e1c17278fd656a167
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344684"
---
# <a name="xml-documentation"></a>Documentación XML

Puede generar documentación a partir de los comentarios de código de barra diagonal triple (/ F#//) en. Los comentarios XML pueden preceder a las declaraciones de los archivos de código (. FS) o de firma (. FSI).

## <a name="generating-documentation-from-comments"></a>Generación de documentación a partir de comentarios

La compatibilidad con F# para generar documentación a partir de comentarios es la misma que en otros lenguajes .NET Framework. Como en otros lenguajes .NET Framework, la [opción del compilador-doc](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) le permite generar un archivo XML que contiene información que puede convertir en documentación mediante una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB). La documentación que se genera mediante herramientas diseñadas para su uso con ensamblados escritos en otros lenguajes .NET Framework generalmente produce una vista de las API que se basa en la forma compilada de F# construcciones. A menos que las F#herramientas admitan específicamente, la documentación generada por F# estas herramientas no coincide con la vista de una API.

Para obtener más información sobre cómo generar documentación a partir de XML, vea [comentarios &#40;de&#35; documentación XML&#41;guía de programación de C](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Etiquetas recomendadas

Hay dos maneras de escribir comentarios de documentación XML. Uno consiste simplemente en escribir la documentación directamente en un Comentario de barra diagonal triple, sin usar etiquetas XML. Si lo hace, se toma todo el texto del comentario como la documentación de Resumen de la construcción de código que sigue inmediatamente. Utilice este método cuando desee escribir solo un breve resumen de cada construcción. El otro método es usar etiquetas XML para proporcionar documentación más estructurada. El segundo método permite especificar notas independientes para un breve resumen, comentarios adicionales, documentación para cada parámetro y parámetro de tipo y excepciones que se producen, y una descripción del valor devuelto. En la tabla siguiente se describen las etiquetas XML que F# se reconocen en los comentarios de código XML.

|Sintaxis de etiquetas|Descripción|
|----------|-----------|
|**\<c\>** _text_ **\</c\>**|Especifica que el *texto* es código. Los generadores de documentación pueden usar esta etiqueta para mostrar texto en una fuente que sea adecuada para el código.|
|**\<summary\>** _text_ **\</Summary\>**|Especifica que el *texto* es una breve descripción del elemento de programa. La descripción suele ser una o dos oraciones.|
|**\<remarks\>** _text_ **\</remarks\>**|Especifica que el *texto* contiene información adicional sobre el elemento de programa.|
|**\<param name = "** _Name_ **"\>** _Description_ **\</param Returns\>**|Especifica el nombre y la descripción de un parámetro de función o método.|
|**\<typeparam name = "** _Name_ **"\>** _Description_ **\</typeparam\>**|Especifica el nombre y la descripción de un parámetro de tipo.|
|**\<returns\>** _text_ **\</returns\>**|Especifica que el *texto* describe el valor devuelto de una función o un método.|
|**\<Exception CREF = "** _tipo_ **"\>** _Descripción_ **\</Exception\>**|Especifica el tipo de excepción que se puede generar y las circunstancias en las que se produce.|
|**\<vea CREF = "** _referencia_ **"\>** _texto_ **\</See\>**|Especifica un vínculo insertado a otro elemento de programa. La *referencia* es el nombre tal y como aparece en el archivo de documentación XML. El *texto* es el texto que se muestra en el vínculo.|
|**\<seeAlso CREF = "** _referencia_ **"/\>**|Especifica un vínculo ver también a la documentación de otro tipo. La *referencia* es el nombre tal y como aparece en el archivo de documentación XML. Vea también los vínculos normalmente aparecen en la parte inferior de una página de documentación.|
|**\<para\>** _text_ **\</para\>**|Especifica un párrafo de texto. Se usa para separar texto dentro de la etiqueta **comentarios** .|

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

A continuación se encuentra un Comentario de documentación XML típico en un archivo de signatura.

### <a name="code"></a>Código

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

En el ejemplo siguiente se muestra el método alternativo, sin etiquetas XML. En este ejemplo, todo el texto del comentario se considera un resumen. Tenga en cuenta que si no especifica explícitamente una etiqueta de Resumen, no debe especificar otras etiquetas, como **param** o **Return** Tags.

### <a name="code"></a>Código

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Opciones del compilador](compiler-options.md)
