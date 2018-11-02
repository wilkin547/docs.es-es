---
title: Documentación XML (F#)
description: 'Obtenga información sobre la compatibilidad de F # para generar documentación a partir de comentarios.'
ms.date: 05/16/2016
ms.openlocfilehash: 1a4cb132e65b630821e5eb2b39276c1de99aff80
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "45641630"
---
# <a name="xml-documentation"></a>Documentación de XML

Se puede generar documentación de triple barra diagonal (/ / /) comentarios en F # en código. Los comentarios XML pueden preceder a las declaraciones en archivos de código (.fs) o archivos de signatura (.fsi).

## <a name="generating-documentation-from-comments"></a>Generar documentación a partir de comentarios

La compatibilidad de F # para generar documentación a partir de comentarios es la misma que en otros lenguajes de .NET Framework. Al igual que en otros lenguajes de .NET Framework, el [-doc (opción) del compilador](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) permite generar un archivo XML que contiene información que se puede convertir en documentación mediante una herramienta como Sandcastle. La documentación generada mediante las herramientas que están diseñadas para su uso con los ensamblados que se escriben en otros lenguajes de .NET Framework, por lo general generan una vista de las API que se basan en el formato compilado de construcciones de F #. A menos que las herramientas específicamente son compatibles con F #, documentación generada por estas herramientas no coincide con la vista de una API de F #.

Para obtener más información sobre cómo generar documentación de XML, vea [comentarios de documentación XML &#40;C&#35; Programming Guide&#41;](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Etiquetas recomendadas

Hay dos maneras de escribir comentarios de documentación XML. Una es simplemente escribir la documentación directamente en un comentario de barra diagonal triple, sin usar etiquetas XML. Si lo hace, el texto del comentario se toma como documentación de resumen para la construcción de código que sigue inmediatamente. Utilice este método cuando desee escribir sólo un breve resumen de cada construcción. El otro método consiste en usar etiquetas XML para proporcionar documentación más estructurada. El segundo método permite especificar notas independientes para un breve resumen, comentarios adicionales, documentación de cada parámetro y el parámetro de tipo y la excepción y una descripción del valor devuelto. En la tabla siguiente se describe las etiquetas XML que se reconocen en los comentarios del código XML de F #.

|Sintaxis de etiquetas|Descripción|
|----------|-----------|
|**&lt;c&gt;***texto***&lt;/c&gt;**|Especifica que *texto* es el código. Esta etiqueta se puede usar generadores de documentación para mostrar texto en una fuente que sea adecuada para el código.|
|**&lt;resumen&gt;***texto*** &lt; /summary&gt;**|Especifica que *texto* es una breve descripción del elemento de programa. La descripción suele ser una o dos frases.|
|**&lt;comentarios&gt;***texto*** &lt; /comentarios&gt;**|Especifica que *texto* contiene información adicional sobre el elemento de programa.|
|**&lt;nombre de parámetro = "***nombre***"&gt;***descripción***&lt;/param&gt;**|Especifica el nombre y una descripción para un parámetro de función o método.|
|**&lt;typeparam nombre = "***nombre***"&gt;***descripción***&lt;/typeparam&gt;**|Especifica el nombre y una descripción para un parámetro de tipo.|
|**&lt;Devuelve&gt;***texto*** &lt; /devuelve&gt;**|Especifica que *texto* describe el valor devuelto de una función o método.|
|**&lt;excepción cref = "***tipo***"&gt;***descripción***&lt;/exception&gt;**|Especifica el tipo de excepción que se puede generar y las circunstancias en las que se produzca la excepción.|
|**&lt;vea cref = "***referencia***"&gt;***texto*** &lt; /ver&gt;**|Especifica un vínculo insertado a otro elemento de programa. El *referencia* es el nombre tal como aparece en el archivo de documentación XML. El *texto* es el texto que se muestra en el vínculo.|
|**&lt;seealso cref = "***referencia***" /&gt;**|Especifica un vínculo Vea también la documentación de otro tipo. El *referencia* es el nombre tal como aparece en el archivo de documentación XML. Vea también suelen aparecer en la parte inferior de una página de documentación de vínculos.|
|**&lt;para&gt;***texto***&lt;/para&gt;**|Especifica un párrafo de texto. Esto se usa para separar el texto dentro de la **comentarios** etiqueta.|

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

El siguiente es un comentario de documentación XML típico en un archivo de signatura.

### <a name="code"></a>Código

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

El ejemplo siguiente muestra el método alternativo, sin las etiquetas XML. En este ejemplo, todo el texto del comentario se considera un resumen. Tenga en cuenta que si no especifica explícitamente una etiqueta de resumen, no debe especificar otras etiquetas, como **param** o **devuelve** etiquetas.

### <a name="code"></a>Código

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Opciones del compilador](compiler-options.md)
