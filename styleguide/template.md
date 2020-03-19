---
title:
- TÍTULO DEL ARTÍCULO
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - MM/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: 1ddeeaca4645bd4788f03018643a0bc2682c731a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79186909"
---
# <a name="metadata-and-markdown-template"></a>Plantilla de Markdown y metadatos

Esta plantilla de dotnet/docs contiene ejemplos de sintaxis de Markdown, así como instrucciones sobre cómo establecer los metadatos. Para sacar el máximo partido, debe ver el [Markdown sin formato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) y la [vista representada](https://github.com/dotnet/docs/blob/master/styleguide/template.md).

Al crear un archivo de Markdown, debe copiar la plantilla en un archivo nuevo, rellenar los metadatos como se indica a continuación, configurar el encabezado H1 como se indica antes del título de este artículo y eliminar el contenido.

## <a name="metadata"></a>Metadatos

Puede encontrar el bloque de metadatos completo más arriba (en el [Markdown sin formato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), dividido en los campos obligatorios y opcionales. Algunas notas claves:

- **Debe** haber un espacio entre los dos puntos (:) y el valor de un elemento de metadatos.
- Si un elemento de metadatos no tiene valor, comente el elemento con el carácter # o quítelo (no lo deje en blanco ni use "na"). Si va a agregar un valor a un elemento que se comentó, asegúrese de quitar el carácter #.
- Dos puntos en un valor (por ejemplo, un título) interrumpen el analizador de metadatos. En este caso, encierre el título con comillas dobles (por ejemplo, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: aparece en los resultados del motor de búsqueda. El título no debe ser idéntico al título en el encabezado H1 y debe contener 60 caracteres o menos.
- **description**: resume el contenido del artículo. Habitualmente aparece en la página de resultados de la búsqueda, pero no se usa para la clasificación de la búsqueda. Debe tener entre 115 y 145 caracteres, incluidos los espacios.
- **author** y **ms.author**: el campo author debe contener el **nombre de usuario de GitHub** del autor, no su alias. Por otro lado, el campo **ms.author** debe contener un alias de Microsoft e indica al responsable de mantener el artículo.
- **ms.topic**: el tipo de tema. El valor más común es `conceptual` y se establece en un nivel global. Otros valores comunes que se usan son `tutorial`, `overview` y `reference`.
- **dev_langs** define el filtro de lenguaje que se muestra para el tema. Puede ver una lista de los valores admitidos en la sección [Lenguajes admitidos](#supported-languages). Solo se debe establecer cuando el tema abarca más de un lenguaje de programación. Por lo general, en nuestro contenido solo se usa `csharp`, `vb`, `fsharp` y `cpp` para este valor.
- **ms.prod**: identificación del producto que se usa con fines de inteligencia empresarial. Por lo general, se establecen en un nivel global, por lo que no suelen aparecer en el bloque de metadatos de cada artículo.
- **ms.technology**: clasificación de inteligencia empresarial adicional. Algunos de los valores admitidos son: `devlang-csharp` para temas de C#, `devlang-fsharp` para temas de F# y `devlang-visual-basic` para temas de VB. Los valores variarán en otras guías, por lo que deberá pedir ayuda a un miembro del equipo.
- **ms.date**: fecha con formato DD/MM/AAAA. Se muestra en la página publicada para indicar la última vez que el artículo se editó de manera sustancial o se garantizó como "actualizado" (es decir, la última vez que se revisó el artículo y se consideró como actualizado).
- **helpviewer_keywords**: las entradas se usan para los índices de libros sin conexión (una funcionalidad de Visual Studio).
- **f1_keywords**: conecta el artículo con la tecla F1 (una funcionalidad de Visual Studio).

## <a name="basic-markdown-gfm-and-special-characters"></a>Markdown básico, GFM y caracteres especiales

Todos los Markdown básicos y característicos de GitHub (GFM) son compatibles. Para obtener más información sobre este tema, consulte:

- [Sintaxis de Markdown de línea de base](https://daringfireball.net/projects/markdown/syntax)
- [Documentación de GFM](https://guides.github.com/features/mastering-markdown)

Markdown utiliza caracteres especiales como \*, \` y \# para dar formato. Si desea incluir uno de estos caracteres en el contenido, tiene dos opciones disponibles:

- Colocar una barra diagonal inversa antes del carácter especial para "aplicarle escape" (por ejemplo, `\*` para \*).
- Usar el [código de entidad HTML](https://www.ascii.cl/htmlcodes.htm) para el carácter (por ejemplo, `&#42;` para &#42;).

## <a name="file-name"></a>Nombre del archivo

Los nombres de archivo utilizan las siguientes reglas:

- Solo contienen letras minúsculas, números y guiones.
- No incluyen espacios ni signos de puntuación. Se usan guiones para separar palabras y números en el nombre de archivo.
- Se usan verbos de acción de uso específicos, como desarrollar, comparar, compilar, solucionar problemas. Ninguna palabra en gerundio.
- No se incluye ninguna palabra pequeña. No incluya a y, el, en, o, etcétera.
- Debe estar en Markdown y utilizar la extensión de archivo .md.
- Los nombres de archivo deben ser razonablemente cortos. Forman parte de la dirección URL para los artículos.

## <a name="headings"></a>Encabezados

Utilice mayúsculas y minúsculas de estilo de oración. Ponga en mayúscula la primera letra de la primera palabra de un título, los nombres propios y la primera letra que aparezca después de un signo de dos puntos (por ejemplo, "Tutorial: Predicción de precios mediante regresión con ML.NET").

No agregue un signo de dos puntos después de "Cómo" (por ejemplo, "Cómo ordenar una matriz" y no "Cómo: Ordenar una matriz").

Los encabezados deben realizarse con estilo atx, es decir, usar de uno a seis caracteres hash (#) al principio de la línea para indicar un título, correspondiente a los niveles de encabezados HTML de H1 a H6. Más arriba se pueden encontrar ejemplos de encabezados de primer y segundo nivel.

Solo **debe** haber un encabezado de primer nivel (H1) en el tema, que se mostrará como título en la página.

Si el encabezado termina en un carácter `#`, debe agregar un carácter de escape para que el título se represente correctamente. Por ejemplo: `# Async programming in F\#`.

Los encabezados de segundo nivel generarán la tabla de contenido en la página que aparece en la sección "En este artículo" debajo del título en la página.

### <a name="third-level-heading"></a>Encabezado de tercer nivel
#### <a name="fourth-level-heading"></a>Encabezado de cuarto nivel
##### <a name="fifth-level-heading"></a>Encabezado de quinto nivel
###### <a name="sixth-level-heading"></a>Encabezado de sexto nivel

## <a name="text-styling"></a>Estilo del texto

*Cursiva* Se utiliza para archivos, carpetas, rutas de acceso (si se trata de elementos largos, divídalos en su propia línea), términos nuevos.

**Negrita** Se utiliza para elementos de la UI.

`Code` Se utiliza para código alineado, palabras clave del lenguaje, nombres de paquetes de NuGet, comandos de la línea de comandos, nombres de columnas y tablas de bases de datos y direcciones URL en las que no quiere que se pueda hacer clic.

## <a name="links"></a>Vínculos

### <a name="internal-links"></a>Vínculos internos

Para vincular a un encabezado en el mismo archivo de Markdown (también conocido como vínculos de anclaje), debe obtener el identificador del encabezado al que está intentando vincular. Para confirmar el identificador, vea el origen del artículo representado, busque el identificador del encabezado (por ejemplo, `id="blockquote"`) y vincúlelo con # + identificador (por ejemplo, `#blockquote`).
El identificador se genera automáticamente basándose en el texto del encabezado. De esta manera, por ejemplo, dada una única sección denominada `## Step 2`, el identificador sería similar a `id="step-2"`.

- Ejemplo: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` genera [Declaración de bloques alineados con un identificador de lenguaje](#inline-code-blocks-with-language-identifier).

Para vincular a un archivo de Markdown en el mismo repositorio, utilice los [vínculos relativos](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), incluyendo el ".md" al final del nombre de archivo.

- Ejemplo: `[Readme file](../README.md)` genera un [archivo Léame](../README.md). (Tenga en cuenta que los vínculos distinguen mayúsculas de minúsculas).
- Ejemplo: `[Welcome to .NET](../docs/welcome.md)` genera [Bienvenido a .NET](../docs/welcome.md).

Para enlazar a un fichero de Markdown en el mismo repositorio, utilice el enlace relativo + enlace hashtag.

- Ejemplo: `[.NET Community](../docs/welcome.md#open-source)` genera [Comunidad de .NET](../docs/welcome.md#open-source).

En la mayoría de los casos, se usan los vínculos relativos y no se aconseja usar `~/` en ellos, porque los vínculos relativos se resuelven en el origen en GitHub. Sin embargo, cada vez que creemos un vínculo a un archivo en un repositorio dependiente, usaremos el carácter `~/` para proporcionar la ruta de acceso. Como los archivos del repositorio dependiente se encuentran en una ubicación distinta en GitHub, los vínculos no se resolverán correctamente con vínculos relativos, independientemente de cómo estén escritos.

La especificación del lenguaje de C# y la de Visual Basic se incluyen en la documentación de .NET mediante la inclusión del origen desde los repositorios de lenguajes. Los orígenes de Markdown se administran en los repositorios [csharplang](https://github.com/dotnet/csharplang) y [visual basic](https://github.com/dotnet/vblang).

Los vínculos a la especificación deben apuntar a los directorios de origen donde se incluyen esas especificaciones. En el caso de C#, es **~/_csharplang/spec** y, en VB, **~/_vblang/spec**.

- Ejemplo: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` genera [Expresiones de consulta de C#](~/_csharplang/spec/expressions.md#query-expressions).

### <a name="external-links"></a>Vínculos externos

Para vincular a un archivo externo, utilice la dirección URL completa como vínculo.

- Ejemplo: `[GitHub](https://www.github.com)` genera [GitHub](https://www.github.com).

Si aparece una dirección URL en un archivo de Markdown, se transformará en un vínculo.

- Ejemplo: `<https://www.github.com>` genera <https://www.github.com>.

Prefiera el protocolo `https` para los vínculos externos. Use solo vínculos `http` para los sitios que no admiten `https`.

### <a name="links-to-apis"></a>Vínculos a las API

El sistema de compilación tiene algunas extensiones que permiten vincular a las API de .NET sin tener que usar los vínculos externos.
Al vincular a una API, puede usar su identificador único (UID) que se genera automáticamente desde el código fuente.

El UID equivale al nombre de miembro y de tipo completo.

Si agrega un carácter \* (o %2A) después del UID, el vínculo representa la página de sobrecarga y no una API específica. Por ejemplo, puede usarlo cuando quiera establecer un vínculo a la página [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) de manera genérica en lugar de una sobrecarga específica como [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_). También puede usar \* para establecer un vínculo a una página de miembro cuando el miembro no está sobrecargado. Esto evitará que tenga que incluir la lista de parámetros en el UID.

Para establecer un vínculo a una sobrecarga de método específica, debe incluir el nombre de tipo completo de cada uno de los parámetros del método. Por ejemplo, \<xref:System.DateTime.ToString> establece un vínculo al método [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) sin parámetros, mientras que \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> establece un vínculo al método [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_). Puede encontrar los UID de un miembro sobrecargado específico desde <https://xref.docs.microsoft.com/autocomplete>. La cadena de consulta"?text= *\<type-member-name>* " identifica el tipo o miembro cuyos UID quiere ver. Por ejemplo, <https://xref.docs.microsoft.com/autocomplete?text=string.format> recupera las sobrecargas [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).

Para establecer un vínculo a un tipo genérico, como [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), puede usar el carácter \` (%60), seguido del número de parámetros de tipo genérico. Por ejemplo, \<xref:System.Nullable%601> establece un vínculo al tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), mientras que \<xref:System.Func%602> establece un vínculo al delegado [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).

Puede utilizar alguna de las siguientes sintaxis:

1. Vínculo automático: `<xref:UID>` o `<xref:UID?displayProperty=nameWithType>`

   El parámetro de consulta `displayProperty` genera un texto de vínculo completo. De manera predeterminada, el texto de vínculo solo muestra el nombre de miembro o de tipo.

2. Vínculo de Markdown: `[link text](xref:UID)`

   Úselo cuando quiera personalizar el texto de vínculo que se muestra.

Ejemplos:

- `<xref:System.String>` se representa como [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` se representa como [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` se representa como [String class](https://docs.microsoft.com/dotnet/api/system.string)

Para obtener más información acerca de cómo utilizar esta notación, consulte [Utilizar referencias cruzadas](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).

Hay dos maneras de encontrar el UID:

- Vea el código fuente de la página de API a la que quiere establecer un vínculo y busque el valor ms.assetid. Tenga en cuenta que los valores de sobrecarga individuales no aparecen en el código fuente.
- Use esta herramienta para buscar los UID: <https://xref.docs.microsoft.com/autocomplete?text=tostring> (reemplace tostring con partes del nombre de la API que intenta encontrar). La herramienta busca el parámetro de consulta `text` proporcionado en cualquier parte del UID. Por ejemplo, puede buscar el nombre de miembro (ToString), el nombre de miembro parcial (ToStri), el nombre de tipo y de miembro (Double.ToString), etc.

Cuando el UID contiene los caracteres especiales \`, \# o \*, el valor de UID debe estar codificado en HTML como `%60`, `%23` y `%2A`, respectivamente. En ocasiones verá paréntesis codificados, pero no es requisito.

Ejemplos:

- System.Threading.Tasks.Task\`1 se convierte en `System.Threading.Tasks.Task%601`.
- System.Exception.\#ctor se convierte en `System.Exception.%23ctor`.
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se convierte en `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`.

## <a name="lists"></a>Listas

### <a name="ordered-lists"></a>Listas ordenadas

1. Esto
1. Es
1. Una
1. Por orden
1. Lista

#### <a name="ordered-list-with-an-embedded-list"></a>Lista ordenada con una lista insertada

1. Aquí
1. viene
1. an
1. insertada
    1. Señora Beatriz
    1. Profesor Alcalá
1. ordered
1. lista

### <a name="unordered-lists"></a>Listas desordenadas

- Esto
- is
- a
- con viñetas
- lista

#### <a name="unordered-list-with-an-embedded-list"></a>Lista desordenada con una lista insertada

- Esto
- con viñetas
- lista
  - Sr. Valladares
  - Sr. Tórrez
- contains
- otras
  1. Coronel Valentín
  1. Sra. Blanco
- listas

## <a name="horizontal-rule"></a>Regla horizontal

---

## <a name="tables"></a>Tablas

| Tablas        | Son           | Geniales  |
| ------------- |:-------------:| -----:|
| col 3 está      | alineado a la derecha | 1600 $ |
| col 2 está      | centrado      |   $12 |
| col 1 está de forma predeterminada | alineado a la izquierda     |    1 $ |

Puede usar una [herramienta de generador de tabla de Markdown](https://www.tablesgenerator.com/markdown_tables) para ayudarle a crearlas más fácilmente.

## <a name="code"></a>Código

La mejor manera de incluir código es incluir fragmentos de código de un ejemplo funcional. Cree el ejemplo siguiendo las instrucciones de la [guía contribuyente](../CONTRIBUTING.md#contributing-to-samples).

Puede incluir el código con la sintaxis siguiente:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- `-<language>` (*opcional*, pero *recomendado*)
  - El lenguaje del fragmento de código al que se hace referencia. Si quiere ver una lista de los valores admitidos, consulte [Lenguajes admitidos](#supported-languages).

- `<name>` (*opcional*)
  - El nombre del fragmento de código. No tienen ningún impacto en el HTML de salida, pero lo puede usar para mejorar la legibilidad de su propio origen de Markdown.

- `<pathToFile>` (*obligatorio*)
  - Ruta de acceso relativa en el sistema de archivos que indica el archivo de fragmento de código al que se va a hacer referencia.

- `<queryoption>` y `<queryoptionvalue>` (*opcional*)
  - Se usan en conjunto para especificar cómo se debe recuperar el código desde el archivo:
    - `#`: `#L{startlinenumber}-L{endlinenumber}` (intervalo de líneas) *o* `#{tagname}` (nombre de etiqueta).
    No se recomienda usar números de línea, porque son muy complicados. La mejor manera de hacer referencia a fragmentos de código es el nombre de etiqueta.
    - `range`: `?range=1,3-5` Un intervalo de líneas. Este ejemplo incluye las líneas 1, 3, 4 y 5.
    - `dedent`: `?dedent=8` Aplica una sangría a las líneas según un número de espacios; en este caso, 8. Se puede combinar con `range` y otras opciones de consulta que seleccionan un subconjunto de las líneas de un archivo.
    - `outdent`: `?outdent=8` Invierte la sangría de las líneas según un número de espacios; en este caso, 8. Se puede combinar con `range` y otras opciones de consulta que seleccionan un subconjunto de las líneas de un archivo.

Se recomienda usar la opción de nombre de etiqueta siempre que sea posible. El nombre de etiqueta es el nombre de una región o de un comentario de código con el formato de `Snippettagname` presente en el código fuente. En el ejemplo siguiente se muestra cómo hacer referencia al nombre de etiqueta `1`:

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

Y puede ver cómo las etiquetas del fragmento de código están estructuradas en [este archivo de código fuente](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs). Para detalles sobre la representación de un nombre de etiqueta en los archivos de código fuente de un fragmento de código por lenguaje, consulte las [instrucciones de DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

Incluir fragmentos de programas completos garantiza que todo el código se ejecuta a través de nuestro sistema de integración continua (CI). Sin embargo, si necesita mostrar algo que causa errores de runtime o de tiempo de compilación, puede utilizar bloques de código alineados.

### <a name="inline-code-blocks-with-language-identifier"></a>Bloques de código alineados con el identificador de idioma

Utilice tres acentos graves (\`\`\`) + un identificador de lenguaje para aplicar la codificación de color específica del lenguaje a un bloque de código. Esta es la lista de lenguajes admitidos donde se muestra la etiqueta de Markdown para cada id. de lenguaje.

#### <a name="supported-languages"></a>Idiomas compatibles

|NOMBRE|Etiqueta de Markdown|
|-----|-------|
|Consola de .NET|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|Azure CLI|azurecli|
|AzCopy|azcopy|
|Azure PowerShell|azurepowershell|
|Bash|Bash|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|C# en el explorador|csharp-interactive|
|Consola|consola|
|CSHTML|cshtml|
|DAX|dax|
|Dockerfile|dockerfile|
|F#|fsharp|
|Ir|go|
|HTML|html|
|HTTP|http|
|Java|Java|
|JavaScript|javascript|
|JSON|json|
|Lenguaje de consulta de Kusto|kusto|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|protobuf|protobuf|
|PowerApps (punto como separador decimal)|powerapps-dot|
|PowerApps (coma como separador decimal)|powerapps-comma|
|PowerShell|powershell|
|Python|Python|
|Q#|qsharp|
|R|r|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|Visual Basic|vb|
|VBScript|vbscript|
|XAML|xaml|
|XML|xml|
|yml|yml|

El nombre `csharp-interactive` especifica el lenguaje C# y la capacidad de ejecutar los ejemplos desde el explorador. Estos fragmentos de código se compilan y ejecutan en un contenedor de Docker y los resultados de la ejecución del programa se muestran en la ventana del explorador del usuario.

Estos son ejemplos de bloques de código que usan los id. de lenguaje para (\`\`\`csharp), Python (\`\`\`python) y PowerShell (\`\`\`powershell).

##### <a name="c"></a>C\#

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a>Python

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a>PowerShell

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a>Bloque de código genérico

Utilice tres acentos graves (```) para la codificación de bloques de código genéricos.

> El enfoque recomendado es utilizar los bloques de código con los identificadores de lenguaje, como se explica en la sección anterior, para garantizar el resaltado de sintaxis correcto en la documentación del sitio. Utilice bloques de código genéricos solo cuando sea necesario.

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a>Blockquotes

> La sequía lleva existiendo diez millones de años y el reino de los terribles lagartos hace mucho que finalizó. Aquí en el Ecuador, en el continente que será un día conocido como África, la batalla por la existencia ha alcanzado un nuevo clímax de ferocidad, y el ganador aún no se ha mostrado. En este terreno estéril y desecado, solo los pequeños, los rápidos o los feroces podrían prosperar, o incluso esperar sobrevivir.

## <a name="images"></a>Imágenes

### <a name="static-image-or-animated-gif"></a>Gif animado o imagen estática

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![este es el texto alternativo](../images/Logo_DotNet.png)

### <a name="linked-image"></a>Imagen vinculada

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

[![texto alternativo para la imagen vinculada](../images/Logo_DotNet.png)](https://dot.net)

## <a name="videos"></a>Vídeos

Actualmente, puede insertar vídeos tanto de Channel 9 como de YouTube con la sintaxis siguiente:

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

Para obtener la dirección URL correcta del vídeo, seleccione la pestaña **Insertar** debajo del fotograma de vídeo y copie la dirección URL del elemento `<iframe>`. Por ejemplo:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Para obtener la dirección URL correcta del vídeo, haga clic con el botón derecho en el vídeo, seleccione **Copiar código para insertar** y copie la dirección URL del elemento `<iframe>`.

```markdown
> [!VIDEO <youtube_video_link>]
```

Por ejemplo:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>Extensiones de docs.microsoft

docs.microsoft proporciona algunas extensiones adicionales a Markdown característico de GitHub.

### <a name="alerts"></a>Alertas

Es importante usar los siguientes estilos de alerta, por lo que se representan con el estilo correspondiente en el sitio de documentación. Pero el motor de representación en GitHub no los diferencia.

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

Y se procesarán como esto: ![Estilos de alerta](../images/alerts.png)

### <a name="includes"></a>Incluye

Puede insertar el Markdown de un archivo en otro con Include.

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a>Listas comprobadas

Hay disponible un estilo personalizado para las listas. Puede representar las listas con marcas de verificación verdes.

> [!div class="checklist"]
>
> - Cómo crear una aplicación .NET Core
> - Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator
> - Cómo editar MyApp.csproj para agregar dependencias
> - Cómo agregar una clase y un XmlSerializer
> - Cómo compilar y ejecutar la aplicación

Puede ver un ejemplo de las listas comprobadas en acción en la [documentación de .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Botones

> [!div class="button"]
> [vínculos de botón](../docs/core/index.md)

Puede ver un ejemplo de los botones en acción en la [documentación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="selectors"></a>Selectores

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

Puede ver un ejemplo de los selectores en acción en la [documentación de Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).

### <a name="step-by-steps"></a>Paso a paso

>[!div class="step-by-step"]
>[Anterior](../docs/csharp/expression-trees-interpreting.md)
>[Siguiente](../docs/csharp/expression-trees-translating.md)

Puede ver un ejemplo de una guía paso a paso en acción en la [guía de C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
