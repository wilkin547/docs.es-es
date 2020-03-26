---
title: Cree componentes de interfaz de usuario reutilizables con Blazor
description: Aprenda a crear componentes de interfaz de usuario reutilizables con Blazor y cómo se comparan con ASP.NET controles de formularios Web Forms.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 228f7aec4c7b87cb6d4127b55745f7a5ed90aaf9
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228620"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="c184c-103">Cree componentes de interfaz de usuario reutilizables con Blazor</span><span class="sxs-lookup"><span data-stu-id="c184c-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c184c-104">Una de las cosas hermosas de ASP.NET formularios Web Forms es cómo permite la encapsulación de partes reutilizables de código de interfaz de usuario (UI) en controles de interfaz de usuario reutilizables.</span><span class="sxs-lookup"><span data-stu-id="c184c-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="c184c-105">Los controles de usuario personalizados se pueden definir en el marcado mediante archivos *.ascx.*</span><span class="sxs-lookup"><span data-stu-id="c184c-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="c184c-106">También puede crear controles de servidor elaborados en código con compatibilidad completa con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="c184c-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="c184c-107">Blazor también admite la encapsulación de la interfaz de usuario a través de *componentes.*</span><span class="sxs-lookup"><span data-stu-id="c184c-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="c184c-108">Un componente:</span><span class="sxs-lookup"><span data-stu-id="c184c-108">A component:</span></span>

- <span data-ttu-id="c184c-109">Es un fragmento independiente de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c184c-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="c184c-110">Mantiene su propio estado y lógica de representación.</span><span class="sxs-lookup"><span data-stu-id="c184c-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="c184c-111">Puede definir controladores de eventos de interfaz de usuario, enlazar a datos de entrada y administrar su propio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="c184c-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="c184c-112">Normalmente se define en un archivo *.razor* mediante la sintaxis de Razor.</span><span class="sxs-lookup"><span data-stu-id="c184c-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="c184c-113">Una introducción a Razor</span><span class="sxs-lookup"><span data-stu-id="c184c-113">An introduction to Razor</span></span>

<span data-ttu-id="c184c-114">Razor es un lenguaje de plantillas de marcado ligero basado en HTML y C.</span><span class="sxs-lookup"><span data-stu-id="c184c-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="c184c-115">Con Razor, puede realizar una transición sin problemas entre el marcado y el código de C- para definir la lógica de representación de componentes.</span><span class="sxs-lookup"><span data-stu-id="c184c-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="c184c-116">Cuando se compila el archivo *.razor,* la lógica de representación se captura de forma estructurada en una clase .NET.</span><span class="sxs-lookup"><span data-stu-id="c184c-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="c184c-117">El nombre de la clase compilada se toma del nombre de archivo *.razor.*</span><span class="sxs-lookup"><span data-stu-id="c184c-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="c184c-118">El espacio de nombres se toma del espacio de nombres predeterminado para el `@namespace` proyecto y la ruta de acceso de la carpeta, o puede especificar explícitamente el espacio de nombres mediante la directiva (más información sobre las directivas Razor a continuación).</span><span class="sxs-lookup"><span data-stu-id="c184c-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="c184c-119">La lógica de representación de un componente se crea mediante el marcado HTML normal con lógica dinámica agregada mediante C.</span><span class="sxs-lookup"><span data-stu-id="c184c-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="c184c-120">El `@` carácter se utiliza para la transición a C.</span><span class="sxs-lookup"><span data-stu-id="c184c-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="c184c-121">Razor suele ser inteligente para averiguar cuándo has vuelto a HTML.</span><span class="sxs-lookup"><span data-stu-id="c184c-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="c184c-122">Por ejemplo, el siguiente `<p>` componente representa una etiqueta con la hora actual:</span><span class="sxs-lookup"><span data-stu-id="c184c-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="c184c-123">Para especificar explícitamente el principio y el final de una expresión de C- , utilice paréntesis:</span><span class="sxs-lookup"><span data-stu-id="c184c-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="c184c-124">Razor también facilita el uso del flujo de control de C- en la lógica de representación.</span><span class="sxs-lookup"><span data-stu-id="c184c-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="c184c-125">Por ejemplo, puede representar condicionalmente algunos HTML como este:</span><span class="sxs-lookup"><span data-stu-id="c184c-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="c184c-126">O bien, puede generar una lista `foreach` de elementos utilizando un bucle normal de C- como este:</span><span class="sxs-lookup"><span data-stu-id="c184c-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="c184c-127">Las directivas de Razor, como las directivas de ASP.NET formularios Web Forms, controlan muchos aspectos de cómo se compila un componente Razor.</span><span class="sxs-lookup"><span data-stu-id="c184c-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="c184c-128">Algunos ejemplos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c184c-128">Examples include the component's:</span></span>

