---
title: Documentar el código con comentarios XML
description: Obtenga información sobre cómo documentar el código con comentarios de documentación XML y generar un archivo de documentación XML en tiempo de compilación.
ms.date: 01/21/2020
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 91de11c610ea17999dabff6d0552de9440f532e6
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465304"
---
# <a name="document-your-code-with-xml-comments"></a>Documentación del código con comentarios XML

Los comentarios de documentación XML son un tipo especial de comentarios que se agregan encima de la definición de un tipo o un miembro definido por el usuario.
Son especiales porque los puede procesar el compilador para generar un archivo de documentación XML en tiempo de compilación.
El archivo XML generado por el compilador se puede distribuir junto con el ensamblado .NET de modo que Visual Studio y otros IDE puedan usar IntelliSense para mostrar información rápida sobre los tipos o los miembros. Además, el archivo XML se puede ejecutar mediante herramientas como [DocFX](https://dotnet.github.io/docfx/) y [Sandcastle](https://github.com/EWSoftware/SHFB) para generar sitios web de referencia de API.

El compilador omite los comentarios de documentación XML, igual que los demás comentarios.

Para generar el archivo XML en tiempo de compilación, realice una de las siguientes acciones:

- Si está desarrollando una aplicación con .NET Core desde la línea de comandos, puede agregar un elemento `GenerateDocumentationFile` a la sección `<PropertyGroup>` de su archivo de proyecto .csproj. También puede especificar la ruta de acceso al archivo de documentación directamente mediante el [elemento `DocumentationFile`](/visualstudio/msbuild/common-msbuild-project-properties). En el siguiente ejemplo se genera un archivo XML en el directorio del proyecto con el mismo nombre de archivo raíz que el ensamblado:

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

   Es equivalente a la siguiente:

   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- Si está desarrollando una aplicación mediante Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **Propiedades**. En el cuadro de diálogo de propiedades, seleccione la pestaña **Compilar** y active **Archivo de documentación XML**. También puede cambiar la ubicación en la que el compilador escribe el archivo.

- Si va a compilar una aplicación de .NET desde la línea de comandos, agregue la [opción del compilador -doc](language-reference/compiler-options/doc-compiler-option.md) al realizar la compilación.  

Los comentarios de documentación XML usan tres barras diagonales (`///`) y un cuerpo de comentario con formato XML. Por ejemplo:

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a>Tutorial

Vamos a documentar una biblioteca matemática muy básica para que a los nuevos desarrolladores les resulte más fácil comprenderla y contribuir, y a los desarrolladores de otras empresas usarla.

Este es el código de la biblioteca matemática simple:

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

La biblioteca de ejemplo es compatible con cuatro operaciones aritméticas principales (`add`, `subtract`, `multiply` y `divide`) en tipos de datos `int` y `double`.

Ahora le interesa crear un documento de referencia de API desde el código para los desarrolladores de otras empresas que usan la biblioteca, pero no tienen acceso al código fuente.
Como se mencionó anteriormente, las etiquetas de documentación XML pueden utilizarse para lograr esto. Ahora recibirá una introducción a las etiquetas XML estándares que admite el compilador de C#.

## \<summary>

La etiqueta `<summary>` agrega información breve sobre un tipo o miembro.
Vamos a demostrar su uso agregándola a la definición de clase `Math` y al primer método `Add`. No dude en aplicarla al resto del código.

[!code-csharp[Summary Tag](~/samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

La etiqueta `<summary>` es importante y se recomienda incluirla, dado que su contenido es la principal fuente de información sobre el tipo o el miembro en IntelliSense o en un documento de referencia de API.

## \<remarks>

La etiqueta `<remarks>` complementa la información sobre los tipos o los miembros que proporciona la etiqueta `<summary>`. En este ejemplo, solo la agregará a la clase.

[!code-csharp[Remarks Tag](~/samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## \<returns>

La etiqueta `<returns>` describe el valor devuelto de una declaración de método.
Al igual que antes, en el ejemplo siguiente se muestra la etiqueta `<returns>` en el primer método `Add`. Puede hacer lo mismo en otros métodos.

[!code-csharp[Returns Tag](~/samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## \<value>

La etiqueta `<value>` es similar a la etiqueta `<returns>`, salvo que se usa para propiedades.
Supongamos que su biblioteca `Math` tenía una propiedad estática denominada `PI`. A continuación le mostramos cómo usaría esta etiqueta:

[!code-csharp[Value Tag](~/samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## \<example>

La etiqueta `<example>` se usa para incluir un ejemplo en la documentación XML.
Esto implica usar la etiqueta secundaria `<code>`.

[!code-csharp[Example Tag](~/samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

La etiqueta `code` conserva los saltos de línea y la sangría en los ejemplos más largos.

## \<para>

La etiqueta `<para>` se usa para dar formato al contenido dentro de la etiqueta primaria. `<para>` suele usarse dentro de una etiqueta, como `<remarks>` o `<returns>`, para dividir el texto en párrafos.
Puede dar formato al contenido de la etiqueta `<remarks>` de su definición de clase.

[!code-csharp[Para Tag](~/samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## \<c>

También en el ámbito del formato, puede usar la etiqueta `<c>` para marcar una parte del texto como código.
Es como la etiqueta `<code>`, pero insertada. Es útil si quiere mostrar un ejemplo de código rápido como parte del contenido de la etiqueta.
Vamos a actualizar la documentación de la clase `Math`.

[!code-csharp[C Tag](~/samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## \<exception>

Mediante el uso de la etiqueta `<exception>`, permite que los desarrolladores sepan que un método puede producir excepciones específicas.
Si examina su biblioteca `Math`, verá que los dos métodos `Add` producen una excepción si se cumple una determinada condición. En cambio, no resulta tan obvio que el método entero `Divide` también produce una si el parámetro `b` es cero. Vamos a agregar documentación de la excepción a este método.

[!code-csharp[Exception Tag](~/samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

El atributo `cref` representa una referencia a una excepción que está disponible desde el entorno de compilación actual.
Puede ser cualquier tipo definido en el proyecto o un ensamblado de referencia. El compilador emitirá una advertencia si su valor no puede resolverse.

## \<see>

La etiqueta `<see>` le permite crear un vínculo interactivo a una página de documentación para otro elemento de código. En el siguiente ejemplo, crearemos un vínculo interactivo entre los dos métodos `Add`.

[!code-csharp[See Tag](~/samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

`cref` es un atributo **necesario** que representa una referencia a un tipo o a su miembro que está disponible desde el entorno de compilación actual.
Puede ser cualquier tipo definido en el proyecto o un ensamblado de referencia.

## \<seealso>

La etiqueta `<seealso>` se usa de la misma manera que la etiqueta `<see>`. La única diferencia es que su contenido se suele colocar en una sección "Vea también". Aquí vamos a agregar una etiqueta `seealso` en el método entero `Add` para hacer referencia a otros métodos de la clase que aceptan parámetros enteros:

[!code-csharp[Seealso Tag](~/samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

El atributo `cref` representa una referencia a un tipo o a su miembro que está disponible desde el entorno de compilación actual.
Puede ser cualquier tipo definido en el proyecto o un ensamblado de referencia.

## \<param>

La etiqueta `<param>` se usa para describir los parámetros de un método. Aquí se muestra un ejemplo del método doble `Add`: el parámetro que la etiqueta describe se especifica en el atributo **necesario** `name`.

[!code-csharp[Param Tag](~/samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## \<typeparam>

La etiqueta `<typeparam>` se usa igual que la etiqueta `<param>`, pero sirve para que las declaraciones de método o tipo genérico describan un parámetro genérico.
Agregue un método genérico rápido a su clase `Math` para comprobar si una cantidad es mayor que otra.

[!code-csharp[Typeparam Tag](~/samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## \<paramref>

Puede darse la situación de que esté describiendo lo que hace un método en una etiqueta `<summary>` y le interese hacer referencia a un parámetro. La etiqueta `<paramref>` es perfecta para esto. Vamos a actualizar el resumen del método doble `Add`. Igual que en la etiqueta `<param>`, el nombre del parámetro se especifica en el atributo **necesario** `name`.

[!code-csharp[Paramref Tag](~/samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## \<typeparamref>

La etiqueta `<typeparamref>` se usa igual que la etiqueta `<paramref>`, pero sirve para que las declaraciones de método o tipo genérico describan un parámetro genérico.
Puede usar el mismo método genérico que ha creado previamente.

[!code-csharp[Typeparamref Tag](~/samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## \<list>

La etiqueta `<list>` se usa para dar formato a la información de la documentación en una lista ordenada, una lista sin ordenar o una tabla. Cree una lista sin ordenar con todas las operaciones matemáticas que admita su biblioteca `Math`.

[!code-csharp[List Tag](~/samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

Para crear una lista ordenada o una tabla, cambie el atributo `type` a `number` o `table`, respectivamente.

## \<inheritdoc>

Puede usar la etiqueta `<inheritdoc>` para heredar comentarios XML de clases base, interfaces y métodos similares. Esto elimina la acción de copiar y pegar no deseada de comentarios XML duplicados y mantiene los comentarios XML sincronizados automáticamente.

[!code-csharp-interactive[InheritDoc Tag](~/samples/snippets/csharp/concepts/codedoc/inheritdoc-tag.cs)]

### <a name="put-it-all-together"></a>Colocación de todo junto

Si ha seguido este tutorial y ha aplicado las etiquetas al código en los casos en que era necesario, el código debe ser ahora similar al siguiente:

[!code-csharp[Tagged Library](~/samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

Desde su código, puede generar un sitio web de documentación detallada completo con referencias cruzadas interactivas. Pero se enfrenta a otro problema: su código se ha vuelto difícil de leer.
Es una pesadilla para los desarrolladores que quieran contribuir a este código, ya que hay mucha información que examinar.
Afortunadamente, hay una etiqueta XML que le ayudará a resolverlo:

## \<include>

La etiqueta `<include>` le permite hacer referencia a los comentarios de un archivo XML independiente que describen los tipos y los miembros del código fuente, en vez de colocar los comentarios de documentación directamente en el archivo de código fuente.

Ahora vamos a mover todas las etiquetas XML a un archivo XML independiente denominado `docs.xml`. Puede ponerle al archivo el nombre que quiera.

[!code-xml[Sample XML](~/samples/snippets/csharp/concepts/codedoc/include.xml)]

En el XML anterior, los comentarios de documentación de cada miembro aparecen directamente dentro de una etiqueta cuyo nombre indica lo que hacen, pero puede elegir su propia estrategia.
Ahora que tiene los comentarios XML en un archivo independiente, veamos cómo se puede hacer más legible el código mediante la etiqueta `<include>`:

[!code-csharp[Include Tag](~/samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

Aquí lo tiene: el código vuelve a ser legible y no se ha perdido ninguna información de documentación.

El atributo `file` representa el nombre del archivo XML que contiene la documentación.

El atributo `path` representa una consulta [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) para el `tag name` presente en el `file` especificado.

El atributo `name` representa el especificador de nombre en la etiqueta que precede a los comentarios.

El atributo `id`, que se puede usar en lugar de `name`, representa el identificador de la etiqueta que precede a los comentarios.

### <a name="user-defined-tags"></a>Etiquetas definidas por el usuario

Todas las etiquetas descritas anteriormente son las que reconoce el compilador de C#, pero el usuario puede definir sus propias etiquetas.
Herramientas como Sandcastle proporcionan compatibilidad con etiquetas adicionales como [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) y [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), e incluso permiten [documentar espacios de nombres](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).
También se pueden usar herramientas de generación de documentación internas o personalizadas con las etiquetas estándar y se admiten varios formatos de salida, de HTML a PDF.

## <a name="recommendations"></a>Recomendaciones

Se recomienda documentar código por diversos motivos. A continuación se muestran algunos procedimientos recomendados, escenarios generales de casos de uso y conceptos que debe conocer al usar etiquetas de documentación XML en el código de C#.

- Por motivos de coherencia, se deben documentar todos los tipos públicamente visibles y sus miembros. Si debe hacerlo, hágalo en todos los elementos.
- Los miembros privados también se pueden documentar mediante comentarios XML, pero esto expone el funcionamiento interno (potencialmente confidencial) de la biblioteca.
- Como mínimo, los tipos y sus miembros deben tener una etiqueta `<summary>`, ya que su contenido es necesario para IntelliSense.
- El texto de la documentación se debe escribir con frases completas que terminen en punto.
- Las clases parciales son totalmente compatibles y la información de documentación se concatenará en una única entrada para ese tipo.
- El compilador comprueba la sintaxis de las etiquetas `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` y `<typeparam>`.
- El compilador valida los parámetros que contienen rutas de acceso de archivo y referencias a otras partes del código.

## <a name="see-also"></a>Vea también

- [Comentarios de documentación XML (Guía de programación de C#)](programming-guide/xmldoc/index.md)
- [Etiquetas recomendadas para comentarios de documentación (Guía de programación de C#)](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
