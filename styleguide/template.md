---
title:
- TÍTULO DEL ARTÍCULO
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - mm/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: e6c912f5ff9590f3b8cbb0f7e3f88e08fa9dd556
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106910"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="bbfb2-102">Plantilla de Markdown y metadatos</span><span class="sxs-lookup"><span data-stu-id="bbfb2-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="bbfb2-103">Esta plantilla de dotnet/docs contiene ejemplos de sintaxis de Markdown, así como instrucciones sobre cómo establecer los metadatos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="bbfb2-104">Para sacar el máximo provecho de ella, debe ver el [Markdown sin formato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) y la [vista representada](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (por ejemplo, el Markdown sin formato muestra el bloque de metadatos, mientras que la vista representada no).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (for instance, the raw Markdown shows the metadata block, while the rendered view does not).</span></span>

<span data-ttu-id="bbfb2-105">Al crear un archivo de Markdown, debe copiar la plantilla en un archivo nuevo, rellenar los metadatos como se indica a continuación, configurar el encabezado H1 como se indica antes del título de este artículo y eliminar el contenido.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="bbfb2-106">Metadatos</span><span class="sxs-lookup"><span data-stu-id="bbfb2-106">Metadata</span></span>

<span data-ttu-id="bbfb2-107">Puede encontrar el bloque de metadatos completo más arriba (en el [Markdown sin formato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), dividido en los campos obligatorios y opcionales.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="bbfb2-108">Algunas notas claves:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-108">Some key notes:</span></span>

- <span data-ttu-id="bbfb2-109">**Debe** haber un espacio entre los dos puntos (:) y el valor de un elemento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="bbfb2-110">Si un elemento de metadatos no tiene valor, comente el elemento con el carácter # o quítelo (no lo deje en blanco ni use "na").</span><span class="sxs-lookup"><span data-stu-id="bbfb2-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="bbfb2-111">Si va a agregar un valor a un elemento que se comentó, asegúrese de quitar el carácter #.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="bbfb2-112">Dos puntos en un valor (por ejemplo, un título) interrumpen el analizador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="bbfb2-113">En este caso, encierre el título con comillas dobles (por ejemplo, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="bbfb2-114">**title**: aparece en los resultados del motor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="bbfb2-115">El título no debe ser idéntico al título en el encabezado H1 y debe contener 60 caracteres o menos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="bbfb2-116">**description**: resume el contenido del artículo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="bbfb2-117">Habitualmente aparece en la página de resultados de la búsqueda, pero no se usa para la clasificación de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="bbfb2-118">Debe tener entre 115 y 145 caracteres, incluidos los espacios.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="bbfb2-119">**author** y **ms.author**: el campo author debe contener el **nombre de usuario de GitHub** del autor, no su alias.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="bbfb2-120">Por otro lado, el campo **ms.author** debe contener un alias de Microsoft e indica al responsable de mantener el artículo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="bbfb2-121">**ms.topic**: el tipo de tema.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="bbfb2-122">El valor más común es `conceptual` y se establece en un nivel global.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="bbfb2-123">Otros valores comunes que se usan son `tutorial`, `overview` y `reference`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="bbfb2-124">**ms.devlang** define el filtro de lenguaje que se muestra para el tema.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-124">**ms.devlang** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="bbfb2-125">Puede ver una lista de los valores admitidos en la sección [Lenguajes admitidos](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="bbfb2-126">Solo se debe establecer cuando el tema abarca más de un lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="bbfb2-127">Por lo general, en nuestro contenido solo se usa `csharp`, `vb`, `fsharp` y `cpp` para este valor.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="bbfb2-128">**ms.prod**: identificación del producto que se usa con fines de inteligencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="bbfb2-129">Por lo general, se establecen en un nivel global, por lo que no suelen aparecer en el bloque de metadatos de cada artículo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="bbfb2-130">**ms.technology**: clasificación de inteligencia empresarial adicional.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="bbfb2-131">Algunos de los valores admitidos son: `devlang-csharp` para temas de C#, `devlang-fsharp` para temas de F# y `devlang-visual-basic` para temas de VB.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="bbfb2-132">Los valores variarán en otras guías, por lo que deberá pedir ayuda a un miembro del equipo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="bbfb2-133">**ms.date**: fecha con formato MM/DD/AAAA.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-133">**ms.date**: A date in the format MM/DD/YYYY.</span></span> <span data-ttu-id="bbfb2-134">Se muestra en la página publicada para indicar la última vez que el artículo se editó de manera sustancial o se garantizó como "actualizado" (es decir, la última vez que se revisó el artículo y se consideró como actualizado).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="bbfb2-135">**helpviewer_keywords**: las entradas se usan para los índices de libros sin conexión (una funcionalidad de Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="bbfb2-136">**f1_keywords**: conecta el artículo con la tecla F1 (una funcionalidad de Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="bbfb2-137">Markdown básico, GFM y caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="bbfb2-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="bbfb2-138">Todos los Markdown básicos y característicos de GitHub (GFM) son compatibles.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="bbfb2-139">Para obtener más información sobre este tema, consulte:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-139">For more information on these, see:</span></span>

- [<span data-ttu-id="bbfb2-140">Sintaxis de Markdown de línea de base</span><span class="sxs-lookup"><span data-stu-id="bbfb2-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="bbfb2-141">Documentación de GFM</span><span class="sxs-lookup"><span data-stu-id="bbfb2-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="bbfb2-142">Markdown utiliza caracteres especiales como \*, \` y \# para dar formato.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="bbfb2-143">Si desea incluir uno de estos caracteres en el contenido, tiene dos opciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="bbfb2-144">Colocar una barra diagonal inversa antes del carácter especial para "escapar" (por ejemplo, `\*` para un \*)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-144">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="bbfb2-145">Utilizar el [código de entidad HTML](https://www.ascii.cl/htmlcodes.htm) para el carácter (por ejemplo, `&#42;` para un \*).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="bbfb2-146">Nombre del archivo</span><span class="sxs-lookup"><span data-stu-id="bbfb2-146">File name</span></span>

<span data-ttu-id="bbfb2-147">Los nombres de archivo utilizan las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-147">File names use the following rules:</span></span>

- <span data-ttu-id="bbfb2-148">Solo contienen letras minúsculas, números y guiones.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="bbfb2-149">No incluyen espacios ni signos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="bbfb2-150">Se usan guiones para separar palabras y números en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="bbfb2-151">Se usan verbos de acción de uso específicos, como desarrollar, comparar, compilar, solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="bbfb2-152">Ninguna palabra en gerundio.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-152">No -ing words.</span></span>
- <span data-ttu-id="bbfb2-153">No se incluye ninguna palabra pequeña. No incluya a y, el, en, o, etcétera.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="bbfb2-154">Debe estar en Markdown y utilizar la extensión de archivo .md.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="bbfb2-155">Los nombres de archivo deben ser razonablemente cortos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-155">Keep file names reasonably short.</span></span> <span data-ttu-id="bbfb2-156">Forman parte de la dirección URL para los artículos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="bbfb2-157">Encabezados</span><span class="sxs-lookup"><span data-stu-id="bbfb2-157">Headings</span></span>

<span data-ttu-id="bbfb2-158">Utilice mayúsculas y minúsculas de estilo de oración.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="bbfb2-159">Utilice siempre mayúscula en:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-159">Always capitalize:</span></span>

- <span data-ttu-id="bbfb2-160">La primera palabra de un encabezado.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-160">The first word of a heading.</span></span>
- <span data-ttu-id="bbfb2-161">La palabra que sigue a un signo de dos puntos en un título o un encabezado (por ejemplo, "Cómo: Ordenar una matriz").</span><span class="sxs-lookup"><span data-stu-id="bbfb2-161">The word following a colon in a title or heading (for example, "How to: Sort an array").</span></span>

<span data-ttu-id="bbfb2-162">Los encabezados deben realizarse con estilo atx, es decir, usar de uno a seis caracteres hash (#) al principio de la línea para indicar un título, correspondiente a los niveles de encabezados HTML de H1 a H6.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-162">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="bbfb2-163">Más arriba se pueden encontrar ejemplos de encabezados de primer y segundo nivel.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-163">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="bbfb2-164">Solo **debe** haber un encabezado de primer nivel (H1) en el tema, que se mostrará como título en la página.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-164">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="bbfb2-165">Si el encabezado finaliza con un carácter `#`, debe agregar un carácter `#` adicional al final para que el título se represente correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-165">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="bbfb2-166">Por ejemplo: `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-166">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="bbfb2-167">Los encabezados de segundo nivel generarán la tabla de contenido en la página que aparece en la sección "En este artículo" debajo del título en la página.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-167">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="bbfb2-168">Encabezado de tercer nivel</span><span class="sxs-lookup"><span data-stu-id="bbfb2-168">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="bbfb2-169">Encabezado de cuarto nivel</span><span class="sxs-lookup"><span data-stu-id="bbfb2-169">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="bbfb2-170">Encabezado de quinto nivel</span><span class="sxs-lookup"><span data-stu-id="bbfb2-170">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="bbfb2-171">Encabezado de sexto nivel</span><span class="sxs-lookup"><span data-stu-id="bbfb2-171">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="bbfb2-172">Estilo del texto</span><span class="sxs-lookup"><span data-stu-id="bbfb2-172">Text styling</span></span>

<span data-ttu-id="bbfb2-173">*Cursiva* Se utiliza para archivos, carpetas, rutas de acceso (si se trata de elementos largos, divídalos en su propia línea), términos nuevos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-173">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="bbfb2-174">**Negrita** Se utiliza para elementos de la UI.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-174">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="bbfb2-175">`Code` Se utiliza para código alineado, palabras clave del lenguaje, nombres de paquetes de NuGet, comandos de la línea de comandos, nombres de columnas y tablas de bases de datos y direcciones URL en las que no quiere que se pueda hacer clic.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-175">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="bbfb2-176">Vínculos</span><span class="sxs-lookup"><span data-stu-id="bbfb2-176">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="bbfb2-177">Vínculos internos</span><span class="sxs-lookup"><span data-stu-id="bbfb2-177">Internal Links</span></span>

<span data-ttu-id="bbfb2-178">Para vincular a un encabezado en el mismo archivo de Markdown (también conocido como vínculos de anclaje), debe obtener el identificador del encabezado al que está intentando vincular.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-178">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="bbfb2-179">Para confirmar el identificador, vea el origen del artículo representado, busque el identificador del encabezado (por ejemplo, `id="blockquote"`) y vincúlelo con # + identificador (por ejemplo, `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-179">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="bbfb2-180">El identificador se genera automáticamente basándose en el texto del encabezado.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-180">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="bbfb2-181">De esta manera, por ejemplo, dada una única sección denominada `## Step 2`, el identificador sería similar a `id="step-2"`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-181">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="bbfb2-182">Ejemplo: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` genera [Declaración de bloques alineados con un identificador de lenguaje](#inline-code-blocks-with-language-identifier).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-182">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="bbfb2-183">Para vincular a un archivo de Markdown en el mismo repositorio, utilice los [vínculos relativos](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), incluyendo el ".md" al final del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-183">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="bbfb2-184">Ejemplo: `[Readme file](../README.md)` genera un [archivo Léame](../README.md).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-184">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="bbfb2-185">(Tenga en cuenta que los vínculos distinguen mayúsculas de minúsculas).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-185">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="bbfb2-186">Ejemplo: `[Welcome to .NET](../docs/welcome.md)` genera [Bienvenido a .NET](../docs/welcome.md).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-186">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="bbfb2-187">Para enlazar a un fichero de Markdown en el mismo repositorio, utilice el enlace relativo + enlace hashtag.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-187">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="bbfb2-188">Ejemplo: `[.NET Community](../docs/welcome.md#open-source)` genera [Comunidad de .NET](../docs/welcome.md#open-source).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-188">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="bbfb2-189">En la mayoría de los casos, se usan los vínculos relativos y no se aconseja usar `~/` en ellos, porque los vínculos relativos se resuelven en el origen en GitHub.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-189">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="bbfb2-190">Sin embargo, cada vez que creemos un vínculo a un archivo en un repositorio dependiente, usaremos el carácter `~/` para proporcionar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-190">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="bbfb2-191">Como los archivos del repositorio dependiente se encuentran en una ubicación distinta en GitHub, los vínculos no se resolverán correctamente con vínculos relativos, independientemente de cómo estén escritos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-191">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="bbfb2-192">La especificación del lenguaje de C# y la de Visual Basic se incluyen en la documentación de .NET mediante la inclusión del origen desde los repositorios de lenguajes.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-192">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="bbfb2-193">Los orígenes de Markdown se administran en los repositorios [csharplang](https://github.com/dotnet/csharplang) y [visual basic](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-193">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="bbfb2-194">Los vínculos a la especificación deben apuntar a los directorios de origen donde se incluyen esas especificaciones.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-194">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="bbfb2-195">En el caso de C#, es **~/_csharplang/spec** y, en VB, **~/_vblang/spec**.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-195">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="bbfb2-196">Ejemplo: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` genera [Expresiones de consulta de C#](~/_csharplang/spec/expressions.md#query-expressions).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-196">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="bbfb2-197">Vínculos externos</span><span class="sxs-lookup"><span data-stu-id="bbfb2-197">External Links</span></span>

<span data-ttu-id="bbfb2-198">Para vincular a un archivo externo, utilice la dirección URL completa como vínculo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-198">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="bbfb2-199">Ejemplo: `[GitHub](https://www.github.com)` genera [GitHub](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-199">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="bbfb2-200">Si aparece una dirección URL en un archivo de Markdown, se transformará en un vínculo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-200">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="bbfb2-201">Ejemplo: `<https://www.github.com>` genera <https://www.github.com>.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-201">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="bbfb2-202">Prefiera el protocolo `https` para los vínculos externos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-202">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="bbfb2-203">Use solo vínculos `http` para los sitios que no admiten `https`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-203">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="bbfb2-204">Vínculos a las API</span><span class="sxs-lookup"><span data-stu-id="bbfb2-204">Links to APIs</span></span>

<span data-ttu-id="bbfb2-205">El sistema de compilación tiene algunas extensiones que permiten vincular a las API de .NET sin tener que usar los vínculos externos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-205">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="bbfb2-206">Al vincular a una API, puede usar su identificador único (UID) que se genera automáticamente desde el código fuente.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-206">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="bbfb2-207">El UID equivale al nombre de miembro y de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-207">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="bbfb2-208">Si agrega un carácter \* (o %2A) después del UID, el vínculo representa la página de sobrecarga y no una API específica.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-208">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="bbfb2-209">Por ejemplo, puede usarlo cuando quiera establecer un vínculo a la página [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) de manera genérica en lugar de una sobrecarga específica como [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-209">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="bbfb2-210">También puede usar \* para establecer un vínculo a una página de miembro cuando el miembro no está sobrecargado. Esto evitará que tenga que incluir la lista de parámetros en el UID.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-210">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="bbfb2-211">Para establecer un vínculo a una sobrecarga de método específica, debe incluir el nombre de tipo completo de cada uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-211">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="bbfb2-212">Por ejemplo, \<xref:System.DateTime.ToString> establece un vínculo al método [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) sin parámetros, mientras que \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> establece un vínculo al método [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-212">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="bbfb2-213">Puede encontrar los UID de un miembro sobrecargado específico desde `https://xref.docs.microsoft.com/autocomplete`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-213">You can find the UIDs of a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="bbfb2-214">La cadena de consulta"?text= *\<type-member-name>* " identifica el tipo o miembro cuyos UID quiere ver.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-214">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="bbfb2-215">Por ejemplo, `https://xref.docs.microsoft.com/autocomplete?text=string.format` recupera las sobrecargas [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-215">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="bbfb2-216">Para establecer un vínculo a un tipo genérico, como [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), puede usar el carácter \` (%60), seguido del número de parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-216">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="bbfb2-217">Por ejemplo, \<xref:System.Nullable%601> establece un vínculo al tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), mientras que \<xref:System.Func%602> establece un vínculo al delegado [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-217">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="bbfb2-218">Puede utilizar alguna de las siguientes sintaxis:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-218">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="bbfb2-219">Vínculo automático: `<xref:UID>` o `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="bbfb2-219">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="bbfb2-220">El parámetro de consulta `displayProperty` genera un texto de vínculo completo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-220">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="bbfb2-221">De manera predeterminada, el texto de vínculo solo muestra el nombre de miembro o de tipo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-221">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="bbfb2-222">Vínculo de Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="bbfb2-222">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="bbfb2-223">Úselo cuando quiera personalizar el texto de vínculo que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-223">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="bbfb2-224">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-224">Examples:</span></span>

- <span data-ttu-id="bbfb2-225">`<xref:System.String>` se representa como [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-225">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="bbfb2-226">`<xref:System.String?displayProperty=nameWithType>` se representa como [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-226">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="bbfb2-227">`[String class](xref:System.String)` se representa como [String class](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-227">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="bbfb2-228">Para obtener más información acerca de cómo utilizar esta notación, consulte [Utilizar referencias cruzadas](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-228">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="bbfb2-229">Hay dos maneras de encontrar el UID:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-229">There are two ways to find the UID:</span></span>

- <span data-ttu-id="bbfb2-230">Vea el código fuente de la página de API a la que quiere establecer un vínculo y busque el valor ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-230">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="bbfb2-231">Tenga en cuenta que los valores de sobrecarga individuales no aparecen en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-231">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="bbfb2-232">Use esta herramienta para buscar los UID: https://xref.docs.microsoft.com/autocomplete?text=tostring (reemplace tostring con partes del nombre de la API que intenta encontrar).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-232">Use the following tool to search for UIDs: https://xref.docs.microsoft.com/autocomplete?text=tostring (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="bbfb2-233">La herramienta busca el parámetro de consulta `text` proporcionado en cualquier parte del UID.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-233">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="bbfb2-234">Por ejemplo, puede buscar el nombre de miembro (ToString), el nombre de miembro parcial (ToStri), el nombre de tipo y de miembro (Double.ToString), etc.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-234">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="bbfb2-235">Cuando el UID contiene los caracteres especiales \`, \# o \*, el valor de UID debe estar codificado en HTML como `%60`, `%23` y `%2A`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-235">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="bbfb2-236">En ocasiones verá paréntesis codificados, pero no es requisito.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-236">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="bbfb2-237">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-237">Examples:</span></span>

- <span data-ttu-id="bbfb2-238">System.Threading.Tasks.Task\`1 se convierte en `System.Threading.Tasks.Task%601`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-238">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="bbfb2-239">System.Exception.\#ctor se convierte en `System.Exception.%23ctor`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-239">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="bbfb2-240">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se convierte en `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-240">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="bbfb2-241">Listas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-241">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="bbfb2-242">Listas ordenadas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-242">Ordered lists</span></span>

1. <span data-ttu-id="bbfb2-243">Esto</span><span class="sxs-lookup"><span data-stu-id="bbfb2-243">This</span></span>
1. <span data-ttu-id="bbfb2-244">Es</span><span class="sxs-lookup"><span data-stu-id="bbfb2-244">Is</span></span>
1. <span data-ttu-id="bbfb2-245">Una</span><span class="sxs-lookup"><span data-stu-id="bbfb2-245">An</span></span>
1. <span data-ttu-id="bbfb2-246">Por orden</span><span class="sxs-lookup"><span data-stu-id="bbfb2-246">Ordered</span></span>
1. <span data-ttu-id="bbfb2-247">Lista</span><span class="sxs-lookup"><span data-stu-id="bbfb2-247">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="bbfb2-248">Lista ordenada con una lista insertada</span><span class="sxs-lookup"><span data-stu-id="bbfb2-248">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="bbfb2-249">Aquí</span><span class="sxs-lookup"><span data-stu-id="bbfb2-249">Here</span></span>
1. <span data-ttu-id="bbfb2-250">viene</span><span class="sxs-lookup"><span data-stu-id="bbfb2-250">comes</span></span>
1. <span data-ttu-id="bbfb2-251">an</span><span class="sxs-lookup"><span data-stu-id="bbfb2-251">an</span></span>
1. <span data-ttu-id="bbfb2-252">insertada</span><span class="sxs-lookup"><span data-stu-id="bbfb2-252">embedded</span></span>
    1. <span data-ttu-id="bbfb2-253">Señora Beatriz</span><span class="sxs-lookup"><span data-stu-id="bbfb2-253">Miss Scarlett</span></span>
    1. <span data-ttu-id="bbfb2-254">Profesor Alcalá</span><span class="sxs-lookup"><span data-stu-id="bbfb2-254">Professor Plum</span></span>
1. <span data-ttu-id="bbfb2-255">ordered</span><span class="sxs-lookup"><span data-stu-id="bbfb2-255">ordered</span></span>
1. <span data-ttu-id="bbfb2-256">lista</span><span class="sxs-lookup"><span data-stu-id="bbfb2-256">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="bbfb2-257">Listas desordenadas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-257">Unordered Lists</span></span>

- <span data-ttu-id="bbfb2-258">Esto</span><span class="sxs-lookup"><span data-stu-id="bbfb2-258">This</span></span>
- <span data-ttu-id="bbfb2-259">is</span><span class="sxs-lookup"><span data-stu-id="bbfb2-259">is</span></span>
- <span data-ttu-id="bbfb2-260">a</span><span class="sxs-lookup"><span data-stu-id="bbfb2-260">a</span></span>
- <span data-ttu-id="bbfb2-261">con viñetas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-261">bulleted</span></span>
- <span data-ttu-id="bbfb2-262">lista</span><span class="sxs-lookup"><span data-stu-id="bbfb2-262">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="bbfb2-263">Lista desordenada con una lista insertada</span><span class="sxs-lookup"><span data-stu-id="bbfb2-263">Unordered list with an embedded list</span></span>

- <span data-ttu-id="bbfb2-264">Esto</span><span class="sxs-lookup"><span data-stu-id="bbfb2-264">This</span></span>
- <span data-ttu-id="bbfb2-265">con viñetas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-265">bulleted</span></span>
- <span data-ttu-id="bbfb2-266">lista</span><span class="sxs-lookup"><span data-stu-id="bbfb2-266">list</span></span>
  - <span data-ttu-id="bbfb2-267">Sr. Valladares</span><span class="sxs-lookup"><span data-stu-id="bbfb2-267">Mrs. Peacock</span></span>
  - <span data-ttu-id="bbfb2-268">Sr. Tórrez</span><span class="sxs-lookup"><span data-stu-id="bbfb2-268">Mr. Green</span></span>
- <span data-ttu-id="bbfb2-269">contains</span><span class="sxs-lookup"><span data-stu-id="bbfb2-269">contains</span></span>
- <span data-ttu-id="bbfb2-270">otras</span><span class="sxs-lookup"><span data-stu-id="bbfb2-270">other</span></span>
  1. <span data-ttu-id="bbfb2-271">Coronel Valentín</span><span class="sxs-lookup"><span data-stu-id="bbfb2-271">Colonel Mustard</span></span>
  1. <span data-ttu-id="bbfb2-272">Sra. Blanco</span><span class="sxs-lookup"><span data-stu-id="bbfb2-272">Mrs. White</span></span>
- <span data-ttu-id="bbfb2-273">listas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-273">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="bbfb2-274">Regla horizontal</span><span class="sxs-lookup"><span data-stu-id="bbfb2-274">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="bbfb2-275">Tablas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-275">Tables</span></span>

| <span data-ttu-id="bbfb2-276">Tablas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-276">Tables</span></span>        | <span data-ttu-id="bbfb2-277">Son</span><span class="sxs-lookup"><span data-stu-id="bbfb2-277">Are</span></span>           | <span data-ttu-id="bbfb2-278">Geniales</span><span class="sxs-lookup"><span data-stu-id="bbfb2-278">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="bbfb2-279">col 3 está</span><span class="sxs-lookup"><span data-stu-id="bbfb2-279">col 3 is</span></span>      | <span data-ttu-id="bbfb2-280">alineado a la derecha</span><span class="sxs-lookup"><span data-stu-id="bbfb2-280">right-aligned</span></span> | <span data-ttu-id="bbfb2-281">1600 $</span><span class="sxs-lookup"><span data-stu-id="bbfb2-281">$1600</span></span> |
| <span data-ttu-id="bbfb2-282">col 2 está</span><span class="sxs-lookup"><span data-stu-id="bbfb2-282">col 2 is</span></span>      | <span data-ttu-id="bbfb2-283">centrado</span><span class="sxs-lookup"><span data-stu-id="bbfb2-283">centered</span></span>      |   <span data-ttu-id="bbfb2-284">$12</span><span class="sxs-lookup"><span data-stu-id="bbfb2-284">$12</span></span> |
| <span data-ttu-id="bbfb2-285">col 1 está de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="bbfb2-285">col 1 is default</span></span> | <span data-ttu-id="bbfb2-286">alineado a la izquierda</span><span class="sxs-lookup"><span data-stu-id="bbfb2-286">left-aligned</span></span>     |    <span data-ttu-id="bbfb2-287">1 $</span><span class="sxs-lookup"><span data-stu-id="bbfb2-287">$1</span></span> |

<span data-ttu-id="bbfb2-288">Puede usar una [herramienta de generador de tabla de Markdown](https://www.tablesgenerator.com/markdown_tables) para ayudarle a crearlas más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-288">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="bbfb2-289">Código</span><span class="sxs-lookup"><span data-stu-id="bbfb2-289">Code</span></span>

<span data-ttu-id="bbfb2-290">La mejor manera de incluir código es incluir fragmentos de código de un ejemplo funcional.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-290">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="bbfb2-291">Cree el ejemplo siguiendo las instrucciones de la [guía contribuyente](../CONTRIBUTING.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-291">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="bbfb2-292">Puede incluir el código con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-292">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="bbfb2-293">`-<language>` (*opcional*, pero *recomendado*)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-293">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="bbfb2-294">El lenguaje del fragmento de código al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-294">Language of the code snippet being referenced.</span></span> <span data-ttu-id="bbfb2-295">Si quiere ver una lista de los valores admitidos, consulte [Lenguajes admitidos](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-295">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="bbfb2-296">`<name>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-296">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="bbfb2-297">El nombre del fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-297">Name for the code snippet.</span></span> <span data-ttu-id="bbfb2-298">No tienen ningún impacto en el HTML de salida, pero lo puede usar para mejorar la legibilidad de su propio origen de Markdown.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-298">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="bbfb2-299">`<pathToFile>` (*obligatorio*)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-299">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="bbfb2-300">Ruta de acceso relativa en el sistema de archivos que indica el archivo de fragmento de código al que se va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-300">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="bbfb2-301">`<queryoption>` y `<queryoptionvalue>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-301">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="bbfb2-302">Se usan en conjunto para especificar cómo se debe recuperar el código desde el archivo:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-302">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="bbfb2-303">`#`: `#L{startlinenumber}-L{endlinenumber}` (intervalo de líneas) *o* `#{tagname}` (nombre de etiqueta).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-303">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="bbfb2-304">No se recomienda usar números de línea, porque son muy complicados.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-304">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="bbfb2-305">La mejor manera de hacer referencia a fragmentos de código es el nombre de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-305">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="bbfb2-306">`range`: `?range=1,3-5` Un intervalo de líneas.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-306">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="bbfb2-307">Este ejemplo incluye las líneas 1, 3, 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-307">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="bbfb2-308">`dedent`: `?dedent=8` Aplica una sangría a las líneas según un número de espacios; en este caso, 8.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-308">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="bbfb2-309">Se puede combinar con `range` y otras opciones de consulta que seleccionan un subconjunto de las líneas de un archivo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-309">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="bbfb2-310">`outdent`: `?outdent=8` Invierte la sangría de las líneas según un número de espacios; en este caso, 8.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-310">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="bbfb2-311">Se puede combinar con `range` y otras opciones de consulta que seleccionan un subconjunto de las líneas de un archivo.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-311">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="bbfb2-312">Se recomienda usar la opción de nombre de etiqueta siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-312">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="bbfb2-313">El nombre de etiqueta es el nombre de una región o de un comentario de código con el formato de `Snippettagname` presente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-313">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="bbfb2-314">En el ejemplo siguiente se muestra cómo hacer referencia al nombre de etiqueta `1`:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-314">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="bbfb2-315">Y puede ver cómo las etiquetas del fragmento de código están estructuradas en [este archivo de código fuente](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-315">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="bbfb2-316">Para detalles sobre la representación de un nombre de etiqueta en los archivos de código fuente de un fragmento de código por lenguaje, consulte las [instrucciones de DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-316">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="bbfb2-317">Incluir fragmentos de programas completos garantiza que todo el código se ejecuta a través de nuestro sistema de integración continua (CI).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-317">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="bbfb2-318">Sin embargo, si necesita mostrar algo que causa errores de runtime o de tiempo de compilación, puede utilizar bloques de código alineados.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-318">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="bbfb2-319">Bloques de código alineados con el identificador de idioma</span><span class="sxs-lookup"><span data-stu-id="bbfb2-319">Inline code blocks with language identifier</span></span>

<span data-ttu-id="bbfb2-320">Utilice tres acentos graves (\`\`\`) + un identificador de lenguaje para aplicar la codificación de color específica del lenguaje a un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-320">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="bbfb2-321">Esta es la lista de lenguajes admitidos donde se muestra la etiqueta de Markdown para cada id. de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-321">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="bbfb2-322">Idiomas compatibles</span><span class="sxs-lookup"><span data-stu-id="bbfb2-322">Supported languages</span></span>

|<span data-ttu-id="bbfb2-323">nombre</span><span class="sxs-lookup"><span data-stu-id="bbfb2-323">Name</span></span>|<span data-ttu-id="bbfb2-324">Etiqueta de Markdown</span><span class="sxs-lookup"><span data-stu-id="bbfb2-324">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="bbfb2-325">ASP.NET con C#</span><span class="sxs-lookup"><span data-stu-id="bbfb2-325">ASP.NET with C#</span></span>|<span data-ttu-id="bbfb2-326">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="bbfb2-326">aspx-csharp</span></span>|
|<span data-ttu-id="bbfb2-327">ASP.NET con VB</span><span class="sxs-lookup"><span data-stu-id="bbfb2-327">ASP.NET with VB</span></span>|<span data-ttu-id="bbfb2-328">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="bbfb2-328">aspx-vb</span></span>|
|<span data-ttu-id="bbfb2-329">CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="bbfb2-329">Azure CLI</span></span>|<span data-ttu-id="bbfb2-330">azurecli</span><span class="sxs-lookup"><span data-stu-id="bbfb2-330">azurecli</span></span>|
|<span data-ttu-id="bbfb2-331">AzCopy</span><span class="sxs-lookup"><span data-stu-id="bbfb2-331">AzCopy</span></span>|<span data-ttu-id="bbfb2-332">azcopy</span><span class="sxs-lookup"><span data-stu-id="bbfb2-332">azcopy</span></span>|
|<span data-ttu-id="bbfb2-333">C++</span><span class="sxs-lookup"><span data-stu-id="bbfb2-333">C++</span></span>|<span data-ttu-id="bbfb2-334">cpp</span><span class="sxs-lookup"><span data-stu-id="bbfb2-334">cpp</span></span>|
|<span data-ttu-id="bbfb2-335">C#</span><span class="sxs-lookup"><span data-stu-id="bbfb2-335">C#</span></span>|<span data-ttu-id="bbfb2-336">csharp</span><span class="sxs-lookup"><span data-stu-id="bbfb2-336">csharp</span></span>|
|<span data-ttu-id="bbfb2-337">C# en el explorador</span><span class="sxs-lookup"><span data-stu-id="bbfb2-337">C# in browser</span></span>|<span data-ttu-id="bbfb2-338">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="bbfb2-338">csharp-interactive</span></span>|
|<span data-ttu-id="bbfb2-339">Consola</span><span class="sxs-lookup"><span data-stu-id="bbfb2-339">Console</span></span>|<span data-ttu-id="bbfb2-340">consola</span><span class="sxs-lookup"><span data-stu-id="bbfb2-340">console</span></span>|
|<span data-ttu-id="bbfb2-341">F#</span><span class="sxs-lookup"><span data-stu-id="bbfb2-341">F#</span></span>|<span data-ttu-id="bbfb2-342">fsharp</span><span class="sxs-lookup"><span data-stu-id="bbfb2-342">fsharp</span></span>|
|<span data-ttu-id="bbfb2-343">Java</span><span class="sxs-lookup"><span data-stu-id="bbfb2-343">Java</span></span>|<span data-ttu-id="bbfb2-344">Java</span><span class="sxs-lookup"><span data-stu-id="bbfb2-344">java</span></span>|
|<span data-ttu-id="bbfb2-345">JavaScript</span><span class="sxs-lookup"><span data-stu-id="bbfb2-345">JavaScript</span></span>|<span data-ttu-id="bbfb2-346">javascript</span><span class="sxs-lookup"><span data-stu-id="bbfb2-346">javascript</span></span>|
|<span data-ttu-id="bbfb2-347">JSON</span><span class="sxs-lookup"><span data-stu-id="bbfb2-347">JSON</span></span>|<span data-ttu-id="bbfb2-348">json</span><span class="sxs-lookup"><span data-stu-id="bbfb2-348">json</span></span>|
|<span data-ttu-id="bbfb2-349">NodeJS</span><span class="sxs-lookup"><span data-stu-id="bbfb2-349">NodeJS</span></span>|<span data-ttu-id="bbfb2-350">nodejs</span><span class="sxs-lookup"><span data-stu-id="bbfb2-350">nodejs</span></span>|
|<span data-ttu-id="bbfb2-351">Objective-C</span><span class="sxs-lookup"><span data-stu-id="bbfb2-351">Objective-C</span></span>|<span data-ttu-id="bbfb2-352">objc</span><span class="sxs-lookup"><span data-stu-id="bbfb2-352">objc</span></span>|
|<span data-ttu-id="bbfb2-353">PHP</span><span class="sxs-lookup"><span data-stu-id="bbfb2-353">PHP</span></span>|<span data-ttu-id="bbfb2-354">php</span><span class="sxs-lookup"><span data-stu-id="bbfb2-354">php</span></span>|
|<span data-ttu-id="bbfb2-355">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbfb2-355">PowerShell</span></span>|<span data-ttu-id="bbfb2-356">powershell</span><span class="sxs-lookup"><span data-stu-id="bbfb2-356">powershell</span></span>|
|<span data-ttu-id="bbfb2-357">Python</span><span class="sxs-lookup"><span data-stu-id="bbfb2-357">Python</span></span>|<span data-ttu-id="bbfb2-358">Python</span><span class="sxs-lookup"><span data-stu-id="bbfb2-358">python</span></span>|
|<span data-ttu-id="bbfb2-359">Ruby</span><span class="sxs-lookup"><span data-stu-id="bbfb2-359">Ruby</span></span>|<span data-ttu-id="bbfb2-360">ruby</span><span class="sxs-lookup"><span data-stu-id="bbfb2-360">ruby</span></span>|
|<span data-ttu-id="bbfb2-361">SQL</span><span class="sxs-lookup"><span data-stu-id="bbfb2-361">SQL</span></span>|<span data-ttu-id="bbfb2-362">sql</span><span class="sxs-lookup"><span data-stu-id="bbfb2-362">sql</span></span>|
|<span data-ttu-id="bbfb2-363">Swift</span><span class="sxs-lookup"><span data-stu-id="bbfb2-363">Swift</span></span>|<span data-ttu-id="bbfb2-364">swift</span><span class="sxs-lookup"><span data-stu-id="bbfb2-364">swift</span></span>|
|<span data-ttu-id="bbfb2-365">VB</span><span class="sxs-lookup"><span data-stu-id="bbfb2-365">VB</span></span>|<span data-ttu-id="bbfb2-366">vb</span><span class="sxs-lookup"><span data-stu-id="bbfb2-366">vb</span></span>|
|<span data-ttu-id="bbfb2-367">XAML</span><span class="sxs-lookup"><span data-stu-id="bbfb2-367">XAML</span></span>|<span data-ttu-id="bbfb2-368">xaml</span><span class="sxs-lookup"><span data-stu-id="bbfb2-368">xaml</span></span>|
|<span data-ttu-id="bbfb2-369">XML</span><span class="sxs-lookup"><span data-stu-id="bbfb2-369">XML</span></span>|<span data-ttu-id="bbfb2-370">xml</span><span class="sxs-lookup"><span data-stu-id="bbfb2-370">xml</span></span>|

<span data-ttu-id="bbfb2-371">El nombre `csharp-interactive` especifica el lenguaje C# y la capacidad de ejecutar los ejemplos desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-371">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="bbfb2-372">Estos fragmentos de código se compilan y ejecutan en un contenedor de Docker y los resultados de la ejecución del programa se muestran en la ventana del explorador del usuario.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-372">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="bbfb2-373">Estos son ejemplos de bloques de código que usan los id. de lenguaje para (\`\`\`csharp), Python (\`\`\`python) y PowerShell (\`\`\`powershell).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-373">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c9839"></a><span data-ttu-id="bbfb2-374">C&#9839;</span><span class="sxs-lookup"><span data-stu-id="bbfb2-374">C&#9839;</span></span>

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

#### <a name="python"></a><span data-ttu-id="bbfb2-375">Python</span><span class="sxs-lookup"><span data-stu-id="bbfb2-375">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="bbfb2-376">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbfb2-376">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="bbfb2-377">Bloque de código genérico</span><span class="sxs-lookup"><span data-stu-id="bbfb2-377">Generic code block</span></span>

<span data-ttu-id="bbfb2-378">Utilice tres acentos graves (\`\`\`) para la codificación de bloques de código genéricos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-378">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="bbfb2-379">El enfoque recomendado es utilizar los bloques de código con los identificadores de lenguaje, como se explica en la sección anterior, para garantizar el resaltado de sintaxis correcto en la documentación del sitio.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-379">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="bbfb2-380">Utilice bloques de código genéricos solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-380">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="bbfb2-381">Blockquotes</span><span class="sxs-lookup"><span data-stu-id="bbfb2-381">Blockquotes</span></span>

> <span data-ttu-id="bbfb2-382">La sequía lleva existiendo diez millones de años y el reino de los terribles lagartos hace mucho que finalizó.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-382">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="bbfb2-383">Aquí en el Ecuador, en el continente que será un día conocido como África, la batalla por la existencia ha alcanzado un nuevo clímax de ferocidad, y el ganador aún no se ha mostrado.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-383">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="bbfb2-384">En este terreno estéril y desecado, solo los pequeños, los rápidos o los feroces podrían prosperar, o incluso esperar sobrevivir.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-384">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="bbfb2-385">Imágenes</span><span class="sxs-lookup"><span data-stu-id="bbfb2-385">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="bbfb2-386">Gif animado o imagen estática</span><span class="sxs-lookup"><span data-stu-id="bbfb2-386">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![este es el texto alternativo](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="bbfb2-388">Imagen vinculada</span><span class="sxs-lookup"><span data-stu-id="bbfb2-388">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="bbfb2-389">[![texto alternativo para la imagen vinculada](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-389">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="bbfb2-390">Vídeos</span><span class="sxs-lookup"><span data-stu-id="bbfb2-390">Videos</span></span>

<span data-ttu-id="bbfb2-391">Actualmente, puede insertar vídeos tanto de Channel 9 como de YouTube con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-391">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="bbfb2-392">Channel 9</span><span class="sxs-lookup"><span data-stu-id="bbfb2-392">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="bbfb2-393">Para obtener la dirección URL correcta del vídeo, seleccione la pestaña **Insertar** debajo del fotograma de vídeo y copie la dirección URL del elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-393">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="bbfb2-394">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-394">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="bbfb2-395">YouTube</span><span class="sxs-lookup"><span data-stu-id="bbfb2-395">YouTube</span></span>

<span data-ttu-id="bbfb2-396">Para obtener la dirección URL correcta del vídeo, haga clic con el botón derecho en el vídeo, seleccione **Copiar código para insertar** y copie la dirección URL del elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-396">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="bbfb2-397">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-397">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="bbfb2-398">Extensiones de docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="bbfb2-398">docs.microsoft extensions</span></span>

<span data-ttu-id="bbfb2-399">docs.microsoft proporciona algunas extensiones adicionales a Markdown característico de GitHub.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-399">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="bbfb2-400">Alertas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-400">Alerts</span></span>

<span data-ttu-id="bbfb2-401">Es importante usar los siguientes estilos de alerta, por lo que se representan con el estilo correspondiente en el sitio de documentación.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-401">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="bbfb2-402">Sin embargo, el motor de representación en GitHub no los diferencia.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-402">However, the rendering engine on GitHub doesn't diferentiate them.</span></span>

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

<span data-ttu-id="bbfb2-403">Y se procesarán como esto: ![Estilos de alerta](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-403">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="bbfb2-404">Incluye</span><span class="sxs-lookup"><span data-stu-id="bbfb2-404">Includes</span></span>

<span data-ttu-id="bbfb2-405">Puede insertar el Markdown de un archivo en otro con Include.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-405">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="bbfb2-406">Listas comprobadas</span><span class="sxs-lookup"><span data-stu-id="bbfb2-406">Checked lists</span></span>

<span data-ttu-id="bbfb2-407">Hay disponible un estilo personalizado para las listas.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-407">A custom style is available for lists.</span></span> <span data-ttu-id="bbfb2-408">Puede representar las listas con marcas de verificación verdes.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-408">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
> - <span data-ttu-id="bbfb2-409">Cómo crear una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="bbfb2-409">How to create a .NET Core app</span></span>
> - <span data-ttu-id="bbfb2-410">Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="bbfb2-410">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="bbfb2-411">Cómo editar MyApp.csproj para agregar dependencias</span><span class="sxs-lookup"><span data-stu-id="bbfb2-411">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="bbfb2-412">Cómo agregar una clase y un XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="bbfb2-412">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="bbfb2-413">Cómo compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="bbfb2-413">How to build and run the application</span></span>

<span data-ttu-id="bbfb2-414">Puede ver un ejemplo de las listas comprobadas en acción en la [documentación de .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-414">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="bbfb2-415">Botones</span><span class="sxs-lookup"><span data-stu-id="bbfb2-415">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="bbfb2-416">vínculos de botón</span><span class="sxs-lookup"><span data-stu-id="bbfb2-416">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="bbfb2-417">Puede ver un ejemplo de los botones en acción en la [documentación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-417">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="bbfb2-418">Selectores</span><span class="sxs-lookup"><span data-stu-id="bbfb2-418">Selectors</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="bbfb2-419">macOS</span><span class="sxs-lookup"><span data-stu-id="bbfb2-419">macOS</span></span>](../docs/core/tutorials/using-on-macos.md)
- [<span data-ttu-id="bbfb2-420">Windows</span><span class="sxs-lookup"><span data-stu-id="bbfb2-420">Windows</span></span>](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="bbfb2-421">Puede ver un ejemplo de los selectores en acción en la [documentación de Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-421">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="bbfb2-422">Paso a paso</span><span class="sxs-lookup"><span data-stu-id="bbfb2-422">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bbfb2-423">[Anterior](../docs/csharp/expression-trees-interpreting.md)
>[Siguiente](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-423">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="bbfb2-424">Puede ver un ejemplo de una guía paso a paso en acción en la [guía de C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-424">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