- <span data-ttu-id="c184c-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c184c-129">Namespace</span></span>
- <span data-ttu-id="c184c-130">Clase base</span><span class="sxs-lookup"><span data-stu-id="c184c-130">Base class</span></span>
- <span data-ttu-id="c184c-131">Interfaces implementadas</span><span class="sxs-lookup"><span data-stu-id="c184c-131">Implemented interfaces</span></span>
- <span data-ttu-id="c184c-132">Parámetros genéricos</span><span class="sxs-lookup"><span data-stu-id="c184c-132">Generic parameters</span></span>
- <span data-ttu-id="c184c-133">Espacios de nombres importados</span><span class="sxs-lookup"><span data-stu-id="c184c-133">Imported namespaces</span></span>
- <span data-ttu-id="c184c-134">Rutas</span><span class="sxs-lookup"><span data-stu-id="c184c-134">Routes</span></span>

<span data-ttu-id="c184c-135">Las directivas de `@` Razor comienzan con el carácter y se usan normalmente al principio de una nueva línea al principio del archivo.</span><span class="sxs-lookup"><span data-stu-id="c184c-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="c184c-136">Por ejemplo, `@namespace` la directiva define el espacio de nombres del componente:</span><span class="sxs-lookup"><span data-stu-id="c184c-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="c184c-137">En la tabla siguiente se resumen las diversas directivas Razor utilizadas en Blazor y sus equivalentes de formularios Web Forms ASP.NET, si existen.</span><span class="sxs-lookup"><span data-stu-id="c184c-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="c184c-138">Directiva</span><span class="sxs-lookup"><span data-stu-id="c184c-138">Directive</span></span>    |<span data-ttu-id="c184c-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="c184c-139">Description</span></span>|<span data-ttu-id="c184c-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c184c-140">Example</span></span>|<span data-ttu-id="c184c-141">Formularios Web equivalentes</span><span class="sxs-lookup"><span data-stu-id="c184c-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="c184c-142">Agrega un atributo de nivel de clase al componente</span><span class="sxs-lookup"><span data-stu-id="c184c-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="c184c-143">None</span><span class="sxs-lookup"><span data-stu-id="c184c-143">None</span></span>|
|`@code`      |<span data-ttu-id="c184c-144">Agrega miembros de clase al componente</span><span class="sxs-lookup"><span data-stu-id="c184c-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="c184c-145">Implementa la interfaz especificada</span><span class="sxs-lookup"><span data-stu-id="c184c-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="c184c-146">Uso de código subyacente</span><span class="sxs-lookup"><span data-stu-id="c184c-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="c184c-147">Hereda de la clase base especificada</span><span class="sxs-lookup"><span data-stu-id="c184c-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="c184c-148">Inyecta un servicio en el componente</span><span class="sxs-lookup"><span data-stu-id="c184c-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="c184c-149">None</span><span class="sxs-lookup"><span data-stu-id="c184c-149">None</span></span>|
|`@layout`    |<span data-ttu-id="c184c-150">Especifica un componente de diseño para el componente</span><span class="sxs-lookup"><span data-stu-id="c184c-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="c184c-151">Establece el espacio de nombres para el componente</span><span class="sxs-lookup"><span data-stu-id="c184c-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="c184c-152">None</span><span class="sxs-lookup"><span data-stu-id="c184c-152">None</span></span>|
|`@page`      |<span data-ttu-id="c184c-153">Especifica la ruta del componente</span><span class="sxs-lookup"><span data-stu-id="c184c-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="c184c-154">Especifica un parámetro de tipo genérico para el componente</span><span class="sxs-lookup"><span data-stu-id="c184c-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="c184c-155">Uso de código subyacente</span><span class="sxs-lookup"><span data-stu-id="c184c-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="c184c-156">Especifica un espacio de nombres para incorporar al ámbito</span><span class="sxs-lookup"><span data-stu-id="c184c-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="c184c-157">Agregar espacio de nombres en *web.config*</span><span class="sxs-lookup"><span data-stu-id="c184c-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="c184c-158">Los componentes de Razor también hacen un uso extensivo de *atributos* de directiva en los elementos para controlar varios aspectos de cómo se compilan los componentes (control de eventos, enlace de datos, referencias de elementos & componentes, etc.).</span><span class="sxs-lookup"><span data-stu-id="c184c-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="c184c-159">Todos los atributos de directiva siguen una sintaxis genérica común en la que los valores entre paréntesis son opcionales:</span><span class="sxs-lookup"><span data-stu-id="c184c-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="c184c-160">En la tabla siguiente se resumen los distintos atributos de las directivas Razor utilizadas en Blazor.</span><span class="sxs-lookup"><span data-stu-id="c184c-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="c184c-161">Atributo</span><span class="sxs-lookup"><span data-stu-id="c184c-161">Attribute</span></span>    |<span data-ttu-id="c184c-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="c184c-162">Description</span></span>|<span data-ttu-id="c184c-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c184c-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="c184c-164">Representa un diccionario de atributos</span><span class="sxs-lookup"><span data-stu-id="c184c-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="c184c-165">Crea un enlace de datos bidireccional</span><span class="sxs-lookup"><span data-stu-id="c184c-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="c184c-166">Agrega un controlador de eventos para el evento especificado</span><span class="sxs-lookup"><span data-stu-id="c184c-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="c184c-167">Especifica una clave que utilizará el algoritmo de diferenciación para conservar los elementos de una colección</span><span class="sxs-lookup"><span data-stu-id="c184c-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="c184c-168">Captura una referencia al componente o elemento HTML</span><span class="sxs-lookup"><span data-stu-id="c184c-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="c184c-169">Los distintos atributos de`@onclick`directiva `@bind` `@ref`utilizados por Blazor ( , , , , etc.) se tratan en las secciones siguientes y capítulos posteriores.</span><span class="sxs-lookup"><span data-stu-id="c184c-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="c184c-170">Muchas de las sintaxis utilizadas en archivos *.aspx* y *.ascx* tienen sintaxis paralelas en Razor.</span><span class="sxs-lookup"><span data-stu-id="c184c-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="c184c-171">A continuación se muestra una comparación sencilla de las sintaxis de ASP.NET Web Forms y Razor.</span><span class="sxs-lookup"><span data-stu-id="c184c-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="c184c-172">Característica</span><span class="sxs-lookup"><span data-stu-id="c184c-172">Feature</span></span>                      |<span data-ttu-id="c184c-173">Formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="c184c-173">Web Forms</span></span>           |<span data-ttu-id="c184c-174">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c184c-174">Syntax</span></span>               |<span data-ttu-id="c184c-175">Razor</span><span class="sxs-lookup"><span data-stu-id="c184c-175">Razor</span></span>         |<span data-ttu-id="c184c-176">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c184c-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="c184c-177">Directivas</span><span class="sxs-lookup"><span data-stu-id="c184c-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="c184c-178">Bloques de código</span><span class="sxs-lookup"><span data-stu-id="c184c-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="c184c-179">Expresiones</span><span class="sxs-lookup"><span data-stu-id="c184c-179">Expressions</span></span><br><span data-ttu-id="c184c-180">(codificado en HTML)</span><span class="sxs-lookup"><span data-stu-id="c184c-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="c184c-181">Implícita:`@`</span><span class="sxs-lookup"><span data-stu-id="c184c-181">Implicit: `@`</span></span><br><span data-ttu-id="c184c-182">Explícito:`@()`</span><span class="sxs-lookup"><span data-stu-id="c184c-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="c184c-183">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c184c-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="c184c-184">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="c184c-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="c184c-185">Para agregar miembros a la `@code` clase de componente Razor, utilice la directiva.</span><span class="sxs-lookup"><span data-stu-id="c184c-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="c184c-186">Esta técnica es similar `<script runat="server">...</script>` al uso de un bloque en una página o control de usuario de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c184c-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="c184c-187">Debido a que Razor se basa en C- , debe compilarse desde dentro de un proyecto de C - (*.csproj*).</span><span class="sxs-lookup"><span data-stu-id="c184c-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="c184c-188">No se pueden compilar archivos *.razor* desde un proyecto de Visual Basic (*.vbproj*).</span><span class="sxs-lookup"><span data-stu-id="c184c-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="c184c-189">Todavía puede hacer referencia a proyectos de Visual Basic desde el proyecto Blazor.</span><span class="sxs-lookup"><span data-stu-id="c184c-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="c184c-190">Lo contrario también es cierto.</span><span class="sxs-lookup"><span data-stu-id="c184c-190">The opposite is true too.</span></span>

