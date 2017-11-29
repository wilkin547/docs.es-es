---
title: "Documentación XML (F#)"
description: "Obtenga información sobre la compatibilidad de F # para generar la documentación de los comentarios."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d99ab1b6-e170-4ec2-a543-43ea7ab15bb2
ms.openlocfilehash: 20768a7d4ea17c926318043f658691819a3d7d2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xml-documentation"></a>Documentación de XML

Se puede generar documentación de triple con una barra diagonal (/ / /) comentarios en F # en código. Comentarios XML pueden preceder a las declaraciones en archivos de código (.fs) o archivos de signatura (.fsi).


## <a name="generating-documentation-from-comments"></a>Generar documentación de comentarios
La compatibilidad de F # para generar la documentación de los comentarios es el mismo que en otros lenguajes de .NET Framework. Al igual que en otros lenguajes de .NET Framework, el [-doc (opción) compilador](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) le permite generar un archivo XML que contiene información que se puede convertir en documentación mediante una herramienta como Sandcastle. La documentación generada mediante herramientas que están diseñados para su uso con los ensamblados que se escriben en otros lenguajes de .NET Framework suelen generar una vista de las API que se basan en el formato compilado de F # construcciones. A menos que herramientas específicamente son compatibles con F #, documentación generada por estas herramientas no coincide con la vista de una API de F #.

Para obtener más información acerca de cómo generar documentación de XML, vea [comentarios de documentación XML &#40; C &#35; Guía de programación de &#41; ](https://msdn.microsoft.com/library/b2s063f7).


## <a name="recommended-tags"></a>Etiquetas recomendadas
Hay dos maneras de escribir comentarios de documentación XML. Una consiste en escribir simplemente la documentación directamente en un comentario de barra diagonal triple, sin utilizar etiquetas XML. Si lo hace, el texto del comentario se toma como documentación de resumen para la construcción de código que sigue inmediatamente a. Utilice este método cuando desee escribir sólo un breve resumen de cada construcción. El otro método consiste en utilizar etiquetas XML para proporcionar documentación más estructurada. El segundo método le permite especificar notas independientes para hacer un breve resumen, notas adicionales, documentación de cada parámetro y el parámetro de tipo y las excepciones iniciadas y una descripción del valor devuelto. La tabla siguiente describen las etiquetas XML que se reconocen en los comentarios de código XML de F #.



|Sintaxis de etiqueta|Descripción|
|----------|-----------|
|**&lt;c&gt;***texto***&lt;/c&gt;**|Especifica que *texto* es el código. Esta etiqueta se pueden usar generadores de documentación para mostrar texto en una fuente que sea adecuada para el código.|
|**&lt;resumen&gt;***texto* **&lt; /resumen&gt;**|Especifica que *texto* es una breve descripción del elemento de programa. La descripción suele ser una o dos frases.|
|**&lt;comentarios&gt;***texto* **&lt; /comentarios&gt;**|Especifica que *texto* contiene información adicional sobre el elemento de programa.|
|**&lt;param name = "***nombre***"&gt;***descripción***&lt;/param&gt;**|Especifica el nombre y una descripción para un parámetro de función o un método.|
|**&lt;typeparam nombre = "***nombre***"&gt;***descripción***&lt;/typeparam&gt;**|Especifica el nombre y una descripción para un parámetro de tipo.|
|**&lt;Devuelve&gt;***texto* **&lt; /devuelve&gt;**|Especifica que *texto* describe el valor devuelto de una función o método.|
|**&lt;excepción cref = "***tipo***"&gt;***descripción***&lt;/exception&gt;**|Especifica el tipo de excepción que se pueden generar y las circunstancias en las que se produce.|
|**&lt;vea cref = "***referencia***"&gt;***texto* **&lt; /vea&gt;**|Especifica un vínculo insertado a otro elemento de programa. El *referencia* es el nombre tal y como aparece en el archivo de documentación XML. El *texto* es el texto que se muestra en el vínculo.|
|**&lt;seealso cref = "***referencia***" /&gt;**|Especifica un vínculo Consulte también la documentación de otro tipo. El *referencia* es el nombre tal y como aparece en el archivo de documentación XML. Vea también suelen aparecer en la parte inferior de una página de documentación de vínculos.|
|**&lt;para&gt;***texto***&lt;/para&gt;**|Especifica un párrafo de texto. Se utiliza para separar el texto dentro de la **comentarios** etiqueta.|

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción
El siguiente es un comentario de documentación XML típico en un archivo de signatura.


### <a name="code"></a>Código
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]
    
## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción
En el ejemplo siguiente se muestra el método alternativo, sin etiquetas XML. En este ejemplo, todo el texto del comentario se considera un resumen. Tenga en cuenta que si no especifica explícitamente un summary (etiqueta), no debe especificar otras etiquetas, como **param** o **devuelve** etiquetas.


### <a name="code"></a>Código
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]
    
## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Opciones del compilador](compiler-options.md)
