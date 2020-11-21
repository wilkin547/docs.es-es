---
title: Documentación de XML
description: 'Obtenga información sobre la compatibilidad de F # para generar documentación a partir de comentarios.'
ms.date: 09/15/2020
ms.openlocfilehash: 24d9dbfb5e28d39e224ef9428f025298464fc7f4
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099014"
---
# <a name="document-your-code-with-xml-comments"></a>Documentación del código con comentarios XML

Puede generar documentación a partir de comentarios de código con una barra diagonal triple (///) en F #. Los comentarios XML pueden preceder a las declaraciones de los archivos de código (. FS) o de firma (. FSI).

Los comentarios de documentación XML son un tipo especial de comentarios que se agregan encima de la definición de un tipo o un miembro definido por el usuario.
Son especiales porque los puede procesar el compilador para generar un archivo de documentación XML en tiempo de compilación.
El archivo XML generado por el compilador se puede distribuir junto con el ensamblado .NET para que los IDE puedan usar la información sobre herramientas para mostrar información rápida sobre los tipos o miembros. Además, el archivo XML se puede ejecutar a través de herramientas como [fsdocs](http://fsprojects.github.io/FSharp.Formatting/) para generar sitios web de referencia de API.

El compilador omite los comentarios de documentación XML, como todos los demás comentarios, a menos que se habiliten las opciones que se describen a continuación para comprobar la validez y la integridad de los comentarios en tiempo de compilación.

Para generar el archivo XML en tiempo de compilación, realice una de las siguientes acciones:

- Puede Agregar un `GenerateDocumentationFile` elemento a la `<PropertyGroup>` sección del archivo de `.fsproj` proyecto, que genera un archivo XML en el directorio del proyecto con el mismo nombre de archivo raíz que el ensamblado. Por ejemplo:

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

- Si está desarrollando una aplicación mediante Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **Propiedades**. En el cuadro de diálogo de propiedades, seleccione la pestaña **Compilar** y active **Archivo de documentación XML**. También puede cambiar la ubicación en la que el compilador escribe el archivo.

Hay dos maneras de escribir comentarios de documentación XML: con y sin etiquetas XML. Ambos usan comentarios de barra diagonal triple.

## <a name="comments-without-xml-tags"></a>Comentarios sin etiquetas XML

Si un `///` comentario no comienza con `<` , se toma el texto del comentario completo como la documentación de Resumen de la construcción de código que sigue inmediatamente. Utilice este método cuando desee escribir solo un breve resumen de cada construcción.

El comentario se codifica en XML durante la preparación de la documentación, por lo que `<` `>` `&` no es necesario usar caracteres de escape como, y. Si no especifica explícitamente una etiqueta de Resumen, no debe especificar otras etiquetas, como **param** o **Return** Tags.

En el ejemplo siguiente se muestra el método alternativo, sin etiquetas XML. En este ejemplo, todo el texto del comentario se considera un resumen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="comments-with-xml-tags"></a>Comentarios con etiquetas XML

Si un cuerpo de comentario comienza con `<` (normalmente `<summary>` ), se trata como un cuerpo de comentario con formato XML mediante etiquetas XML. Este segundo le permite especificar notas independientes para un breve resumen, comentarios adicionales, documentación para cada parámetro y parámetro de tipo y excepciones producidas, y una descripción del valor devuelto.

A continuación se encuentra un Comentario de documentación XML típico en un archivo de signatura:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="recommended-tags"></a>Etiquetas recomendadas

Si usa etiquetas XML, en la tabla siguiente se describen las etiquetas externas reconocidas en los comentarios de código XML de F #.

| Sintaxis de etiquetas                                  | Descripción |
|---------------------------------------------|-----------|
| `<summary>`**_negrita_**`</summary>`           | Especifica que el *texto* es una breve descripción del elemento de programa. La descripción suele ser una o dos oraciones.|
| `<remarks>`**_negrita_**`</remarks>`           | Especifica que el *texto* contiene información adicional sobre el elemento de programa.|
| `<param name="`**_nombre_** `">` de **_Descripción_ de**`</param>` | Especifica el nombre y la descripción de un parámetro de función o método.|
| `<typeparam name="`**_nombre_** `">` de **_Descripción_ de**`</typeparam>` | Especifica el nombre y la descripción de un parámetro de tipo.|
| `<returns>`**_negrita_**`</returns>`           | Especifica que el *texto* describe el valor devuelto de una función o un método.|
| `<exception cref="`**_tipo_** `">` de **_Descripción_ de**`</exception>` |Especifica el tipo de excepción que se puede generar y las circunstancias en las que se produce.|
| `<seealso cref="`**_referencia_**`"/>`      | Especifica un vínculo ver también a la documentación de otro tipo. La *referencia* es el nombre tal y como aparece en el archivo de documentación XML. Vea también los vínculos normalmente aparecen en la parte inferior de una página de documentación.|

En la tabla siguiente se describen las etiquetas para su uso dentro de las secciones de Descripción:

| Sintaxis de etiquetas                                | Descripción |
|-------------------------------------------|-------------|
| `<para>`**_negrita_**`</para>`               | Especifica un párrafo de texto. Se usa para separar texto dentro de la etiqueta **comentarios** .|
| `<code>`**_negrita_**`</code>`               | Especifica que el *texto* es varias líneas de código. Los generadores de documentación pueden usar esta etiqueta para mostrar texto en una fuente que sea adecuada para el código.|
| `<paramref name="`**_Name_**`"/>`         | Especifica una referencia a un parámetro en el mismo comentario de documentación.|
| `<typeparamref name="`**_Name_**`"/>`     | Especifica una referencia a un parámetro de tipo en el mismo comentario de documentación.|
| `<c>`**_negrita_**`</c>`                     | Especifica que el *texto* es código insertado. Los generadores de documentación pueden usar esta etiqueta para mostrar texto en una fuente que sea adecuada para el código.|
| `<see cref="`**_referencia_** `">` de **_texto_ de**`</see>` | Especifica un vínculo insertado a otro elemento de programa. La *referencia* es el nombre tal y como aparece en el archivo de documentación XML. El *texto* es el texto que se muestra en el vínculo.|

### <a name="user-defined-tags"></a>Etiquetas definidas por el usuario

Las etiquetas anteriores representan aquellas que reconoce el compilador de F # y las herramientas típicas del editor de F #. pero el usuario puede definir sus propias etiquetas.
Herramientas como fsdocs proporcionan compatibilidad con etiquetas adicionales como [\<namespacedoc>](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1031-xmldoc-extensions.md) .
También se pueden usar herramientas de generación de documentación internas o personalizadas con las etiquetas estándar y se admiten varios formatos de salida, de HTML a PDF.

## <a name="compile-time-checking"></a>Comprobación en tiempo de compilación

Cuando `--warnon:3390` está habilitado, el compilador comprueba la sintaxis del XML y los parámetros a los que se hace referencia en las `<param>` `<paramref>` etiquetas y.

## <a name="documenting-f-constructs"></a>Documentar construcciones de F #

Las construcciones de F #, como los módulos, los miembros, los casos de Unión y los campos de registro, se documentan mediante un `///` Comentario inmediatamente antes de su declaración.
Si es necesario, los constructores implícitos de clases se documentan asignando un `///` comentario antes de la lista de argumentos. Por ejemplo:

```fsharp
/// This is the type
type SomeType
      /// This is the implicit constructor
      (a: int, b: int) =

    /// This is the member
    member _.Sum() = a + b
```

## <a name="limitations"></a>Limitaciones

Algunas características de la documentación XML en C# y otros lenguajes .NET no se admiten en C#.

- En F #, las referencias cruzadas deben usar la firma XML completa del símbolo correspondiente, por ejemplo `cref="T:System.Console"` .
  El compilador de F # no comprueba las referencias cruzadas simples de estilo C#, como, `cref="Console"` que no se han elaborado a firmas XML completas y que estos elementos no se comprueban. Algunas herramientas de documentación pueden permitir el uso de estas referencias cruzadas en el procesamiento posterior, pero se deben usar las firmas completas.

- El `<include>` `<inheritdoc>` compilador de F # no admite las etiquetas. No se produce ningún error si se usan, pero simplemente se copian en el archivo de documentación generado sin afectar de otro modo a la documentación generada.

- El compilador de F # no comprueba las referencias cruzadas, incluso cuando `-warnon:3390` se usa.

- El `<typeparam>` compilador de F # no comprueba los nombres que se usan en las etiquetas y `<typeparamref>` , incluso cuando `--warnon:3390` se usa.

- No se proporcionan advertencias si falta documentación, incluso cuando `--warnon:3390` se usa.

## <a name="recommendations"></a>Recomendaciones

Se recomienda documentar código por diversos motivos. A continuación se muestran algunos procedimientos recomendados, escenarios de casos de uso generales y aspectos que debe conocer al usar etiquetas de documentación XML en el código de F #.

- Habilite la opción `--warnon:3390` en el código para asegurarse de que la documentación XML sea XML válida.

- Considere la posibilidad de agregar archivos de firma para separar los comentarios de documentación XML largos de la implementación.

- Por motivos de coherencia, se deben documentar todos los tipos públicamente visibles y sus miembros. Si debe hacerlo, hágalo en todos los elementos.

- Como mínimo, los módulos, los tipos y sus miembros deben tener una `///` etiqueta o comentario sin formato `<summary>` . Esto se mostrará en una ventana de información sobre herramientas de finalización automática en herramientas de edición de F #.

- El texto de la documentación se debe escribir con frases completas que terminen en punto.

## <a name="see-also"></a>Vea también

- [Comentarios de documentación XML de C# &#40;guía de programación de C&#35;&#41;](../../csharp/programming-guide/xmldoc/index.md).
- [Referencia del lenguaje F#](index.md)
- [Opciones del compilador](compiler-options.md)