<span data-ttu-id="c184c-191">Para obtener una referencia de sintaxis de Razor completa, consulte Referencia de [sintaxis](/aspnet/core/mvc/views/razor)de Razor para ASP.NET Core .</span><span class="sxs-lookup"><span data-stu-id="c184c-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="c184c-192">Uso de componentes</span><span class="sxs-lookup"><span data-stu-id="c184c-192">Use components</span></span>

<span data-ttu-id="c184c-193">Aparte de HTML normal, los componentes también pueden utilizar otros componentes como parte de su lógica de representación.</span><span class="sxs-lookup"><span data-stu-id="c184c-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="c184c-194">La sintaxis para usar un componente en Razor es similar al uso de un control de usuario en una aplicación de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c184c-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="c184c-195">Los componentes se especifican mediante una etiqueta de elemento que coincide con el nombre de tipo del componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="c184c-196">Por ejemplo, puede `Counter` agregar un componente como este:</span><span class="sxs-lookup"><span data-stu-id="c184c-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="c184c-197">A diferencia de ASP.NET formularios Web Forms, los componentes de Blazor:</span><span class="sxs-lookup"><span data-stu-id="c184c-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="c184c-198">No utilice un prefijo de elemento `asp:`(por ejemplo, ).</span><span class="sxs-lookup"><span data-stu-id="c184c-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="c184c-199">No es necesario registrarse en la página o en *el archivo web.config*.</span><span class="sxs-lookup"><span data-stu-id="c184c-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="c184c-200">Piense en los componentes de Razor como lo haría con los tipos .NET, porque eso es exactamente lo que son.</span><span class="sxs-lookup"><span data-stu-id="c184c-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="c184c-201">Si se hace referencia al ensamblaje que contiene el componente, el componente está disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="c184c-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="c184c-202">Para incorporar el espacio de nombres `@using` del componente en el ámbito, aplique la directiva:</span><span class="sxs-lookup"><span data-stu-id="c184c-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="c184c-203">Como se ve en los proyectos predeterminados de `@using` Blazor, es común poner directivas en un archivo *_Imports.razor* para que se importen en todos los archivos *.razor* en el mismo directorio y en directorios secundarios.</span><span class="sxs-lookup"><span data-stu-id="c184c-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="c184c-204">Si el espacio de nombres de un componente no está en el ámbito, puede especificar un componente con su nombre de tipo completo, como puede hacer en C-:</span><span class="sxs-lookup"><span data-stu-id="c184c-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="c184c-205">Parámetros del componente</span><span class="sxs-lookup"><span data-stu-id="c184c-205">Component parameters</span></span>

