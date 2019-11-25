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
ms.openlocfilehash: ed9fd55fd84606d2083e0576581391331769a1e6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089276"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="79d79-102">Plantilla de Markdown y metadatos</span><span class="sxs-lookup"><span data-stu-id="79d79-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="79d79-103">Esta plantilla de dotnet/docs contiene ejemplos de sintaxis de Markdown, así como instrucciones sobre cómo establecer los metadatos.</span><span class="sxs-lookup"><span data-stu-id="79d79-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="79d79-104">Para sacar el máximo partido, debe ver el [Markdown sin formato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) y la [vista representada](https://github.com/dotnet/docs/blob/master/styleguide/template.md).</span><span class="sxs-lookup"><span data-stu-id="79d79-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md).</span></span>

<span data-ttu-id="79d79-105">Al crear un archivo de Markdown, debe copiar la plantilla en un archivo nuevo, rellenar los metadatos como se indica a continuación, configurar el encabezado H1 como se indica antes del título de este artículo y eliminar el contenido.</span><span class="sxs-lookup"><span data-stu-id="79d79-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="79d79-106">Metadatos</span><span class="sxs-lookup"><span data-stu-id="79d79-106">Metadata</span></span>

<span data-ttu-id="79d79-107">Puede encontrar el bloque de metadatos completo más arriba (en el [Markdown sin formato](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), dividido en los campos obligatorios y opcionales.</span><span class="sxs-lookup"><span data-stu-id="79d79-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="79d79-108">Algunas notas claves:</span><span class="sxs-lookup"><span data-stu-id="79d79-108">Some key notes:</span></span>

- <span data-ttu-id="79d79-109">**Debe** haber un espacio entre los dos puntos (:) y el valor de un elemento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="79d79-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="79d79-110">Si un elemento de metadatos no tiene valor, comente el elemento con el carácter # o quítelo (no lo deje en blanco ni use "na").</span><span class="sxs-lookup"><span data-stu-id="79d79-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="79d79-111">Si va a agregar un valor a un elemento que se comentó, asegúrese de quitar el carácter #.</span><span class="sxs-lookup"><span data-stu-id="79d79-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="79d79-112">Dos puntos en un valor (por ejemplo, un título) interrumpen el analizador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="79d79-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="79d79-113">En este caso, encierre el título con comillas dobles (por ejemplo, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="79d79-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="79d79-114">**title**: aparece en los resultados del motor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="79d79-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="79d79-115">El título no debe ser idéntico al título en el encabezado H1 y debe contener 60 caracteres o menos.</span><span class="sxs-lookup"><span data-stu-id="79d79-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="79d79-116">**description**: resume el contenido del artículo.</span><span class="sxs-lookup"><span data-stu-id="79d79-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="79d79-117">Habitualmente aparece en la página de resultados de la búsqueda, pero no se usa para la clasificación de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="79d79-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="79d79-118">Debe tener entre 115 y 145 caracteres, incluidos los espacios.</span><span class="sxs-lookup"><span data-stu-id="79d79-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="79d79-119">**author** y **ms.author**: el campo author debe contener el **nombre de usuario de GitHub** del autor, no su alias.</span><span class="sxs-lookup"><span data-stu-id="79d79-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="79d79-120">Por otro lado, el campo **ms.author** debe contener un alias de Microsoft e indica al responsable de mantener el artículo.</span><span class="sxs-lookup"><span data-stu-id="79d79-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="79d79-121">**ms.topic**: el tipo de tema.</span><span class="sxs-lookup"><span data-stu-id="79d79-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="79d79-122">El valor más común es `conceptual` y se establece en un nivel global.</span><span class="sxs-lookup"><span data-stu-id="79d79-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="79d79-123">Otros valores comunes que se usan son `tutorial`, `overview` y `reference`.</span><span class="sxs-lookup"><span data-stu-id="79d79-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="79d79-124">**dev_langs** define el filtro de lenguaje que se muestra para el tema.</span><span class="sxs-lookup"><span data-stu-id="79d79-124">**dev_langs** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="79d79-125">Puede ver una lista de los valores admitidos en la sección [Lenguajes admitidos](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="79d79-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="79d79-126">Solo se debe establecer cuando el tema abarca más de un lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="79d79-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="79d79-127">Por lo general, en nuestro contenido solo se usa `csharp`, `vb`, `fsharp` y `cpp` para este valor.</span><span class="sxs-lookup"><span data-stu-id="79d79-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="79d79-128">**ms.prod**: identificación del producto que se usa con fines de inteligencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="79d79-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="79d79-129">Por lo general, se establecen en un nivel global, por lo que no suelen aparecer en el bloque de metadatos de cada artículo.</span><span class="sxs-lookup"><span data-stu-id="79d79-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="79d79-130">**ms.technology**: clasificación de inteligencia empresarial adicional.</span><span class="sxs-lookup"><span data-stu-id="79d79-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="79d79-131">Algunos de los valores admitidos son: `devlang-csharp` para temas de C#, `devlang-fsharp` para temas de F# y `devlang-visual-basic` para temas de VB.</span><span class="sxs-lookup"><span data-stu-id="79d79-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="79d79-132">Los valores variarán en otras guías, por lo que deberá pedir ayuda a un miembro del equipo.</span><span class="sxs-lookup"><span data-stu-id="79d79-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="79d79-133">**ms.date**: fecha con formato DD/MM/AAAA.</span><span class="sxs-lookup"><span data-stu-id="79d79-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="79d79-134">Se muestra en la página publicada para indicar la última vez que el artículo se editó de manera sustancial o se garantizó como "actualizado" (es decir, la última vez que se revisó el artículo y se consideró como actualizado).</span><span class="sxs-lookup"><span data-stu-id="79d79-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="79d79-135">**helpviewer_keywords**: las entradas se usan para los índices de libros sin conexión (una funcionalidad de Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="79d79-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="79d79-136">**f1_keywords**: conecta el artículo con la tecla F1 (una funcionalidad de Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="79d79-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="79d79-137">Markdown básico, GFM y caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="79d79-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="79d79-138">Todos los Markdown básicos y característicos de GitHub (GFM) son compatibles.</span><span class="sxs-lookup"><span data-stu-id="79d79-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="79d79-139">Para obtener más información sobre este tema, consulte:</span><span class="sxs-lookup"><span data-stu-id="79d79-139">For more information on these, see:</span></span>

- [<span data-ttu-id="79d79-140">Sintaxis de Markdown de línea de base</span><span class="sxs-lookup"><span data-stu-id="79d79-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="79d79-141">Documentación de GFM</span><span class="sxs-lookup"><span data-stu-id="79d79-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="79d79-142">Markdown utiliza caracteres especiales como \*, \` y \# para dar formato.</span><span class="sxs-lookup"><span data-stu-id="79d79-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="79d79-143">Si desea incluir uno de estos caracteres en el contenido, tiene dos opciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="79d79-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="79d79-144">Colocar una barra diagonal inversa antes del carácter especial para "aplicarle escape" (por ejemplo, `\*` para \*).</span><span class="sxs-lookup"><span data-stu-id="79d79-144">Put a backslash before the special character to "escape" it (for example, `\*` for an \*)</span></span>
- <span data-ttu-id="79d79-145">Usar el [código de entidad HTML](https://www.ascii.cl/htmlcodes.htm) para el carácter (por ejemplo, `&#42;` para &#42;).</span><span class="sxs-lookup"><span data-stu-id="79d79-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for an &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="79d79-146">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="79d79-146">File name</span></span>

<span data-ttu-id="79d79-147">Los nombres de archivo utilizan las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="79d79-147">File names use the following rules:</span></span>

- <span data-ttu-id="79d79-148">Solo contienen letras minúsculas, números y guiones.</span><span class="sxs-lookup"><span data-stu-id="79d79-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="79d79-149">No incluyen espacios ni signos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="79d79-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="79d79-150">Se usan guiones para separar palabras y números en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="79d79-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="79d79-151">Se usan verbos de acción de uso específicos, como desarrollar, comparar, compilar, solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="79d79-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="79d79-152">No utilice gerundios.</span><span class="sxs-lookup"><span data-stu-id="79d79-152">No -ing words.</span></span>
- <span data-ttu-id="79d79-153">No utilice palabras cortas ni incluya un, y, el, en, o, etc.</span><span class="sxs-lookup"><span data-stu-id="79d79-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="79d79-154">Debe estar en Markdown y utilizar la extensión de archivo .md.</span><span class="sxs-lookup"><span data-stu-id="79d79-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="79d79-155">Los nombres de archivo deben ser razonablemente cortos.</span><span class="sxs-lookup"><span data-stu-id="79d79-155">Keep file names reasonably short.</span></span> <span data-ttu-id="79d79-156">Forman parte de la dirección URL para los artículos.</span><span class="sxs-lookup"><span data-stu-id="79d79-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="79d79-157">Encabezados</span><span class="sxs-lookup"><span data-stu-id="79d79-157">Headings</span></span>

<span data-ttu-id="79d79-158">Utilice mayúsculas y minúsculas de estilo de oración.</span><span class="sxs-lookup"><span data-stu-id="79d79-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="79d79-159">Ponga en mayúscula la primera letra de la primera palabra de un título, los nombres propios y la primera letra que aparezca después de un signo de dos puntos (por ejemplo, "Tutorial: Predicción de precios mediante regresión con ML.NET").</span><span class="sxs-lookup"><span data-stu-id="79d79-159">Capitalize the first letter of the first word of a heading, proper nouns, and the first letter following a colon (for example, "Tutorial: Predict prices using regression with ML.NET").</span></span>

<span data-ttu-id="79d79-160">No agregue un signo de dos puntos después de "Cómo" (por ejemplo, "Cómo ordenar una matriz" y no "Cómo: Ordenar una matriz").</span><span class="sxs-lookup"><span data-stu-id="79d79-160">Don't add a colon after "How to" (for example, "How to sort an array" and not "How to: Sort an array").</span></span>

<span data-ttu-id="79d79-161">Los encabezados deben realizarse con estilo atx, es decir, usar de uno a seis caracteres hash (#) al principio de la línea para indicar un título, correspondiente a los niveles de encabezados HTML de H1 a H6.</span><span class="sxs-lookup"><span data-stu-id="79d79-161">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="79d79-162">Más arriba se pueden encontrar ejemplos de encabezados de primer y segundo nivel.</span><span class="sxs-lookup"><span data-stu-id="79d79-162">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="79d79-163">Solo **debe** haber un encabezado de primer nivel (H1) en el tema, que se mostrará como título en la página.</span><span class="sxs-lookup"><span data-stu-id="79d79-163">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="79d79-164">Si el encabezado termina en un carácter `#`, debe agregar un carácter de escape para que el título se represente correctamente.</span><span class="sxs-lookup"><span data-stu-id="79d79-164">If your heading ends in a `#` character, you need to escape it for the title to render correctly.</span></span> <span data-ttu-id="79d79-165">Por ejemplo, `# Async programming in F\#`.</span><span class="sxs-lookup"><span data-stu-id="79d79-165">For example, `# Async programming in F\#`.</span></span>

<span data-ttu-id="79d79-166">Los encabezados de segundo nivel generarán la tabla de contenido en la página que aparece en la sección "En este artículo" debajo del título en la página.</span><span class="sxs-lookup"><span data-stu-id="79d79-166">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="79d79-167">Encabezado de tercer nivel</span><span class="sxs-lookup"><span data-stu-id="79d79-167">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="79d79-168">Encabezado de cuarto nivel</span><span class="sxs-lookup"><span data-stu-id="79d79-168">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="79d79-169">Encabezado de quinto nivel</span><span class="sxs-lookup"><span data-stu-id="79d79-169">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="79d79-170">Encabezado de sexto nivel</span><span class="sxs-lookup"><span data-stu-id="79d79-170">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="79d79-171">Estilo del texto</span><span class="sxs-lookup"><span data-stu-id="79d79-171">Text styling</span></span>

<span data-ttu-id="79d79-172">*Cursiva* Se utiliza para archivos, carpetas, rutas de acceso (si se trata de elementos largos, divídalos en su propia línea), términos nuevos.</span><span class="sxs-lookup"><span data-stu-id="79d79-172">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="79d79-173">**Negrita** Se utiliza para elementos de la UI.</span><span class="sxs-lookup"><span data-stu-id="79d79-173">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="79d79-174">`Code` Se utiliza para código alineado, palabras clave del lenguaje, nombres de paquetes de NuGet, comandos de la línea de comandos, nombres de columnas y tablas de bases de datos y direcciones URL en las que no quiere que se pueda hacer clic.</span><span class="sxs-lookup"><span data-stu-id="79d79-174">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="79d79-175">Vínculos</span><span class="sxs-lookup"><span data-stu-id="79d79-175">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="79d79-176">Vínculos internos</span><span class="sxs-lookup"><span data-stu-id="79d79-176">Internal Links</span></span>

<span data-ttu-id="79d79-177">Para vincular a un encabezado en el mismo archivo de Markdown (también conocido como vínculos de anclaje), debe obtener el identificador del encabezado al que está intentando vincular.</span><span class="sxs-lookup"><span data-stu-id="79d79-177">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="79d79-178">Para confirmar el identificador, vea el origen del artículo representado, busque el identificador del encabezado (por ejemplo, `id="blockquote"`) y vincúlelo con # + identificador (por ejemplo, `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="79d79-178">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="79d79-179">El identificador se genera automáticamente basándose en el texto del encabezado.</span><span class="sxs-lookup"><span data-stu-id="79d79-179">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="79d79-180">De esta manera, por ejemplo, dada una única sección denominada `## Step 2`, el identificador sería similar a `id="step-2"`.</span><span class="sxs-lookup"><span data-stu-id="79d79-180">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="79d79-181">Ejemplo: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` genera [Declaración de bloques alineados con un identificador de lenguaje](#inline-code-blocks-with-language-identifier).</span><span class="sxs-lookup"><span data-stu-id="79d79-181">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="79d79-182">Para vincular a un archivo de Markdown en el mismo repositorio, utilice los [vínculos relativos](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), incluyendo el ".md" al final del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="79d79-182">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="79d79-183">Ejemplo: `[Readme file](../README.md)` genera un [archivo Léame](../README.md).</span><span class="sxs-lookup"><span data-stu-id="79d79-183">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="79d79-184">(Tenga en cuenta que los vínculos distinguen mayúsculas de minúsculas).</span><span class="sxs-lookup"><span data-stu-id="79d79-184">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="79d79-185">Ejemplo: `[Welcome to .NET](../docs/welcome.md)` genera [Bienvenido a .NET](../docs/welcome.md).</span><span class="sxs-lookup"><span data-stu-id="79d79-185">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="79d79-186">Para enlazar a un fichero de Markdown en el mismo repositorio, utilice el enlace relativo + enlace hashtag.</span><span class="sxs-lookup"><span data-stu-id="79d79-186">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="79d79-187">Ejemplo: `[.NET Community](../docs/welcome.md#open-source)` genera [Comunidad de .NET](../docs/welcome.md#open-source).</span><span class="sxs-lookup"><span data-stu-id="79d79-187">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="79d79-188">En la mayoría de los casos, se usan los vínculos relativos y no se aconseja usar `~/` en ellos, porque los vínculos relativos se resuelven en el origen en GitHub.</span><span class="sxs-lookup"><span data-stu-id="79d79-188">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="79d79-189">Sin embargo, cada vez que creemos un vínculo a un archivo en un repositorio dependiente, usaremos el carácter `~/` para proporcionar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="79d79-189">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="79d79-190">Como los archivos del repositorio dependiente se encuentran en una ubicación distinta en GitHub, los vínculos no se resolverán correctamente con vínculos relativos, independientemente de cómo estén escritos.</span><span class="sxs-lookup"><span data-stu-id="79d79-190">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="79d79-191">La especificación del lenguaje de C# y la de Visual Basic se incluyen en la documentación de .NET mediante la inclusión del origen desde los repositorios de lenguajes.</span><span class="sxs-lookup"><span data-stu-id="79d79-191">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="79d79-192">Los orígenes de Markdown se administran en los repositorios [csharplang](https://github.com/dotnet/csharplang) y [visual basic](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="79d79-192">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="79d79-193">Los vínculos a la especificación deben apuntar a los directorios de origen donde se incluyen esas especificaciones.</span><span class="sxs-lookup"><span data-stu-id="79d79-193">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="79d79-194">En el caso de C#, es **~/_csharplang/spec** y, en VB, **~/_vblang/spec**.</span><span class="sxs-lookup"><span data-stu-id="79d79-194">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="79d79-195">Ejemplo: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` genera [Expresiones de consulta de C#](~/_csharplang/spec/expressions.md#query-expressions).</span><span class="sxs-lookup"><span data-stu-id="79d79-195">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="79d79-196">Vínculos externos</span><span class="sxs-lookup"><span data-stu-id="79d79-196">External Links</span></span>

<span data-ttu-id="79d79-197">Para vincular a un archivo externo, utilice la dirección URL completa como vínculo.</span><span class="sxs-lookup"><span data-stu-id="79d79-197">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="79d79-198">Ejemplo: `[GitHub](https://www.github.com)` genera [GitHub](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="79d79-198">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="79d79-199">Si aparece una dirección URL en un archivo de Markdown, se transformará en un vínculo.</span><span class="sxs-lookup"><span data-stu-id="79d79-199">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="79d79-200">Ejemplo: `<https://www.github.com>` genera <https://www.github.com>.</span><span class="sxs-lookup"><span data-stu-id="79d79-200">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="79d79-201">Prefiera el protocolo `https` para los vínculos externos.</span><span class="sxs-lookup"><span data-stu-id="79d79-201">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="79d79-202">Use solo vínculos `http` para los sitios que no admiten `https`.</span><span class="sxs-lookup"><span data-stu-id="79d79-202">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="79d79-203">Vínculos a las API</span><span class="sxs-lookup"><span data-stu-id="79d79-203">Links to APIs</span></span>

<span data-ttu-id="79d79-204">El sistema de compilación tiene algunas extensiones que permiten vincular a las API de .NET sin tener que usar los vínculos externos.</span><span class="sxs-lookup"><span data-stu-id="79d79-204">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="79d79-205">Al vincular a una API, puede usar su identificador único (UID) que se genera automáticamente desde el código fuente.</span><span class="sxs-lookup"><span data-stu-id="79d79-205">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="79d79-206">El UID equivale al nombre de miembro y de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="79d79-206">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="79d79-207">Si agrega un carácter \* (o %2A) después del UID, el vínculo representa la página de sobrecarga y no una API específica.</span><span class="sxs-lookup"><span data-stu-id="79d79-207">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="79d79-208">Por ejemplo, puede usarlo cuando quiera establecer un vínculo a la página [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) de manera genérica en lugar de una sobrecarga específica como [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="79d79-208">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="79d79-209">También puede usar \* para establecer un vínculo a una página de miembro cuando el miembro no está sobrecargado. Esto evitará que tenga que incluir la lista de parámetros en el UID.</span><span class="sxs-lookup"><span data-stu-id="79d79-209">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="79d79-210">Para establecer un vínculo a una sobrecarga de método específica, debe incluir el nombre de tipo completo de cada uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="79d79-210">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="79d79-211">Por ejemplo, \<xref:System.DateTime.ToString> establece un vínculo al método [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) sin parámetros, mientras que \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> establece un vínculo al método [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="79d79-211">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="79d79-212">Puede encontrar los UID de un miembro sobrecargado específico desde <https://xref.docs.microsoft.com/autocomplete>.</span><span class="sxs-lookup"><span data-stu-id="79d79-212">You can find the UIDs of a particular overloaded member from <https://xref.docs.microsoft.com/autocomplete>.</span></span> <span data-ttu-id="79d79-213">La cadena de consulta"?text= *\<type-member-name>* " identifica el tipo o miembro cuyos UID quiere ver.</span><span class="sxs-lookup"><span data-stu-id="79d79-213">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="79d79-214">Por ejemplo, <https://xref.docs.microsoft.com/autocomplete?text=string.format> recupera las sobrecargas [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="79d79-214">For example, <https://xref.docs.microsoft.com/autocomplete?text=string.format> retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="79d79-215">Para establecer un vínculo a un tipo genérico, como [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), puede usar el carácter \` (%60), seguido del número de parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="79d79-215">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="79d79-216">Por ejemplo, \<xref:System.Nullable%601> establece un vínculo al tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), mientras que \<xref:System.Func%602> establece un vínculo al delegado [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="79d79-216">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="79d79-217">Puede utilizar alguna de las siguientes sintaxis:</span><span class="sxs-lookup"><span data-stu-id="79d79-217">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="79d79-218">Vínculo automático: `<xref:UID>` o `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="79d79-218">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="79d79-219">El parámetro de consulta `displayProperty` genera un texto de vínculo completo.</span><span class="sxs-lookup"><span data-stu-id="79d79-219">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="79d79-220">De manera predeterminada, el texto de vínculo solo muestra el nombre de miembro o de tipo.</span><span class="sxs-lookup"><span data-stu-id="79d79-220">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="79d79-221">Vínculo de Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="79d79-221">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="79d79-222">Úselo cuando quiera personalizar el texto de vínculo que se muestra.</span><span class="sxs-lookup"><span data-stu-id="79d79-222">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="79d79-223">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="79d79-223">Examples:</span></span>

- <span data-ttu-id="79d79-224">`<xref:System.String>` se representa como [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="79d79-224">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="79d79-225">`<xref:System.String?displayProperty=nameWithType>` se representa como [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="79d79-225">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="79d79-226">`[String class](xref:System.String)` se representa como [String class](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="79d79-226">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="79d79-227">Para obtener más información acerca de cómo utilizar esta notación, consulte [Utilizar referencias cruzadas](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="79d79-227">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="79d79-228">Hay dos maneras de encontrar el UID:</span><span class="sxs-lookup"><span data-stu-id="79d79-228">There are two ways to find the UID:</span></span>

- <span data-ttu-id="79d79-229">Vea el código fuente de la página de API a la que quiere establecer un vínculo y busque el valor ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="79d79-229">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="79d79-230">Tenga en cuenta que los valores de sobrecarga individuales no aparecen en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="79d79-230">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="79d79-231">Use esta herramienta para buscar los UID: <https://xref.docs.microsoft.com/autocomplete?text=tostring> (reemplace tostring con partes del nombre de la API que intenta encontrar).</span><span class="sxs-lookup"><span data-stu-id="79d79-231">Use the following tool to search for UIDs: <https://xref.docs.microsoft.com/autocomplete?text=tostring> (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="79d79-232">La herramienta busca el parámetro de consulta `text` proporcionado en cualquier parte del UID.</span><span class="sxs-lookup"><span data-stu-id="79d79-232">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="79d79-233">Por ejemplo, puede buscar el nombre de miembro (ToString), el nombre de miembro parcial (ToStri), el nombre de tipo y de miembro (Double.ToString), etc.</span><span class="sxs-lookup"><span data-stu-id="79d79-233">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="79d79-234">Cuando el UID contiene los caracteres especiales \`, \# o \*, el valor de UID debe estar codificado en HTML como `%60`, `%23` y `%2A`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="79d79-234">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="79d79-235">En ocasiones verá paréntesis codificados, pero no es requisito.</span><span class="sxs-lookup"><span data-stu-id="79d79-235">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="79d79-236">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="79d79-236">Examples:</span></span>

- <span data-ttu-id="79d79-237">System.Threading.Tasks.Task\`1 se convierte en `System.Threading.Tasks.Task%601`.</span><span class="sxs-lookup"><span data-stu-id="79d79-237">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="79d79-238">System.Exception.\#ctor se convierte en `System.Exception.%23ctor`.</span><span class="sxs-lookup"><span data-stu-id="79d79-238">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="79d79-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se convierte en `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`.</span><span class="sxs-lookup"><span data-stu-id="79d79-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="79d79-240">Listas</span><span class="sxs-lookup"><span data-stu-id="79d79-240">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="79d79-241">Listas ordenadas</span><span class="sxs-lookup"><span data-stu-id="79d79-241">Ordered lists</span></span>

1. <span data-ttu-id="79d79-242">Esto</span><span class="sxs-lookup"><span data-stu-id="79d79-242">This</span></span>
1. <span data-ttu-id="79d79-243">Is</span><span class="sxs-lookup"><span data-stu-id="79d79-243">Is</span></span>
1. <span data-ttu-id="79d79-244">Una</span><span class="sxs-lookup"><span data-stu-id="79d79-244">An</span></span>
1. <span data-ttu-id="79d79-245">Por orden</span><span class="sxs-lookup"><span data-stu-id="79d79-245">Ordered</span></span>
1. <span data-ttu-id="79d79-246">Lista</span><span class="sxs-lookup"><span data-stu-id="79d79-246">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="79d79-247">Lista ordenada con una lista insertada</span><span class="sxs-lookup"><span data-stu-id="79d79-247">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="79d79-248">Aquí</span><span class="sxs-lookup"><span data-stu-id="79d79-248">Here</span></span>
1. <span data-ttu-id="79d79-249">viene</span><span class="sxs-lookup"><span data-stu-id="79d79-249">comes</span></span>
1. <span data-ttu-id="79d79-250">an</span><span class="sxs-lookup"><span data-stu-id="79d79-250">an</span></span>
1. <span data-ttu-id="79d79-251">insertada</span><span class="sxs-lookup"><span data-stu-id="79d79-251">embedded</span></span>
    1. <span data-ttu-id="79d79-252">Señora Beatriz</span><span class="sxs-lookup"><span data-stu-id="79d79-252">Miss Scarlett</span></span>
    1. <span data-ttu-id="79d79-253">Profesor Alcalá</span><span class="sxs-lookup"><span data-stu-id="79d79-253">Professor Plum</span></span>
1. <span data-ttu-id="79d79-254">ordered</span><span class="sxs-lookup"><span data-stu-id="79d79-254">ordered</span></span>
1. <span data-ttu-id="79d79-255">list</span><span class="sxs-lookup"><span data-stu-id="79d79-255">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="79d79-256">Listas desordenadas</span><span class="sxs-lookup"><span data-stu-id="79d79-256">Unordered Lists</span></span>

- <span data-ttu-id="79d79-257">Este</span><span class="sxs-lookup"><span data-stu-id="79d79-257">This</span></span>
- <span data-ttu-id="79d79-258">is</span><span class="sxs-lookup"><span data-stu-id="79d79-258">is</span></span>
- <span data-ttu-id="79d79-259">a</span><span class="sxs-lookup"><span data-stu-id="79d79-259">a</span></span>
- <span data-ttu-id="79d79-260">con viñetas</span><span class="sxs-lookup"><span data-stu-id="79d79-260">bulleted</span></span>
- <span data-ttu-id="79d79-261">lista</span><span class="sxs-lookup"><span data-stu-id="79d79-261">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="79d79-262">Lista desordenada con una lista insertada</span><span class="sxs-lookup"><span data-stu-id="79d79-262">Unordered list with an embedded list</span></span>

- <span data-ttu-id="79d79-263">Este</span><span class="sxs-lookup"><span data-stu-id="79d79-263">This</span></span>
- <span data-ttu-id="79d79-264">con viñetas</span><span class="sxs-lookup"><span data-stu-id="79d79-264">bulleted</span></span>
- <span data-ttu-id="79d79-265">list</span><span class="sxs-lookup"><span data-stu-id="79d79-265">list</span></span>
  - <span data-ttu-id="79d79-266">Sr. Valladares</span><span class="sxs-lookup"><span data-stu-id="79d79-266">Mrs. Peacock</span></span>
  - <span data-ttu-id="79d79-267">Sr. Tórrez</span><span class="sxs-lookup"><span data-stu-id="79d79-267">Mr. Green</span></span>
- <span data-ttu-id="79d79-268">contains</span><span class="sxs-lookup"><span data-stu-id="79d79-268">contains</span></span>
- <span data-ttu-id="79d79-269">otras</span><span class="sxs-lookup"><span data-stu-id="79d79-269">other</span></span>
  1. <span data-ttu-id="79d79-270">Coronel Valentín</span><span class="sxs-lookup"><span data-stu-id="79d79-270">Colonel Mustard</span></span>
  1. <span data-ttu-id="79d79-271">Sra. Blanco</span><span class="sxs-lookup"><span data-stu-id="79d79-271">Mrs. White</span></span>
- <span data-ttu-id="79d79-272">listas</span><span class="sxs-lookup"><span data-stu-id="79d79-272">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="79d79-273">Regla horizontal</span><span class="sxs-lookup"><span data-stu-id="79d79-273">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="79d79-274">Tablas</span><span class="sxs-lookup"><span data-stu-id="79d79-274">Tables</span></span>

| <span data-ttu-id="79d79-275">Tablas</span><span class="sxs-lookup"><span data-stu-id="79d79-275">Tables</span></span>        | <span data-ttu-id="79d79-276">Son</span><span class="sxs-lookup"><span data-stu-id="79d79-276">Are</span></span>           | <span data-ttu-id="79d79-277">Geniales</span><span class="sxs-lookup"><span data-stu-id="79d79-277">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="79d79-278">col 3 está</span><span class="sxs-lookup"><span data-stu-id="79d79-278">col 3 is</span></span>      | <span data-ttu-id="79d79-279">alineado a la derecha</span><span class="sxs-lookup"><span data-stu-id="79d79-279">right-aligned</span></span> | <span data-ttu-id="79d79-280">1600 $</span><span class="sxs-lookup"><span data-stu-id="79d79-280">$1600</span></span> |
| <span data-ttu-id="79d79-281">col 2 está</span><span class="sxs-lookup"><span data-stu-id="79d79-281">col 2 is</span></span>      | <span data-ttu-id="79d79-282">centrado</span><span class="sxs-lookup"><span data-stu-id="79d79-282">centered</span></span>      |   <span data-ttu-id="79d79-283">$12</span><span class="sxs-lookup"><span data-stu-id="79d79-283">$12</span></span> |
| <span data-ttu-id="79d79-284">col 1 está de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="79d79-284">col 1 is default</span></span> | <span data-ttu-id="79d79-285">alineado a la izquierda</span><span class="sxs-lookup"><span data-stu-id="79d79-285">left-aligned</span></span>     |    <span data-ttu-id="79d79-286">1 $</span><span class="sxs-lookup"><span data-stu-id="79d79-286">$1</span></span> |

<span data-ttu-id="79d79-287">Puede usar una [herramienta de generador de tabla de Markdown](https://www.tablesgenerator.com/markdown_tables) para ayudarle a crearlas más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="79d79-287">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="79d79-288">Código</span><span class="sxs-lookup"><span data-stu-id="79d79-288">Code</span></span>

<span data-ttu-id="79d79-289">La mejor manera de incluir código es incluir fragmentos de código de un ejemplo funcional.</span><span class="sxs-lookup"><span data-stu-id="79d79-289">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="79d79-290">Cree el ejemplo siguiendo las instrucciones de la [guía contribuyente](../CONTRIBUTING.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="79d79-290">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="79d79-291">Puede incluir el código con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="79d79-291">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="79d79-292">`-<language>` (*opcional*, pero *recomendado*)</span><span class="sxs-lookup"><span data-stu-id="79d79-292">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="79d79-293">El lenguaje del fragmento de código al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="79d79-293">Language of the code snippet being referenced.</span></span> <span data-ttu-id="79d79-294">Si quiere ver una lista de los valores admitidos, consulte [Lenguajes admitidos](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="79d79-294">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="79d79-295">`<name>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="79d79-295">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="79d79-296">El nombre del fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="79d79-296">Name for the code snippet.</span></span> <span data-ttu-id="79d79-297">No tienen ningún impacto en el HTML de salida, pero lo puede usar para mejorar la legibilidad de su propio origen de Markdown.</span><span class="sxs-lookup"><span data-stu-id="79d79-297">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="79d79-298">`<pathToFile>` (*obligatorio*)</span><span class="sxs-lookup"><span data-stu-id="79d79-298">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="79d79-299">Ruta de acceso relativa en el sistema de archivos que indica el archivo de fragmento de código al que se va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="79d79-299">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="79d79-300">`<queryoption>` y `<queryoptionvalue>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="79d79-300">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="79d79-301">Se usan en conjunto para especificar cómo se debe recuperar el código desde el archivo:</span><span class="sxs-lookup"><span data-stu-id="79d79-301">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="79d79-302">`#`: `#L{startlinenumber}-L{endlinenumber}` (intervalo de líneas) *o* `#{tagname}` (nombre de etiqueta).</span><span class="sxs-lookup"><span data-stu-id="79d79-302">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="79d79-303">No se recomienda usar números de línea, porque son muy complicados.</span><span class="sxs-lookup"><span data-stu-id="79d79-303">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="79d79-304">La mejor manera de hacer referencia a fragmentos de código es el nombre de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="79d79-304">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="79d79-305">`range`: `?range=1,3-5` Un intervalo de líneas.</span><span class="sxs-lookup"><span data-stu-id="79d79-305">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="79d79-306">Este ejemplo incluye las líneas 1, 3, 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="79d79-306">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="79d79-307">`dedent`: `?dedent=8` Aplica una sangría a las líneas según un número de espacios; en este caso, 8.</span><span class="sxs-lookup"><span data-stu-id="79d79-307">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="79d79-308">Se puede combinar con `range` y otras opciones de consulta que seleccionan un subconjunto de las líneas de un archivo.</span><span class="sxs-lookup"><span data-stu-id="79d79-308">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="79d79-309">`outdent`: `?outdent=8` Invierte la sangría de las líneas según un número de espacios; en este caso, 8.</span><span class="sxs-lookup"><span data-stu-id="79d79-309">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="79d79-310">Se puede combinar con `range` y otras opciones de consulta que seleccionan un subconjunto de las líneas de un archivo.</span><span class="sxs-lookup"><span data-stu-id="79d79-310">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="79d79-311">Se recomienda usar la opción de nombre de etiqueta siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="79d79-311">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="79d79-312">El nombre de etiqueta es el nombre de una región o de un comentario de código con el formato de `Snippettagname` presente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="79d79-312">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="79d79-313">En el ejemplo siguiente se muestra cómo hacer referencia al nombre de etiqueta `1`:</span><span class="sxs-lookup"><span data-stu-id="79d79-313">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="79d79-314">Y puede ver cómo las etiquetas del fragmento de código están estructuradas en [este archivo de código fuente](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span><span class="sxs-lookup"><span data-stu-id="79d79-314">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="79d79-315">Para detalles sobre la representación de un nombre de etiqueta en los archivos de código fuente de un fragmento de código por lenguaje, consulte las [instrucciones de DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="79d79-315">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="79d79-316">Incluir fragmentos de programas completos garantiza que todo el código se ejecuta a través de nuestro sistema de integración continua (CI).</span><span class="sxs-lookup"><span data-stu-id="79d79-316">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="79d79-317">Sin embargo, si necesita mostrar algo que causa errores de runtime o de tiempo de compilación, puede utilizar bloques de código alineados.</span><span class="sxs-lookup"><span data-stu-id="79d79-317">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="79d79-318">Bloques de código alineados con el identificador de idioma</span><span class="sxs-lookup"><span data-stu-id="79d79-318">Inline code blocks with language identifier</span></span>

<span data-ttu-id="79d79-319">Utilice tres acentos graves (\`\`\`) + un identificador de lenguaje para aplicar la codificación de color específica del lenguaje a un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="79d79-319">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="79d79-320">Esta es la lista de lenguajes admitidos donde se muestra la etiqueta de Markdown para cada id. de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="79d79-320">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="79d79-321">Idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="79d79-321">Supported languages</span></span>

|<span data-ttu-id="79d79-322">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="79d79-322">Name</span></span>|<span data-ttu-id="79d79-323">Etiqueta de Markdown</span><span class="sxs-lookup"><span data-stu-id="79d79-323">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="79d79-324">Consola de .NET</span><span class="sxs-lookup"><span data-stu-id="79d79-324">.NET Console</span></span>|<span data-ttu-id="79d79-325">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="79d79-325">dotnetcli</span></span>|
|<span data-ttu-id="79d79-326">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="79d79-326">ASP.NET (C#)</span></span>|<span data-ttu-id="79d79-327">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="79d79-327">aspx-csharp</span></span>|
|<span data-ttu-id="79d79-328">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="79d79-328">ASP.NET (VB)</span></span>|<span data-ttu-id="79d79-329">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="79d79-329">aspx-vb</span></span>|
|<span data-ttu-id="79d79-330">CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="79d79-330">Azure CLI</span></span>|<span data-ttu-id="79d79-331">azurecli</span><span class="sxs-lookup"><span data-stu-id="79d79-331">azurecli</span></span>|
|<span data-ttu-id="79d79-332">AzCopy</span><span class="sxs-lookup"><span data-stu-id="79d79-332">AzCopy</span></span>|<span data-ttu-id="79d79-333">azcopy</span><span class="sxs-lookup"><span data-stu-id="79d79-333">azcopy</span></span>|
|<span data-ttu-id="79d79-334">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="79d79-334">Azure PowerShell</span></span>|<span data-ttu-id="79d79-335">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="79d79-335">azurepowershell</span></span>|
|<span data-ttu-id="79d79-336">Bash</span><span class="sxs-lookup"><span data-stu-id="79d79-336">Bash</span></span>|<span data-ttu-id="79d79-337">Bash</span><span class="sxs-lookup"><span data-stu-id="79d79-337">bash</span></span>|
|<span data-ttu-id="79d79-338">C++</span><span class="sxs-lookup"><span data-stu-id="79d79-338">C++</span></span>|<span data-ttu-id="79d79-339">cpp</span><span class="sxs-lookup"><span data-stu-id="79d79-339">cpp</span></span>|
|<span data-ttu-id="79d79-340">C++/CX</span><span class="sxs-lookup"><span data-stu-id="79d79-340">C++/CX</span></span>|<span data-ttu-id="79d79-341">cppcx</span><span class="sxs-lookup"><span data-stu-id="79d79-341">cppcx</span></span>|
|<span data-ttu-id="79d79-342">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="79d79-342">C++/WinRT</span></span>|<span data-ttu-id="79d79-343">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="79d79-343">cppwinrt</span></span>|
|<span data-ttu-id="79d79-344">C#</span><span class="sxs-lookup"><span data-stu-id="79d79-344">C#</span></span>|<span data-ttu-id="79d79-345">csharp</span><span class="sxs-lookup"><span data-stu-id="79d79-345">csharp</span></span>|
|<span data-ttu-id="79d79-346">C# en el explorador</span><span class="sxs-lookup"><span data-stu-id="79d79-346">C# in browser</span></span>|<span data-ttu-id="79d79-347">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="79d79-347">csharp-interactive</span></span>|
|<span data-ttu-id="79d79-348">Consola</span><span class="sxs-lookup"><span data-stu-id="79d79-348">Console</span></span>|<span data-ttu-id="79d79-349">console</span><span class="sxs-lookup"><span data-stu-id="79d79-349">console</span></span>|
|<span data-ttu-id="79d79-350">CSHTML</span><span class="sxs-lookup"><span data-stu-id="79d79-350">CSHTML</span></span>|<span data-ttu-id="79d79-351">cshtml</span><span class="sxs-lookup"><span data-stu-id="79d79-351">cshtml</span></span>|
|<span data-ttu-id="79d79-352">DAX</span><span class="sxs-lookup"><span data-stu-id="79d79-352">DAX</span></span>|<span data-ttu-id="79d79-353">dax</span><span class="sxs-lookup"><span data-stu-id="79d79-353">dax</span></span>|
|<span data-ttu-id="79d79-354">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="79d79-354">Dockerfile</span></span>|<span data-ttu-id="79d79-355">dockerfile</span><span class="sxs-lookup"><span data-stu-id="79d79-355">dockerfile</span></span>|
|<span data-ttu-id="79d79-356">F#</span><span class="sxs-lookup"><span data-stu-id="79d79-356">F#</span></span>|<span data-ttu-id="79d79-357">fsharp</span><span class="sxs-lookup"><span data-stu-id="79d79-357">fsharp</span></span>|
|<span data-ttu-id="79d79-358">Go</span><span class="sxs-lookup"><span data-stu-id="79d79-358">Go</span></span>|<span data-ttu-id="79d79-359">go</span><span class="sxs-lookup"><span data-stu-id="79d79-359">go</span></span>|
|<span data-ttu-id="79d79-360">HTML</span><span class="sxs-lookup"><span data-stu-id="79d79-360">HTML</span></span>|<span data-ttu-id="79d79-361">html</span><span class="sxs-lookup"><span data-stu-id="79d79-361">html</span></span>|
|<span data-ttu-id="79d79-362">HTTP</span><span class="sxs-lookup"><span data-stu-id="79d79-362">HTTP</span></span>|<span data-ttu-id="79d79-363">http</span><span class="sxs-lookup"><span data-stu-id="79d79-363">http</span></span>|
|<span data-ttu-id="79d79-364">Java</span><span class="sxs-lookup"><span data-stu-id="79d79-364">Java</span></span>|<span data-ttu-id="79d79-365">Java</span><span class="sxs-lookup"><span data-stu-id="79d79-365">java</span></span>|
|<span data-ttu-id="79d79-366">JavaScript</span><span class="sxs-lookup"><span data-stu-id="79d79-366">JavaScript</span></span>|<span data-ttu-id="79d79-367">javascript</span><span class="sxs-lookup"><span data-stu-id="79d79-367">javascript</span></span>|
|<span data-ttu-id="79d79-368">JSON</span><span class="sxs-lookup"><span data-stu-id="79d79-368">JSON</span></span>|<span data-ttu-id="79d79-369">json</span><span class="sxs-lookup"><span data-stu-id="79d79-369">json</span></span>|
|<span data-ttu-id="79d79-370">Lenguaje de consulta de Kusto</span><span class="sxs-lookup"><span data-stu-id="79d79-370">Kusto Query Language</span></span>|<span data-ttu-id="79d79-371">kusto</span><span class="sxs-lookup"><span data-stu-id="79d79-371">kusto</span></span>|
|<span data-ttu-id="79d79-372">Markdown</span><span class="sxs-lookup"><span data-stu-id="79d79-372">Markdown</span></span>|<span data-ttu-id="79d79-373">md</span><span class="sxs-lookup"><span data-stu-id="79d79-373">md</span></span>|
|<span data-ttu-id="79d79-374">NodeJS</span><span class="sxs-lookup"><span data-stu-id="79d79-374">NodeJS</span></span>|<span data-ttu-id="79d79-375">nodejs</span><span class="sxs-lookup"><span data-stu-id="79d79-375">nodejs</span></span>|
|<span data-ttu-id="79d79-376">Objective-C</span><span class="sxs-lookup"><span data-stu-id="79d79-376">Objective-C</span></span>|<span data-ttu-id="79d79-377">objc</span><span class="sxs-lookup"><span data-stu-id="79d79-377">objc</span></span>|
|<span data-ttu-id="79d79-378">OData</span><span class="sxs-lookup"><span data-stu-id="79d79-378">OData</span></span>|<span data-ttu-id="79d79-379">odata</span><span class="sxs-lookup"><span data-stu-id="79d79-379">odata</span></span>|
|<span data-ttu-id="79d79-380">PHP</span><span class="sxs-lookup"><span data-stu-id="79d79-380">PHP</span></span>|<span data-ttu-id="79d79-381">php</span><span class="sxs-lookup"><span data-stu-id="79d79-381">php</span></span>|
|<span data-ttu-id="79d79-382">protobuf</span><span class="sxs-lookup"><span data-stu-id="79d79-382">protobuf</span></span>|<span data-ttu-id="79d79-383">protobuf</span><span class="sxs-lookup"><span data-stu-id="79d79-383">protobuf</span></span>|
|<span data-ttu-id="79d79-384">PowerApps (punto como separador decimal)</span><span class="sxs-lookup"><span data-stu-id="79d79-384">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="79d79-385">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="79d79-385">powerapps-dot</span></span>|
|<span data-ttu-id="79d79-386">PowerApps (coma como separador decimal)</span><span class="sxs-lookup"><span data-stu-id="79d79-386">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="79d79-387">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="79d79-387">powerapps-comma</span></span>|
|<span data-ttu-id="79d79-388">PowerShell</span><span class="sxs-lookup"><span data-stu-id="79d79-388">PowerShell</span></span>|<span data-ttu-id="79d79-389">powershell</span><span class="sxs-lookup"><span data-stu-id="79d79-389">powershell</span></span>|
|<span data-ttu-id="79d79-390">Python</span><span class="sxs-lookup"><span data-stu-id="79d79-390">Python</span></span>|<span data-ttu-id="79d79-391">Python</span><span class="sxs-lookup"><span data-stu-id="79d79-391">python</span></span>|
|<span data-ttu-id="79d79-392">Q#</span><span class="sxs-lookup"><span data-stu-id="79d79-392">Q#</span></span>|<span data-ttu-id="79d79-393">qsharp</span><span class="sxs-lookup"><span data-stu-id="79d79-393">qsharp</span></span>|
|<span data-ttu-id="79d79-394">R</span><span class="sxs-lookup"><span data-stu-id="79d79-394">R</span></span>|<span data-ttu-id="79d79-395">r</span><span class="sxs-lookup"><span data-stu-id="79d79-395">r</span></span>|
|<span data-ttu-id="79d79-396">Ruby</span><span class="sxs-lookup"><span data-stu-id="79d79-396">Ruby</span></span>|<span data-ttu-id="79d79-397">ruby</span><span class="sxs-lookup"><span data-stu-id="79d79-397">ruby</span></span>|
|<span data-ttu-id="79d79-398">SQL</span><span class="sxs-lookup"><span data-stu-id="79d79-398">SQL</span></span>|<span data-ttu-id="79d79-399">sql</span><span class="sxs-lookup"><span data-stu-id="79d79-399">sql</span></span>|
|<span data-ttu-id="79d79-400">Swift</span><span class="sxs-lookup"><span data-stu-id="79d79-400">Swift</span></span>|<span data-ttu-id="79d79-401">swift</span><span class="sxs-lookup"><span data-stu-id="79d79-401">swift</span></span>|
|<span data-ttu-id="79d79-402">TypeScript</span><span class="sxs-lookup"><span data-stu-id="79d79-402">TypeScript</span></span>|<span data-ttu-id="79d79-403">typescript</span><span class="sxs-lookup"><span data-stu-id="79d79-403">typescript</span></span>|
|<span data-ttu-id="79d79-404">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79d79-404">Visual Basic</span></span>|<span data-ttu-id="79d79-405">vb</span><span class="sxs-lookup"><span data-stu-id="79d79-405">vb</span></span>|
|<span data-ttu-id="79d79-406">VBScript</span><span class="sxs-lookup"><span data-stu-id="79d79-406">VBScript</span></span>|<span data-ttu-id="79d79-407">vbscript</span><span class="sxs-lookup"><span data-stu-id="79d79-407">vbscript</span></span>|
|<span data-ttu-id="79d79-408">XAML</span><span class="sxs-lookup"><span data-stu-id="79d79-408">XAML</span></span>|<span data-ttu-id="79d79-409">xaml</span><span class="sxs-lookup"><span data-stu-id="79d79-409">xaml</span></span>|
|<span data-ttu-id="79d79-410">XML</span><span class="sxs-lookup"><span data-stu-id="79d79-410">XML</span></span>|<span data-ttu-id="79d79-411">Xml</span><span class="sxs-lookup"><span data-stu-id="79d79-411">xml</span></span>|
|<span data-ttu-id="79d79-412">yml</span><span class="sxs-lookup"><span data-stu-id="79d79-412">yml</span></span>|<span data-ttu-id="79d79-413">yml</span><span class="sxs-lookup"><span data-stu-id="79d79-413">yml</span></span>|

<span data-ttu-id="79d79-414">El nombre `csharp-interactive` especifica el lenguaje C# y la capacidad de ejecutar los ejemplos desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="79d79-414">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="79d79-415">Estos fragmentos de código se compilan y ejecutan en un contenedor de Docker y los resultados de la ejecución del programa se muestran en la ventana del explorador del usuario.</span><span class="sxs-lookup"><span data-stu-id="79d79-415">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="79d79-416">Estos son ejemplos de bloques de código que usan los id. de lenguaje para (\`\`\`csharp), Python (\`\`\`python) y PowerShell (\`\`\`powershell).</span><span class="sxs-lookup"><span data-stu-id="79d79-416">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c"></a><span data-ttu-id="79d79-417">C\#</span><span class="sxs-lookup"><span data-stu-id="79d79-417">C\#</span></span>

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

#### <a name="python"></a><span data-ttu-id="79d79-418">Python</span><span class="sxs-lookup"><span data-stu-id="79d79-418">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="79d79-419">PowerShell</span><span class="sxs-lookup"><span data-stu-id="79d79-419">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="79d79-420">Bloque de código genérico</span><span class="sxs-lookup"><span data-stu-id="79d79-420">Generic code block</span></span>

<span data-ttu-id="79d79-421">Utilice tres acentos graves (\`\`\`) para la codificación de bloques de código genéricos.</span><span class="sxs-lookup"><span data-stu-id="79d79-421">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="79d79-422">El enfoque recomendado es utilizar los bloques de código con los identificadores de lenguaje, como se explica en la sección anterior, para garantizar el resaltado de sintaxis correcto en la documentación del sitio.</span><span class="sxs-lookup"><span data-stu-id="79d79-422">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="79d79-423">Utilice bloques de código genéricos solo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="79d79-423">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="79d79-424">Blockquotes</span><span class="sxs-lookup"><span data-stu-id="79d79-424">Blockquotes</span></span>

> <span data-ttu-id="79d79-425">La sequía lleva existiendo diez millones de años y el reino de los terribles lagartos hace mucho que finalizó.</span><span class="sxs-lookup"><span data-stu-id="79d79-425">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="79d79-426">Aquí en el Ecuador, en el continente que será un día conocido como África, la batalla por la existencia ha alcanzado un nuevo clímax de ferocidad, y el ganador aún no se ha mostrado.</span><span class="sxs-lookup"><span data-stu-id="79d79-426">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="79d79-427">En este terreno estéril y desecado, solo los pequeños, los rápidos o los feroces podrían prosperar, o incluso esperar sobrevivir.</span><span class="sxs-lookup"><span data-stu-id="79d79-427">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="79d79-428">Imágenes</span><span class="sxs-lookup"><span data-stu-id="79d79-428">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="79d79-429">Gif animado o imagen estática</span><span class="sxs-lookup"><span data-stu-id="79d79-429">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![este es el texto alternativo](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="79d79-431">Imagen vinculada</span><span class="sxs-lookup"><span data-stu-id="79d79-431">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="79d79-432">[![texto alternativo para la imagen vinculada](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="79d79-432">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="79d79-433">Vídeos</span><span class="sxs-lookup"><span data-stu-id="79d79-433">Videos</span></span>

<span data-ttu-id="79d79-434">Actualmente, puede insertar vídeos tanto de Channel 9 como de YouTube con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="79d79-434">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="79d79-435">Channel 9</span><span class="sxs-lookup"><span data-stu-id="79d79-435">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="79d79-436">Para obtener la dirección URL correcta del vídeo, seleccione la pestaña **Insertar** debajo del fotograma de vídeo y copie la dirección URL del elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="79d79-436">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="79d79-437">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79d79-437">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="79d79-438">YouTube</span><span class="sxs-lookup"><span data-stu-id="79d79-438">YouTube</span></span>

<span data-ttu-id="79d79-439">Para obtener la dirección URL correcta del vídeo, haga clic con el botón derecho en el vídeo, seleccione **Copiar código para insertar** y copie la dirección URL del elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="79d79-439">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="79d79-440">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79d79-440">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="79d79-441">Extensiones de docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="79d79-441">docs.microsoft extensions</span></span>

<span data-ttu-id="79d79-442">docs.microsoft proporciona algunas extensiones adicionales a Markdown característico de GitHub.</span><span class="sxs-lookup"><span data-stu-id="79d79-442">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="79d79-443">Alertas</span><span class="sxs-lookup"><span data-stu-id="79d79-443">Alerts</span></span>

<span data-ttu-id="79d79-444">Es importante usar los siguientes estilos de alerta, por lo que se representan con el estilo correspondiente en el sitio de documentación.</span><span class="sxs-lookup"><span data-stu-id="79d79-444">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="79d79-445">Pero el motor de representación en GitHub no los diferencia.</span><span class="sxs-lookup"><span data-stu-id="79d79-445">However, the rendering engine on GitHub doesn't differentiate them.</span></span>

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

<span data-ttu-id="79d79-446">Y se procesarán como esto: ![Estilos de alerta](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="79d79-446">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="79d79-447">Incluye</span><span class="sxs-lookup"><span data-stu-id="79d79-447">Includes</span></span>

<span data-ttu-id="79d79-448">Puede insertar el Markdown de un archivo en otro con Include.</span><span class="sxs-lookup"><span data-stu-id="79d79-448">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="79d79-449">Listas comprobadas</span><span class="sxs-lookup"><span data-stu-id="79d79-449">Checked lists</span></span>

<span data-ttu-id="79d79-450">Hay disponible un estilo personalizado para las listas.</span><span class="sxs-lookup"><span data-stu-id="79d79-450">A custom style is available for lists.</span></span> <span data-ttu-id="79d79-451">Puede representar las listas con marcas de verificación verdes.</span><span class="sxs-lookup"><span data-stu-id="79d79-451">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="79d79-452">Cómo crear una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="79d79-452">How to create a .NET Core app</span></span>
> - <span data-ttu-id="79d79-453">Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="79d79-453">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="79d79-454">Cómo editar MyApp.csproj para agregar dependencias</span><span class="sxs-lookup"><span data-stu-id="79d79-454">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="79d79-455">Cómo agregar una clase y un XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="79d79-455">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="79d79-456">Cómo compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="79d79-456">How to build and run the application</span></span>

<span data-ttu-id="79d79-457">Puede ver un ejemplo de las listas comprobadas en acción en la [documentación de .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="79d79-457">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="79d79-458">Botones</span><span class="sxs-lookup"><span data-stu-id="79d79-458">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="79d79-459">vínculos de botón</span><span class="sxs-lookup"><span data-stu-id="79d79-459">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="79d79-460">Puede ver un ejemplo de los botones en acción en la [documentación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="79d79-460">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="79d79-461">Selectores</span><span class="sxs-lookup"><span data-stu-id="79d79-461">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="79d79-464">Puede ver un ejemplo de los selectores en acción en la [documentación de Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="79d79-464">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="79d79-465">Paso a paso</span><span class="sxs-lookup"><span data-stu-id="79d79-465">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="79d79-466">[Anterior](../docs/csharp/expression-trees-interpreting.md)
>[Siguiente](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="79d79-466">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="79d79-467">Puede ver un ejemplo de una guía paso a paso en acción en la [guía de C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="79d79-467">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
