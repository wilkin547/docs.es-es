---
title: Documentar el código con comentarios XML
description: Obtenga información sobre cómo documentar el código con comentarios de documentación XML y generar un archivo de documentación XML en tiempo de compilación.
ms.date: 01/21/2020
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: 1ec088db1de7c953bdb20b1129c5fd40f9e31454
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965937"
---
# <a name="document-your-code-with-xml-comments"></a><span data-ttu-id="92af1-103">Documentación del código con comentarios XML</span><span class="sxs-lookup"><span data-stu-id="92af1-103">Document your code with XML comments</span></span>

<span data-ttu-id="92af1-104">Los comentarios de documentación XML son un tipo especial de comentarios que se agregan encima de la definición de un tipo o un miembro definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="92af1-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="92af1-105">Son especiales porque los puede procesar el compilador para generar un archivo de documentación XML en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="92af1-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="92af1-106">El archivo XML generado por el compilador se puede distribuir junto con el ensamblado .NET de modo que Visual Studio y otros IDE puedan usar IntelliSense para mostrar información rápida sobre los tipos o los miembros.</span><span class="sxs-lookup"><span data-stu-id="92af1-106">The compiler-generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="92af1-107">Además, el archivo XML se puede ejecutar mediante herramientas como [DocFX](https://dotnet.github.io/docfx/) y [Sandcastle](https://github.com/EWSoftware/SHFB) para generar sitios web de referencia de API.</span><span class="sxs-lookup"><span data-stu-id="92af1-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="92af1-108">El compilador omite los comentarios de documentación XML, igual que los demás comentarios.</span><span class="sxs-lookup"><span data-stu-id="92af1-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="92af1-109">Para generar el archivo XML en tiempo de compilación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="92af1-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="92af1-110">Si está desarrollando una aplicación con .NET Core desde la línea de comandos, puede agregar un elemento `GenerateDocumentationFile` a la sección `<PropertyGroup>` de su archivo de proyecto .csproj.</span><span class="sxs-lookup"><span data-stu-id="92af1-110">If you are developing an application with .NET Core from the command line, you can add a `GenerateDocumentationFile` element to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="92af1-111">También puede especificar la ruta de acceso al archivo de documentación directamente mediante el [elemento `DocumentationFile`](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="92af1-111">You can also specify the path to the documentation file directly using [`DocumentationFile` element](/visualstudio/msbuild/common-msbuild-project-properties).</span></span> <span data-ttu-id="92af1-112">En el siguiente ejemplo se genera un archivo XML en el directorio del proyecto con el mismo nombre de archivo raíz que el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="92af1-112">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```
   
   <span data-ttu-id="92af1-113">Es equivalente a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="92af1-113">This is equivalent to the following:</span></span>
   
   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- <span data-ttu-id="92af1-114">Si está desarrollando una aplicación mediante Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="92af1-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="92af1-115">En el cuadro de diálogo de propiedades, seleccione la pestaña **Compilar** y active **Archivo de documentación XML**.</span><span class="sxs-lookup"><span data-stu-id="92af1-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="92af1-116">También puede cambiar la ubicación en la que el compilador escribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="92af1-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="92af1-117">Si está compilando una aplicación de .NET Framework desde la línea de comandos, agregue la [opción del compilador -doc](language-reference/compiler-options/doc-compiler-option.md) al compilar.</span><span class="sxs-lookup"><span data-stu-id="92af1-117">If you are compiling a .NET Framework application from the command line, add the [-doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="92af1-118">Los comentarios de documentación XML usan tres barras diagonales (`///`) y un cuerpo de comentario con formato XML.</span><span class="sxs-lookup"><span data-stu-id="92af1-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="92af1-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="92af1-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="92af1-120">Tutorial</span><span class="sxs-lookup"><span data-stu-id="92af1-120">Walkthrough</span></span>

<span data-ttu-id="92af1-121">Vamos a documentar una biblioteca matemática muy básica para que a los nuevos desarrolladores les resulte más fácil comprenderla y contribuir, y a los desarrolladores de otras empresas usarla.</span><span class="sxs-lookup"><span data-stu-id="92af1-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third-party developers to use.</span></span>

<span data-ttu-id="92af1-122">Este es el código de la biblioteca matemática simple:</span><span class="sxs-lookup"><span data-stu-id="92af1-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="92af1-123">La biblioteca de ejemplo es compatible con cuatro operaciones aritméticas principales (`add`, `subtract`, `multiply` y `divide`) en tipos de datos `int` y `double`.</span><span class="sxs-lookup"><span data-stu-id="92af1-123">The sample library supports four major arithmetic operations (`add`, `subtract`, `multiply`, and `divide`) on `int` and `double` data types.</span></span>

<span data-ttu-id="92af1-124">Ahora le interesa crear un documento de referencia de API desde el código para los desarrolladores de otras empresas que usan la biblioteca, pero no tienen acceso al código fuente.</span><span class="sxs-lookup"><span data-stu-id="92af1-124">Now you want to be able to create an API reference document from your code for third-party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="92af1-125">Como se mencionó anteriormente, las etiquetas de documentación XML pueden utilizarse para lograr esto.</span><span class="sxs-lookup"><span data-stu-id="92af1-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="92af1-126">Ahora recibirá una introducción a las etiquetas XML estándares que admite el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="92af1-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

## <a name="summary"></a><span data-ttu-id="92af1-127">\<summary></span><span class="sxs-lookup"><span data-stu-id="92af1-127">\<summary></span></span>

<span data-ttu-id="92af1-128">La etiqueta `<summary>` agrega información breve sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="92af1-128">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="92af1-129">Vamos a demostrar su uso agregándola a la definición de clase `Math` y al primer método `Add`.</span><span class="sxs-lookup"><span data-stu-id="92af1-129">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="92af1-130">No dude en aplicarla al resto del código.</span><span class="sxs-lookup"><span data-stu-id="92af1-130">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](~/samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="92af1-131">La etiqueta `<summary>` es importante y se recomienda incluirla, dado que su contenido es la principal fuente de información sobre el tipo o el miembro en IntelliSense o en un documento de referencia de API.</span><span class="sxs-lookup"><span data-stu-id="92af1-131">The `<summary>` tag is important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

## <a name="remarks"></a><span data-ttu-id="92af1-132">\<remarks></span><span class="sxs-lookup"><span data-stu-id="92af1-132">\<remarks></span></span>

<span data-ttu-id="92af1-133">La etiqueta `<remarks>` complementa la información sobre los tipos o los miembros que proporciona la etiqueta `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="92af1-133">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="92af1-134">En este ejemplo, solo la agregará a la clase.</span><span class="sxs-lookup"><span data-stu-id="92af1-134">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](~/samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## <a name="returns"></a><span data-ttu-id="92af1-135">\<returns></span><span class="sxs-lookup"><span data-stu-id="92af1-135">\<returns></span></span>

<span data-ttu-id="92af1-136">La etiqueta `<returns>` describe el valor devuelto de una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="92af1-136">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="92af1-137">Al igual que antes, en el ejemplo siguiente se muestra la etiqueta `<returns>` en el primer método `Add`.</span><span class="sxs-lookup"><span data-stu-id="92af1-137">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="92af1-138">Puede hacer lo mismo en otros métodos.</span><span class="sxs-lookup"><span data-stu-id="92af1-138">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](~/samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## <a name="value"></a><span data-ttu-id="92af1-139">\<value></span><span class="sxs-lookup"><span data-stu-id="92af1-139">\<value></span></span>

<span data-ttu-id="92af1-140">La etiqueta `<value>` es similar a la etiqueta `<returns>`, salvo que se usa para propiedades.</span><span class="sxs-lookup"><span data-stu-id="92af1-140">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="92af1-141">Supongamos que su biblioteca `Math` tenía una propiedad estática denominada `PI`. A continuación le mostramos cómo usaría esta etiqueta:</span><span class="sxs-lookup"><span data-stu-id="92af1-141">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](~/samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## <a name="example"></a><span data-ttu-id="92af1-142">\<example></span><span class="sxs-lookup"><span data-stu-id="92af1-142">\<example></span></span>

<span data-ttu-id="92af1-143">La etiqueta `<example>` se usa para incluir un ejemplo en la documentación XML.</span><span class="sxs-lookup"><span data-stu-id="92af1-143">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="92af1-144">Esto implica usar la etiqueta secundaria `<code>`.</span><span class="sxs-lookup"><span data-stu-id="92af1-144">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](~/samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="92af1-145">La etiqueta `code` conserva los saltos de línea y la sangría en los ejemplos más largos.</span><span class="sxs-lookup"><span data-stu-id="92af1-145">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

## <a name="para"></a><span data-ttu-id="92af1-146">\<para></span><span class="sxs-lookup"><span data-stu-id="92af1-146">\<para></span></span>

<span data-ttu-id="92af1-147">La etiqueta `<para>` se usa para dar formato al contenido dentro de la etiqueta primaria.</span><span class="sxs-lookup"><span data-stu-id="92af1-147">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="92af1-148">`<para>` suele usarse dentro de una etiqueta, como `<remarks>` o `<returns>`, para dividir el texto en párrafos.</span><span class="sxs-lookup"><span data-stu-id="92af1-148">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="92af1-149">Puede dar formato al contenido de la etiqueta `<remarks>` de su definición de clase.</span><span class="sxs-lookup"><span data-stu-id="92af1-149">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](~/samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## <a name="c"></a><span data-ttu-id="92af1-150">\<c></span><span class="sxs-lookup"><span data-stu-id="92af1-150">\<c></span></span>

<span data-ttu-id="92af1-151">También en el ámbito del formato, puede usar la etiqueta `<c>` para marcar una parte del texto como código.</span><span class="sxs-lookup"><span data-stu-id="92af1-151">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="92af1-152">Es como la etiqueta `<code>`, pero insertada.</span><span class="sxs-lookup"><span data-stu-id="92af1-152">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="92af1-153">Es útil si quiere mostrar un ejemplo de código rápido como parte del contenido de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="92af1-153">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="92af1-154">Vamos a actualizar la documentación de la clase `Math`.</span><span class="sxs-lookup"><span data-stu-id="92af1-154">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](~/samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## <a name="exception"></a><span data-ttu-id="92af1-155">\<exception></span><span class="sxs-lookup"><span data-stu-id="92af1-155">\<exception></span></span>

<span data-ttu-id="92af1-156">Mediante el uso de la etiqueta `<exception>`, permite que los desarrolladores sepan que un método puede producir excepciones específicas.</span><span class="sxs-lookup"><span data-stu-id="92af1-156">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="92af1-157">Si examina su biblioteca `Math`, verá que los dos métodos `Add` producen una excepción si se cumple una determinada condición.</span><span class="sxs-lookup"><span data-stu-id="92af1-157">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="92af1-158">En cambio, no resulta tan obvio que el método entero `Divide` también produce una si el parámetro `b` es cero.</span><span class="sxs-lookup"><span data-stu-id="92af1-158">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="92af1-159">Vamos a agregar documentación de la excepción a este método.</span><span class="sxs-lookup"><span data-stu-id="92af1-159">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](~/samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="92af1-160">El atributo `cref` representa una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="92af1-160">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="92af1-161">Puede ser cualquier tipo definido en el proyecto o un ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="92af1-161">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="92af1-162">El compilador emitirá una advertencia si su valor no puede resolverse.</span><span class="sxs-lookup"><span data-stu-id="92af1-162">The compiler will issue a warning if its value cannot be resolved.</span></span>

## <a name="see"></a><span data-ttu-id="92af1-163">\<see></span><span class="sxs-lookup"><span data-stu-id="92af1-163">\<see></span></span>

<span data-ttu-id="92af1-164">La etiqueta `<see>` le permite crear un vínculo interactivo a una página de documentación para otro elemento de código.</span><span class="sxs-lookup"><span data-stu-id="92af1-164">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="92af1-165">En el siguiente ejemplo, crearemos un vínculo interactivo entre los dos métodos `Add`.</span><span class="sxs-lookup"><span data-stu-id="92af1-165">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](~/samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="92af1-166">`cref` es un atributo **necesario** que representa una referencia a un tipo o a su miembro que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="92af1-166">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="92af1-167">Puede ser cualquier tipo definido en el proyecto o un ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="92af1-167">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="seealso"></a><span data-ttu-id="92af1-168">\<seealso></span><span class="sxs-lookup"><span data-stu-id="92af1-168">\<seealso></span></span>

<span data-ttu-id="92af1-169">La etiqueta `<seealso>` se usa de la misma manera que la etiqueta `<see>`.</span><span class="sxs-lookup"><span data-stu-id="92af1-169">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="92af1-170">La única diferencia es que su contenido se suele colocar en una sección "Vea también".</span><span class="sxs-lookup"><span data-stu-id="92af1-170">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="92af1-171">Aquí vamos a agregar una etiqueta `seealso` en el método entero `Add` para hacer referencia a otros métodos de la clase que aceptan parámetros enteros:</span><span class="sxs-lookup"><span data-stu-id="92af1-171">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](~/samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="92af1-172">El atributo `cref` representa una referencia a un tipo o a su miembro que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="92af1-172">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="92af1-173">Puede ser cualquier tipo definido en el proyecto o un ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="92af1-173">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="param"></a><span data-ttu-id="92af1-174">\<param></span><span class="sxs-lookup"><span data-stu-id="92af1-174">\<param></span></span>

<span data-ttu-id="92af1-175">La etiqueta `<param>` se usa para describir los parámetros de un método.</span><span class="sxs-lookup"><span data-stu-id="92af1-175">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="92af1-176">Este es un ejemplo sobre el método doble `Add`: El parámetro que describe la etiqueta se especifica en el atributo **necesario** `name`.</span><span class="sxs-lookup"><span data-stu-id="92af1-176">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](~/samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## <a name="typeparam"></a><span data-ttu-id="92af1-177">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="92af1-177">\<typeparam></span></span>

<span data-ttu-id="92af1-178">La etiqueta `<typeparam>` se usa igual que la etiqueta `<param>`, pero sirve para que las declaraciones de método o tipo genérico describan un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="92af1-178">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="92af1-179">Agregue un método genérico rápido a su clase `Math` para comprobar si una cantidad es mayor que otra.</span><span class="sxs-lookup"><span data-stu-id="92af1-179">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](~/samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## <a name="paramref"></a><span data-ttu-id="92af1-180">\<paramref></span><span class="sxs-lookup"><span data-stu-id="92af1-180">\<paramref></span></span>

<span data-ttu-id="92af1-181">Puede darse la situación de que esté describiendo lo que hace un método en una etiqueta `<summary>` y le interese hacer referencia a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="92af1-181">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="92af1-182">La etiqueta `<paramref>` es perfecta para esto.</span><span class="sxs-lookup"><span data-stu-id="92af1-182">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="92af1-183">Vamos a actualizar el resumen del método doble `Add`.</span><span class="sxs-lookup"><span data-stu-id="92af1-183">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="92af1-184">Igual que en la etiqueta `<param>`, el nombre del parámetro se especifica en el atributo **necesario** `name`.</span><span class="sxs-lookup"><span data-stu-id="92af1-184">Like the `<param>` tag, the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](~/samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## <a name="typeparamref"></a><span data-ttu-id="92af1-185">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="92af1-185">\<typeparamref></span></span>

<span data-ttu-id="92af1-186">La etiqueta `<typeparamref>` se usa igual que la etiqueta `<paramref>`, pero sirve para que las declaraciones de método o tipo genérico describan un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="92af1-186">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="92af1-187">Puede usar el mismo método genérico que ha creado previamente.</span><span class="sxs-lookup"><span data-stu-id="92af1-187">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](~/samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## <a name="list"></a><span data-ttu-id="92af1-188">\<list></span><span class="sxs-lookup"><span data-stu-id="92af1-188">\<list></span></span>

<span data-ttu-id="92af1-189">La etiqueta `<list>` se usa para dar formato a la información de la documentación en una lista ordenada, una lista sin ordenar o una tabla.</span><span class="sxs-lookup"><span data-stu-id="92af1-189">You use the `<list>` tag to format documentation information as an ordered list, unordered list, or table.</span></span> <span data-ttu-id="92af1-190">Cree una lista sin ordenar con todas las operaciones matemáticas que admita su biblioteca `Math`.</span><span class="sxs-lookup"><span data-stu-id="92af1-190">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](~/samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="92af1-191">Para crear una lista ordenada o una tabla, cambie el atributo `type` a `number` o `table`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="92af1-191">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

## <a name="inheritdoc"></a><span data-ttu-id="92af1-192">\<inheritdoc></span><span class="sxs-lookup"><span data-stu-id="92af1-192">\<inheritdoc></span></span>

<span data-ttu-id="92af1-193">Puede usar la etiqueta `<inheritdoc>` para heredar comentarios XML de clases base, interfaces y métodos similares.</span><span class="sxs-lookup"><span data-stu-id="92af1-193">You can use the `<inheritdoc>` tag to inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="92af1-194">Esto elimina la acción de copiar y pegar no deseada de comentarios XML duplicados y mantiene los comentarios XML sincronizados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="92af1-194">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>

[!code-csharp-interactive[InheritDoc Tag](~/samples/snippets/csharp/concepts/codedoc/inheritdoc-tag.cs)]

### <a name="put-it-all-together"></a><span data-ttu-id="92af1-195">En resumen</span><span class="sxs-lookup"><span data-stu-id="92af1-195">Put it all together</span></span>

<span data-ttu-id="92af1-196">Si ha seguido este tutorial y ha aplicado las etiquetas al código en los casos en que era necesario, el código debe ser ahora similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="92af1-196">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](~/samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="92af1-197">Desde su código, puede generar un sitio web de documentación detallada completo con referencias cruzadas interactivas.</span><span class="sxs-lookup"><span data-stu-id="92af1-197">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="92af1-198">Pero se enfrenta a otro problema: su código se ha vuelto difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="92af1-198">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="92af1-199">Es una pesadilla para los desarrolladores que quieran contribuir a este código, ya que hay mucha información que examinar.</span><span class="sxs-lookup"><span data-stu-id="92af1-199">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="92af1-200">Afortunadamente, hay una etiqueta XML que le ayudará a resolverlo:</span><span class="sxs-lookup"><span data-stu-id="92af1-200">Thankfully there's an XML tag that can help you deal with this:</span></span>

## <a name="include"></a><span data-ttu-id="92af1-201">\<include></span><span class="sxs-lookup"><span data-stu-id="92af1-201">\<include></span></span>

<span data-ttu-id="92af1-202">La etiqueta `<include>` le permite hacer referencia a los comentarios de un archivo XML independiente que describen los tipos y los miembros del código fuente, en vez de colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="92af1-202">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="92af1-203">Ahora vamos a mover todas las etiquetas XML a un archivo XML independiente denominado `docs.xml`.</span><span class="sxs-lookup"><span data-stu-id="92af1-203">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="92af1-204">Puede ponerle al archivo el nombre que quiera.</span><span class="sxs-lookup"><span data-stu-id="92af1-204">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](~/samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="92af1-205">En el XML anterior, los comentarios de documentación de cada miembro aparecen directamente dentro de una etiqueta cuyo nombre indica lo que hacen,</span><span class="sxs-lookup"><span data-stu-id="92af1-205">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="92af1-206">pero puede elegir su propia estrategia.</span><span class="sxs-lookup"><span data-stu-id="92af1-206">You can choose your own strategy.</span></span>
<span data-ttu-id="92af1-207">Ahora que tiene los comentarios XML en un archivo independiente, veamos cómo se puede hacer más legible el código mediante la etiqueta `<include>`:</span><span class="sxs-lookup"><span data-stu-id="92af1-207">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](~/samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="92af1-208">Aquí lo tiene: el código vuelve a ser legible y no se ha perdido ninguna información de documentación.</span><span class="sxs-lookup"><span data-stu-id="92af1-208">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="92af1-209">El atributo `file` representa el nombre del archivo XML que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="92af1-209">The `file` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="92af1-210">El atributo `path` representa una consulta [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) para el `tag name` presente en el `file` especificado.</span><span class="sxs-lookup"><span data-stu-id="92af1-210">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `file`.</span></span>

<span data-ttu-id="92af1-211">El atributo `name` representa el especificador de nombre en la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="92af1-211">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="92af1-212">El atributo `id`, que se puede usar en lugar de `name`, representa el identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="92af1-212">The `id` attribute, which can be used in place of `name`, represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="92af1-213">Etiquetas definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="92af1-213">User-defined tags</span></span>

<span data-ttu-id="92af1-214">Todas las etiquetas descritas anteriormente son las que reconoce el compilador de C#,</span><span class="sxs-lookup"><span data-stu-id="92af1-214">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="92af1-215">pero el usuario puede definir sus propias etiquetas.</span><span class="sxs-lookup"><span data-stu-id="92af1-215">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="92af1-216">Las herramientas como Sandcastle proporcionan compatibilidad con etiquetas adicionales como [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) y [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), e incluso permiten [documentar espacios de nombres](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span><span class="sxs-lookup"><span data-stu-id="92af1-216">Tools like Sandcastle bring support for extra tags like [\<event>](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) and [\<note>](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm), and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="92af1-217">También se pueden usar herramientas de generación de documentación internas o personalizadas con las etiquetas estándar y se admiten varios formatos de salida, de HTML a PDF.</span><span class="sxs-lookup"><span data-stu-id="92af1-217">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="92af1-218">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="92af1-218">Recommendations</span></span>

<span data-ttu-id="92af1-219">Se recomienda documentar código por diversos motivos.</span><span class="sxs-lookup"><span data-stu-id="92af1-219">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="92af1-220">A continuación se muestran algunos procedimientos recomendados, escenarios generales de casos de uso y conceptos que debe conocer al usar etiquetas de documentación XML en el código de C#.</span><span class="sxs-lookup"><span data-stu-id="92af1-220">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

- <span data-ttu-id="92af1-221">Por motivos de coherencia, se deben documentar todos los tipos públicamente visibles y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="92af1-221">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="92af1-222">Si debe hacerlo, hágalo en todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="92af1-222">If you must do it, do it all.</span></span>
- <span data-ttu-id="92af1-223">Los miembros privados también se pueden documentar mediante comentarios XML,</span><span class="sxs-lookup"><span data-stu-id="92af1-223">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="92af1-224">pero esto expone el funcionamiento interno (potencialmente confidencial) de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="92af1-224">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
- <span data-ttu-id="92af1-225">Como mínimo, los tipos y sus miembros deben tener una etiqueta `<summary>`, ya que su contenido es necesario para IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="92af1-225">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
- <span data-ttu-id="92af1-226">El texto de la documentación se debe escribir con frases completas que terminen en punto.</span><span class="sxs-lookup"><span data-stu-id="92af1-226">Documentation text should be written using complete sentences ending with full stops.</span></span>
- <span data-ttu-id="92af1-227">Las clases parciales son totalmente compatibles y la información de documentación se concatenará en una única entrada para ese tipo.</span><span class="sxs-lookup"><span data-stu-id="92af1-227">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
- <span data-ttu-id="92af1-228">El compilador comprueba la sintaxis de las etiquetas `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` y `<typeparam>`.</span><span class="sxs-lookup"><span data-stu-id="92af1-228">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>`, and `<typeparam>` tags.</span></span>
- <span data-ttu-id="92af1-229">El compilador valida los parámetros que contienen rutas de acceso de archivo y referencias a otras partes del código.</span><span class="sxs-lookup"><span data-stu-id="92af1-229">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="92af1-230">Vea también</span><span class="sxs-lookup"><span data-stu-id="92af1-230">See also</span></span>

- [<span data-ttu-id="92af1-231">Comentarios de documentación XML (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="92af1-231">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/index.md)
- [<span data-ttu-id="92af1-232">Etiquetas recomendadas para comentarios de documentación (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="92af1-232">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