<span data-ttu-id="c184c-206">En ASP.NET formularios Web Forms, puede fluir parámetros y datos a controles mediante propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="c184c-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="c184c-207">Estas propiedades se pueden establecer en el marcado mediante atributos o establecer directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="c184c-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="c184c-208">Los componentes Blazor funcionan de forma similar, aunque `[Parameter]` las propiedades del componente también deben marcarse con el atributo que se debe considerar parámetros de componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="c184c-209">El `Counter` componente siguiente define `IncrementAmount` un parámetro de componente denominado `Counter` que se puede utilizar para especificar la cantidad que se debe incrementar cada vez que se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="c184c-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

```razor
<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    int currentCount = 0;

    [Parameter]
    public int IncrementAmount { get; set; } = 1;

    void IncrementCount()
    {
        currentCount+=IncrementAmount;
    }
}
```

<span data-ttu-id="c184c-210">Para especificar un parámetro de componente en Blazor, utilice un atributo como lo haría en ASP.NET formularios Web Forms:</span><span class="sxs-lookup"><span data-stu-id="c184c-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="c184c-211">Controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="c184c-211">Event handlers</span></span>

<span data-ttu-id="c184c-212">Tanto ASP.NET formularios Web Forms como Blazor proporcionan un modelo de programación basado en eventos para controlar eventos de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c184c-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="c184c-213">Algunos ejemplos de estos eventos son los clics de botón y la entrada de texto.</span><span class="sxs-lookup"><span data-stu-id="c184c-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="c184c-214">En ASP.NET formularios Web Forms, se usan controles de servidor HTML para controlar los eventos de interfaz de usuario expuestos por el DOM, o puede controlar los eventos expuestos por los controles de servidor web.</span><span class="sxs-lookup"><span data-stu-id="c184c-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="c184c-215">Los eventos se exponen en el servidor a través de solicitudes de devolución de formulario.</span><span class="sxs-lookup"><span data-stu-id="c184c-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="c184c-216">Considere el siguiente botón de formularios Web Forms haga clic en ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c184c-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="c184c-217">*Counter.ascx*</span><span class="sxs-lookup"><span data-stu-id="c184c-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="c184c-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="c184c-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="c184c-219">En Blazor, puede registrar controladores para eventos de interfaz de usuario DE DOM directamente mediante atributos de directiva del formulario. `@on{event}`</span><span class="sxs-lookup"><span data-stu-id="c184c-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="c184c-220">El `{event}` marcador de posición representa el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="c184c-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="c184c-221">Por ejemplo, puede escuchar clics de botón como este:</span><span class="sxs-lookup"><span data-stu-id="c184c-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="c184c-222">Los controladores de eventos pueden aceptar un argumento opcional específico del evento para proporcionar más información sobre el evento.</span><span class="sxs-lookup"><span data-stu-id="c184c-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="c184c-223">Por ejemplo, los eventos `MouseEventArgs` del mouse pueden tomar un argumento, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="c184c-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="c184c-224">En lugar de hacer referencia a un grupo de métodos para un controlador de eventos, puede usar una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="c184c-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="c184c-225">Una expresión lambda permite cerrar otros valores en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="c184c-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="c184c-226">Los controladores de eventos se pueden ejecutar de forma sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c184c-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="c184c-227">Por ejemplo, `OnClick` el siguiente controlador de eventos se ejecuta de forma asincrónica:</span><span class="sxs-lookup"><span data-stu-id="c184c-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="c184c-228">Después de controlar un evento, el componente se representa para tener en cuenta los cambios de estado del componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="c184c-229">Con los controladores de eventos asincrónicos, el componente se representa inmediatamente después de que se complete la ejecución del controlador.</span><span class="sxs-lookup"><span data-stu-id="c184c-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="c184c-230">El componente se representa de `Task` nuevo una *vez* completada la asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c184c-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="c184c-231">Este modo de ejecución asincrónica proporciona una oportunidad `Task` para representar alguna interfaz de usuario adecuada mientras la asincrónica todavía está en curso.</span><span class="sxs-lookup"><span data-stu-id="c184c-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="ShowMessage">Get message</button>

