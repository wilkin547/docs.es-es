---
title: Documentación XML (F#)
description: Obtenga información sobre la compatibilidad en F# para generar documentación a partir de comentarios.
ms.date: 05/16/2016
ms.openlocfilehash: c5305dea8832112644710b2863269ef00feddd10
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204683"
---
# <a name="xml-documentation"></a>Documentación de XML

Se puede generar documentación de triple barra diagonal (/ / /) en los comentarios de código F#. Los comentarios XML pueden preceder a las declaraciones en archivos de código (.fs) o archivos de signatura (.fsi).

## <a name="generating-documentation-from-comments"></a>Generar documentación a partir de comentarios

La compatibilidad en F# para generar documentación a partir de comentarios es la misma que en otros lenguajes de .NET Framework. Al igual que en otros lenguajes de .NET Framework, el [-doc (opción) del compilador](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) permite generar un archivo XML que contiene información que se puede convertir en documentación mediante una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [ Sandcastle](https://github.com/EWSoftware/SHFB). La documentación generada mediante las herramientas que están diseñadas para su uso con los ensamblados que se escriben en otros lenguajes de .NET Framework, por lo general generan una vista de las API que se basan en el formato compilado de F# construye. A menos que admiten específicamente herramientas F#, documentación generada por estas herramientas no coincide con el F# vista de una API.

Para obtener más información sobre cómo generar documentación de XML, vea [comentarios de documentación XML &#40;C&#35; Programming Guide&#41;](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Etiquetas recomendadas

Hay dos maneras de escribir comentarios de documentación XML. Una es simplemente escribir la documentación directamente en un comentario de barra diagonal triple, sin usar etiquetas XML. Si lo hace, el texto del comentario se toma como documentación de resumen para la construcción de código que sigue inmediatamente. Utilice este método cuando desee escribir sólo un breve resumen de cada construcción. El otro método consiste en usar etiquetas XML para proporcionar documentación más estructurada. El segundo método permite especificar notas independientes para un breve resumen, comentarios adicionales, documentación de cada parámetro y el parámetro de tipo y la excepción y una descripción del valor devuelto. La tabla siguiente describen las etiquetas XML que se reconocen en F# comentarios del código XML.

|Sintaxis de etiquetas|Descripción|
|----------|-----------|
|**\<c\>**_text_**\</c\>**|Especifica que *texto* es el código. Esta etiqueta se puede usar generadores de documentación para mostrar texto en una fuente que sea adecuada para el código.|
|**\<summary\>**_text_**\</summary\>**|Especifica que *texto* es una breve descripción del elemento de programa. La descripción suele ser una o dos frases.|
|**\<remarks\>**_text_**\</remarks\>**|Especifica que *texto* contiene información adicional sobre el elemento de programa.|
|**\<nombre de parámetro = "**_nombre_**"\>**_descripción_**\</param\>**|Especifica el nombre y una descripción para un parámetro de función o método.|
|**\<typeparam nombre = "**_nombre_**"\>**_descripción_**\</typeparam\>**|Especifica el nombre y una descripción para un parámetro de tipo.|
|**\<returns\>**_text_**\</returns\>**|Especifica que *texto* describe el valor devuelto de una función o método.|
|**\<excepción cref = "**_tipo_**"\>**_descripción_**\</exception\>**|Especifica el tipo de excepción que se puede generar y las circunstancias en las que se produzca la excepción.|
|**\<vea cref = "**_referencia_**"\>**_texto_ **\< /ver\>**|Especifica un vínculo insertado a otro elemento de programa. El *referencia* es el nombre tal como aparece en el archivo de documentación XML. El *texto* es el texto que se muestra en el vínculo.|
|**\<seealso cref = "**_referencia_**" /\>**|Especifica un vínculo Vea también la documentación de otro tipo. El *referencia* es el nombre tal como aparece en el archivo de documentación XML. Vea también suelen aparecer en la parte inferior de una página de documentación de vínculos.|
|**\<para\>**_text_**\</para\>**|Especifica un párrafo de texto. Esto se usa para separar el texto dentro de la **comentarios** etiqueta.|

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