@if (showMessage)
{
    @if (message == null)
    {
        <p><em>Loading...</em></p>
    }
    else
    {
        <p>The message is: @message</p>
    }
}

@code
{
    bool showMessage = false;
    string message;

    public async Task ShowMessage()
    {
        showMessage = true;
        message = await MessageService.GetMessageAsync();
    }
}
```

<span data-ttu-id="c184c-232">Los componentes también pueden definir sus propios `EventCallback<TValue>`eventos definiendo un parámetro de componente de tipo .</span><span class="sxs-lookup"><span data-stu-id="c184c-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="c184c-233">Las devoluciones de llamada de eventos admiten todas las variaciones de los controladores de eventos de la interfaz de usuario de DOM: argumentos opcionales, sincrónicos o asincrónicos, grupos de métodos o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="c184c-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="c184c-234">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="c184c-234">Data binding</span></span>

<span data-ttu-id="c184c-235">Blazor proporciona un mecanismo sencillo para enlazar datos de un componente de interfaz de usuario al estado del componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="c184c-236">Este enfoque difiere de las características de ASP.NET formularios Web Forms para enlazar datos de orígenes de datos a controles de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c184c-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="c184c-237">Trataremos el manejo de datos de diferentes fuentes de datos en la sección [Tratamiento de datos.](data.md)</span><span class="sxs-lookup"><span data-stu-id="c184c-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="c184c-238">Para crear un enlace de datos bidireccional desde un componente de `@bind` interfaz de usuario al estado del componente, utilice el atributo directive.</span><span class="sxs-lookup"><span data-stu-id="c184c-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="c184c-239">En el ejemplo siguiente, el valor de `isChecked` la casilla de verificación está enlazado al campo.</span><span class="sxs-lookup"><span data-stu-id="c184c-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="c184c-240">Cuando se representa el componente, el valor de la `isChecked` casilla de verificación se establece en el valor del campo.</span><span class="sxs-lookup"><span data-stu-id="c184c-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="c184c-241">Cuando el usuario alterna la `onchange` casilla de `isChecked` verificación, se desencadena el evento y el campo se establece en el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="c184c-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="c184c-242">La `@bind` sintaxis en este caso es equivalente al siguiente marcado:</span><span class="sxs-lookup"><span data-stu-id="c184c-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="c184c-243">Para cambiar el evento utilizado para `@bind:event` el enlace, utilice el atributo.</span><span class="sxs-lookup"><span data-stu-id="c184c-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="c184c-244">Los componentes también pueden admitir el enlace de datos a sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="c184c-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="c184c-245">Para enlazar datos, defina un parámetro de devolución de llamada de evento con el mismo nombre que el parámetro enlazable.</span><span class="sxs-lookup"><span data-stu-id="c184c-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="c184c-246">El sufijo "Changed" se agrega al nombre.</span><span class="sxs-lookup"><span data-stu-id="c184c-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="c184c-247">*PasswordBox.razor*</span><span class="sxs-lookup"><span data-stu-id="c184c-247">*PasswordBox.razor*</span></span>

```razor
Password: <input
    value="@Password"
    @oninput="OnPasswordChanged"
    type="@(showPassword ? "text" : "password")" />

<label><input type="checkbox" @bind="showPassword" />Show password</label>

@code {
    private bool showPassword;

    [Parameter]
    public string Password { get; set; }

    [Parameter]
    public EventCallback<string> PasswordChanged { get; set; }

    private Task OnPasswordChanged(ChangeEventArgs e)
    {
        Password = e.Value.ToString();
        return PasswordChanged.InvokeAsync(Password);
    }
}
```

<span data-ttu-id="c184c-248">Para encadenar un enlace de datos a un elemento de interfaz de usuario `@bind` subyacente, establezca el valor y controle el evento directamente en el elemento de interfaz de usuario en lugar de usar el atributo.</span><span class="sxs-lookup"><span data-stu-id="c184c-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="c184c-249">Para enlazar a un parámetro `@bind-{Parameter}` de componente, utilice un atributo para especificar el parámetro al que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="c184c-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="c184c-250">Cambios de estado</span><span class="sxs-lookup"><span data-stu-id="c184c-250">State changes</span></span>

<span data-ttu-id="c184c-251">Si el estado del componente ha cambiado fuera de un evento de interfaz de usuario normal o devolución de llamada de eventos, el componente debe indicar manualmente que debe representarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c184c-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="c184c-252">Para indicar que el estado de un `StateHasChanged` componente ha cambiado, llame al método en el componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="c184c-253">En el ejemplo siguiente, un componente `AppState` muestra un mensaje de un servicio que se puede actualizar por otras partes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c184c-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="c184c-254">El componente registra `StateHasChanged` su `AppState.OnChange` método con el evento para que el componente se represente cada vez que se actualiza el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c184c-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        shortlist.Add(itinerary);
        NotifyStateChanged();
    }

    private void NotifyStateChanged() => OnChange?.Invoke();
}
```

```razor
@inject AppState AppState

<p>App message: @AppState.Message</p>

@code {
    protected override void OnInitialized()
    {
        AppState.OnChange += StateHasChanged
    }
}
```

## <a name="component-lifecycle"></a><span data-ttu-id="c184c-255">Ciclo de vida de los componentes</span><span class="sxs-lookup"><span data-stu-id="c184c-255">Component lifecycle</span></span>

<span data-ttu-id="c184c-256">El marco de trabajo de formularios Web Forms ASP.NET tiene métodos de ciclo de vida bien definidos para módulos, páginas y controles.</span><span class="sxs-lookup"><span data-stu-id="c184c-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="c184c-257">Por ejemplo, el siguiente control implementa `Init`controladores de eventos para los eventos , `Load`, y `UnLoad` lifecycle:</span><span class="sxs-lookup"><span data-stu-id="c184c-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="c184c-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="c184c-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="c184c-259">Los componentes de Blazor también tienen un ciclo de vida bien definido.</span><span class="sxs-lookup"><span data-stu-id="c184c-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="c184c-260">El ciclo de vida de un componente se puede utilizar para inicializar el estado del componente e implementar comportamientos avanzados de los componentes.</span><span class="sxs-lookup"><span data-stu-id="c184c-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="c184c-261">Todos los métodos de ciclo de vida de componentes de Blazor tienen versiones sincrónicas y asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="c184c-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="c184c-262">La representación de componentes es sincrónica.</span><span class="sxs-lookup"><span data-stu-id="c184c-262">Component rendering is synchronous.</span></span> <span data-ttu-id="c184c-263">No se puede ejecutar la lógica asincrónica como parte de la representación de componentes.</span><span class="sxs-lookup"><span data-stu-id="c184c-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="c184c-264">Toda la lógica asincrónica debe `async` ejecutarse como parte de un método de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="c184c-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="c184c-265">OnInitialized</span><span class="sxs-lookup"><span data-stu-id="c184c-265">OnInitialized</span></span>

<span data-ttu-id="c184c-266">Los `OnInitialized` `OnInitializedAsync` métodos y se utilizan para inicializar el componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="c184c-267">Normalmente, un componente se inicializa después de que se representa por primera vez.</span><span class="sxs-lookup"><span data-stu-id="c184c-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="c184c-268">Después de inicializar un componente, se puede representar varias veces antes de que finalmente se elimine.</span><span class="sxs-lookup"><span data-stu-id="c184c-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="c184c-269">El `OnInitialized` método es `Page_Load` similar al evento en ASP.NET páginas y controles de formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="c184c-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="c184c-270">OnParametersSet</span><span class="sxs-lookup"><span data-stu-id="c184c-270">OnParametersSet</span></span>

<span data-ttu-id="c184c-271">Los `OnParametersSet` `OnParametersSetAsync` métodos y se llaman cuando un componente ha recibido parámetros de su elemento primario y el valor se asigna a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c184c-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="c184c-272">Estos métodos se ejecutan después de la inicialización del componente y *cada vez que se representa el componente.*</span><span class="sxs-lookup"><span data-stu-id="c184c-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="c184c-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="c184c-273">OnAfterRender</span></span>

<span data-ttu-id="c184c-274">Los `OnAfterRender` `OnAfterRenderAsync` métodos y se llaman después de que un componente haya terminado de renderizar.</span><span class="sxs-lookup"><span data-stu-id="c184c-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="c184c-275">Las referencias de elementos y componentes se rellenan en este punto (más información sobre estos conceptos a continuación).</span><span class="sxs-lookup"><span data-stu-id="c184c-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="c184c-276">La interactividad con el navegador se habilita en este momento.</span><span class="sxs-lookup"><span data-stu-id="c184c-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="c184c-277">Las interacciones con la ejecución de DOM y JavaScript pueden tener lugar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c184c-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

```csharp
protected override void OnAfterRender(bool firstRender)
{
    if (firstRender)
    {
        ...
    }
}
protected override async Task OnAfterRenderAsync(bool firstRender)
{
    if (firstRender)
    {
        await ...
    }
}
```

<span data-ttu-id="c184c-278">`OnAfterRender`y `OnAfterRenderAsync` *no se llaman al preprocesamiento en el servidor.*</span><span class="sxs-lookup"><span data-stu-id="c184c-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="c184c-279">El `firstRender` parámetro `true` es la primera vez que se representa el componente; de lo contrario, su valor es `false`.</span><span class="sxs-lookup"><span data-stu-id="c184c-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="c184c-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="c184c-280">IDisposable</span></span>

<span data-ttu-id="c184c-281">Los componentes de `IDisposable` Blazor se pueden implementar para eliminar recursos cuando el componente se quita de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c184c-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="c184c-282">Un componente Razor `IDispose` se `@implements` puede implementar mediante la directiva:</span><span class="sxs-lookup"><span data-stu-id="c184c-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

```razor
@using System
@implements IDisposable

...

@code {
    public void Dispose()
    {
        ...
    }
}
```

## <a name="capture-component-references"></a><span data-ttu-id="c184c-283">Capturar referencias de componentes</span><span class="sxs-lookup"><span data-stu-id="c184c-283">Capture component references</span></span>

<span data-ttu-id="c184c-284">En ASP.NET formularios Web Forms, es común manipular una instancia de control directamente en el código haciendo referencia a su identificador.</span><span class="sxs-lookup"><span data-stu-id="c184c-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="c184c-285">En Blazor, también es posible capturar y manipular una referencia a un componente, aunque es mucho menos común.</span><span class="sxs-lookup"><span data-stu-id="c184c-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="c184c-286">Para capturar una referencia de componente `@ref` en Blazor, utilice el atributo directive.</span><span class="sxs-lookup"><span data-stu-id="c184c-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="c184c-287">El valor del atributo debe coincidir con el nombre de un campo configurable con el mismo tipo que el componente al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="c184c-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

```razor
<MyLoginDialog @ref="loginDialog" ... />

@code {
    MyLoginDialog loginDialog;

    void OnSomething()
    {
        loginDialog.Show();
    }
}
```

<span data-ttu-id="c184c-288">Cuando se representa el componente primario, el campo se rellena con la instancia del componente secundario.</span><span class="sxs-lookup"><span data-stu-id="c184c-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="c184c-289">A continuación, puede llamar a métodos en la instancia del componente o manipularla de otro modo.</span><span class="sxs-lookup"><span data-stu-id="c184c-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="c184c-290">No se recomienda manipular el estado del componente directamente mediante referencias de componentes.</span><span class="sxs-lookup"><span data-stu-id="c184c-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="c184c-291">Al hacerlo, se evita que el componente se represente automáticamente en los momentos correctos.</span><span class="sxs-lookup"><span data-stu-id="c184c-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="c184c-292">Capturar referencias de elementos</span><span class="sxs-lookup"><span data-stu-id="c184c-292">Capture element references</span></span>

<span data-ttu-id="c184c-293">Los componentes blazor pueden capturar referencias a un elemento.</span><span class="sxs-lookup"><span data-stu-id="c184c-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="c184c-294">A diferencia de los controles de servidor HTML en ASP.NET formularios Web Forms, no se puede manipular el DOM directamente mediante una referencia de elemento en Blazor.</span><span class="sxs-lookup"><span data-stu-id="c184c-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="c184c-295">Blazor maneja la mayoría de las interacciones DOM por usted usando su algoritmo de diferenciación DOM.</span><span class="sxs-lookup"><span data-stu-id="c184c-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="c184c-296">Las referencias de elementos capturadas en Blazor son opacas.</span><span class="sxs-lookup"><span data-stu-id="c184c-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="c184c-297">Sin embargo, se usan para pasar una referencia de elemento específica en una llamada de interoperabilidad de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="c184c-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="c184c-298">Para obtener más información acerca de la interoperabilidad de JavaScript, vea [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="c184c-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="c184c-299">Componentes con plantilla</span><span class="sxs-lookup"><span data-stu-id="c184c-299">Templated components</span></span>

<span data-ttu-id="c184c-300">En ASP.NET formularios Web Forms, puede crear *controles con plantilla.*</span><span class="sxs-lookup"><span data-stu-id="c184c-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="c184c-301">Los controles con plantilla permiten al desarrollador especificar una parte del código HTML utilizado para representar un control contenedor.</span><span class="sxs-lookup"><span data-stu-id="c184c-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="c184c-302">La mecánica de creación de controles de servidor con plantilla es compleja, pero permiten escenarios eficaces para representar datos de una manera personalizable por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c184c-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="c184c-303">Entre los ejemplos `Repeater` de `DataList`controles con plantilla se incluyen y .</span><span class="sxs-lookup"><span data-stu-id="c184c-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="c184c-304">Los componentes Blazor también se pueden plantillar definiendo parámetros de componente de tipo `RenderFragment` o `RenderFragment<T>`.</span><span class="sxs-lookup"><span data-stu-id="c184c-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="c184c-305">A `RenderFragment` representa un fragmento de marcado Razor que el componente puede representar.</span><span class="sxs-lookup"><span data-stu-id="c184c-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="c184c-306">A `RenderFragment<T>` es un fragmento de marcado de Razor que toma un parámetro que se puede especificar cuando se representa el fragmento de representación.</span><span class="sxs-lookup"><span data-stu-id="c184c-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="c184c-307">Contenido infantil</span><span class="sxs-lookup"><span data-stu-id="c184c-307">Child content</span></span>

<span data-ttu-id="c184c-308">Los componentes de Blazor `RenderFragment` pueden capturar su contenido secundario como a y representar ese contenido como parte de la representación de componentes.</span><span class="sxs-lookup"><span data-stu-id="c184c-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="c184c-309">Para capturar contenido secundario, defina `RenderFragment` un parámetro `ChildContent`de componente de tipo y asímócelo.</span><span class="sxs-lookup"><span data-stu-id="c184c-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="c184c-310">*ChildContentComponent.razor*</span><span class="sxs-lookup"><span data-stu-id="c184c-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="c184c-311">A continuación, un componente primario puede proporcionar contenido secundario mediante la sintaxis normal de Razor.</span><span class="sxs-lookup"><span data-stu-id="c184c-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="c184c-312">Parámetros de plantilla</span><span class="sxs-lookup"><span data-stu-id="c184c-312">Template parameters</span></span>

<span data-ttu-id="c184c-313">Un componente Blazor con plantilla también puede `RenderFragment` `RenderFragment<T>`definir varios parámetros de componente de tipo o .</span><span class="sxs-lookup"><span data-stu-id="c184c-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="c184c-314">El parámetro `RenderFragment<T>` para a se puede especificar cuando se invoca.</span><span class="sxs-lookup"><span data-stu-id="c184c-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="c184c-315">Para especificar un parámetro de tipo `@typeparam` genérico para un componente, utilice la directiva Razor.</span><span class="sxs-lookup"><span data-stu-id="c184c-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="c184c-316">*SimpleListView.razor*</span><span class="sxs-lookup"><span data-stu-id="c184c-316">*SimpleListView.razor*</span></span>

```razor
@typeparam TItem

@Heading

<ul>
@foreach (var item in Items)
{
    <li>@ItemTemplate(item)</li>
}
</ul>

@code {
    [Parameter]
    public RenderFragment Heading { get; set; }

    [Parameter]
    public RenderFragment<TItem> ItemTemplate { get; set; }

    [Parameter]
    public IEnumerable<TItem> Items { get; set; }
}
```

<span data-ttu-id="c184c-317">Cuando se utiliza un componente con plantilla, los parámetros de plantilla se pueden especificar mediante elementos secundarios que coinciden con los nombres de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="c184c-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="c184c-318">Los argumentos `RenderFragment<T>` de componente de tipo `context`pasados como elementos tienen un parámetro implícito denominado .</span><span class="sxs-lookup"><span data-stu-id="c184c-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="c184c-319">Puede cambiar el nombre de este `Context` parámetro implement mediante el atributo del elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="c184c-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="c184c-320">Los parámetros de tipo genérico se pueden especificar mediante un atributo que coincida con el nombre del parámetro type.</span><span class="sxs-lookup"><span data-stu-id="c184c-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="c184c-321">El parámetro type se deducirá si es posible:</span><span class="sxs-lookup"><span data-stu-id="c184c-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Content="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="c184c-322">La salida de este componente tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="c184c-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="c184c-323">Código subyacente</span><span class="sxs-lookup"><span data-stu-id="c184c-323">Code-behind</span></span>

<span data-ttu-id="c184c-324">Un componente Blazor se crea normalmente en un único archivo *.razor.*</span><span class="sxs-lookup"><span data-stu-id="c184c-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="c184c-325">Sin embargo, también es posible separar el código y el marcado mediante un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="c184c-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="c184c-326">Para utilizar un archivo de componente, agregue un archivo de Cá que coincida con el nombre de archivo del archivo de componente pero con una extensión *.cs* agregada (*Counter.razor.cs*).</span><span class="sxs-lookup"><span data-stu-id="c184c-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="c184c-327">Utilice el archivo de C- para definir una clase base para el componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="c184c-328">Puede asignar a la clase base el nombre que desee, pero es común asignar a `Base` la`CounterBase`clase el mismo nombre que la clase de componente, pero con una extensión agregada ( ).</span><span class="sxs-lookup"><span data-stu-id="c184c-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="c184c-329">La clase basada en componentes también debe derivar de `ComponentBase`.</span><span class="sxs-lookup"><span data-stu-id="c184c-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="c184c-330">A continuación, en el archivo `@inherits` de componente Razor, agregue`@inherits CounterBase`la directiva para especificar la clase base para el componente ( ).</span><span class="sxs-lookup"><span data-stu-id="c184c-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="c184c-331">*Counter.razor*</span><span class="sxs-lookup"><span data-stu-id="c184c-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="c184c-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="c184c-332">*Counter.razor.cs*</span></span>

```csharp
public class CounterBase : ComponentBase
{
    protected int currentCount = 0;

    protected void IncrementCount()
    {
        currentCount++;
    }
}
```

<span data-ttu-id="c184c-333">La visibilidad de los miembros del componente `protected` `public` en la clase base debe ser o para ser visible para la clase de componente.</span><span class="sxs-lookup"><span data-stu-id="c184c-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c184c-334">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c184c-334">Additional resources</span></span>

<span data-ttu-id="c184c-335">Lo anterior no es un tratamiento exhaustivo de todos los aspectos de los componentes de Blazor.</span><span class="sxs-lookup"><span data-stu-id="c184c-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="c184c-336">Para obtener más información sobre cómo [crear y utilizar componentes de ASP.NET Core Razor,](/aspnet/core/blazor/components)consulte la documentación de Blazor.</span><span class="sxs-lookup"><span data-stu-id="c184c-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c184c-337">[Anterior](app-startup.md)
>[Siguiente](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="c184c-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
