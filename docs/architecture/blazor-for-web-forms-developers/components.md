---
title: Cree componentes de interfaz de usuario reutilizables con Blazor
description: Aprenda a crear componentes de interfaz de usuario reutilizables con Blazor y cómo se comparan con los controles de formularios Web Forms de ASP.net.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/18/2019
ms.openlocfilehash: fd560c84c095dffc3718a7709af904d9ba722a18
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512774"
---
# <a name="build-reusable-ui-components-with-no-locblazor"></a><span data-ttu-id="7c990-103">Cree componentes de interfaz de usuario reutilizables con Blazor</span><span class="sxs-lookup"><span data-stu-id="7c990-103">Build reusable UI components with Blazor</span></span>

<span data-ttu-id="7c990-104">Una de las cosas atractivas sobre los formularios Web Forms de ASP.NET es cómo permite la encapsulación de partes reutilizables del código de la interfaz de usuario (IU) en controles de interfaz de usuario reutilizables.</span><span class="sxs-lookup"><span data-stu-id="7c990-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="7c990-105">Los controles de usuario personalizados se pueden definir en el marcado mediante archivos *. ascx* .</span><span class="sxs-lookup"><span data-stu-id="7c990-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="7c990-106">También puede crear controles de servidor elaborados en el código con compatibilidad completa con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="7c990-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="7c990-107">Blazor también admite la encapsulación de la interfaz de usuario a través de *componentes*.</span><span class="sxs-lookup"><span data-stu-id="7c990-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="7c990-108">Un componente:</span><span class="sxs-lookup"><span data-stu-id="7c990-108">A component:</span></span>

- <span data-ttu-id="7c990-109">Es un fragmento independiente de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="7c990-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="7c990-110">Mantiene su propia lógica de representación y estado.</span><span class="sxs-lookup"><span data-stu-id="7c990-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="7c990-111">Puede definir controladores de eventos de la interfaz de usuario, enlazar a datos de entrada y administrar su propio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="7c990-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="7c990-112">Normalmente se define en un archivo *. Razor* mediante sintaxis Razor.</span><span class="sxs-lookup"><span data-stu-id="7c990-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="7c990-113">Introducción a Razor</span><span class="sxs-lookup"><span data-stu-id="7c990-113">An introduction to Razor</span></span>

<span data-ttu-id="7c990-114">Razor es un lenguaje de plantillas de marcado ligero basado en HTML y C#.</span><span class="sxs-lookup"><span data-stu-id="7c990-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="7c990-115">Con Razor, puede realizar una transición sin problemas entre código de marcado y C# para definir la lógica de representación de componentes.</span><span class="sxs-lookup"><span data-stu-id="7c990-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="7c990-116">Cuando se compila el archivo *. Razor* , la lógica de representación se captura de forma estructurada en una clase .net.</span><span class="sxs-lookup"><span data-stu-id="7c990-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="7c990-117">El nombre de la clase compilada se toma del nombre de archivo *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="7c990-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="7c990-118">El espacio de nombres se toma del espacio de nombres predeterminado para el proyecto y la ruta de acceso de la carpeta, o bien se puede especificar explícitamente el espacio de nombres mediante la `@namespace` Directiva (más información sobre las directivas de Razor a continuación).</span><span class="sxs-lookup"><span data-stu-id="7c990-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="7c990-119">La lógica de representación de un componente se crea mediante el marcado HTML normal con lógica dinámica agregada mediante C#.</span><span class="sxs-lookup"><span data-stu-id="7c990-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="7c990-120">El `@` carácter se usa para realizar la transición a C#.</span><span class="sxs-lookup"><span data-stu-id="7c990-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="7c990-121">Razor suele ser una forma inteligente de averiguar cuándo ha cambiado a HTML.</span><span class="sxs-lookup"><span data-stu-id="7c990-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="7c990-122">Por ejemplo, el siguiente componente representa una `<p>` etiqueta con la hora actual:</span><span class="sxs-lookup"><span data-stu-id="7c990-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="7c990-123">Para especificar explícitamente el principio y el final de una expresión de C#, use paréntesis:</span><span class="sxs-lookup"><span data-stu-id="7c990-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="7c990-124">Razor también facilita el uso del flujo de control de C# en la lógica de representación.</span><span class="sxs-lookup"><span data-stu-id="7c990-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="7c990-125">Por ejemplo, puede representar condicionalmente un código HTML similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c990-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="7c990-126">O bien, puede generar una lista de elementos mediante un bucle normal de C# `foreach` como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c990-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="7c990-127">Las directivas de Razor, como las directivas de formularios Web Forms de ASP.NET, controlan muchos aspectos de cómo se compila un componente de Razor.</span><span class="sxs-lookup"><span data-stu-id="7c990-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="7c990-128">Algunos ejemplos son:</span><span class="sxs-lookup"><span data-stu-id="7c990-128">Examples include the component's:</span></span>

- <span data-ttu-id="7c990-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="7c990-129">Namespace</span></span>
- <span data-ttu-id="7c990-130">Clase base</span><span class="sxs-lookup"><span data-stu-id="7c990-130">Base class</span></span>
- <span data-ttu-id="7c990-131">Interfaces implementadas</span><span class="sxs-lookup"><span data-stu-id="7c990-131">Implemented interfaces</span></span>
- <span data-ttu-id="7c990-132">Parámetros genéricos</span><span class="sxs-lookup"><span data-stu-id="7c990-132">Generic parameters</span></span>
- <span data-ttu-id="7c990-133">Espacios de nombres importados</span><span class="sxs-lookup"><span data-stu-id="7c990-133">Imported namespaces</span></span>
- <span data-ttu-id="7c990-134">Rutas</span><span class="sxs-lookup"><span data-stu-id="7c990-134">Routes</span></span>

<span data-ttu-id="7c990-135">Las directivas de Razor comienzan con el `@` carácter y suelen usarse al principio de una nueva línea al principio del archivo.</span><span class="sxs-lookup"><span data-stu-id="7c990-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="7c990-136">Por ejemplo, la `@namespace` Directiva define el espacio de nombres del componente:</span><span class="sxs-lookup"><span data-stu-id="7c990-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="7c990-137">En la tabla siguiente se resumen las distintas directivas de Razor usadas en Blazor y sus equivalentes de formularios web forms ASP.net, si existen.</span><span class="sxs-lookup"><span data-stu-id="7c990-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="7c990-138">Directiva</span><span class="sxs-lookup"><span data-stu-id="7c990-138">Directive</span></span>    |<span data-ttu-id="7c990-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c990-139">Description</span></span>|<span data-ttu-id="7c990-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c990-140">Example</span></span>|<span data-ttu-id="7c990-141">Equivalentes de formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="7c990-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="7c990-142">Agrega un atributo de nivel de clase al componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="7c990-143">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7c990-143">None</span></span>|
|`@code`      |<span data-ttu-id="7c990-144">Agrega miembros de clase al componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="7c990-145">Implementa la interfaz especificada.</span><span class="sxs-lookup"><span data-stu-id="7c990-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="7c990-146">Uso de código subyacente</span><span class="sxs-lookup"><span data-stu-id="7c990-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="7c990-147">Hereda de la clase base especificada</span><span class="sxs-lookup"><span data-stu-id="7c990-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="7c990-148">Inserta un servicio en el componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="7c990-149">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7c990-149">None</span></span>|
|`@layout`    |<span data-ttu-id="7c990-150">Especifica un componente de diseño para el componente</span><span class="sxs-lookup"><span data-stu-id="7c990-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="7c990-151">Establece el espacio de nombres del componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="7c990-152">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7c990-152">None</span></span>|
|`@page`      |<span data-ttu-id="7c990-153">Especifica la ruta del componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="7c990-154">Especifica un parámetro de tipo genérico para el componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="7c990-155">Uso de código subyacente</span><span class="sxs-lookup"><span data-stu-id="7c990-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="7c990-156">Especifica un espacio de nombres que se va a incluir en el ámbito</span><span class="sxs-lookup"><span data-stu-id="7c990-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="7c990-157">Agregar espacio de nombres en *web.config*</span><span class="sxs-lookup"><span data-stu-id="7c990-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="7c990-158">Los componentes de Razor también hacen un uso intensivo de *los atributos de la Directiva* en los elementos para controlar diversos aspectos de cómo se compilan los componentes (control de eventos, enlace de datos, referencias de elementos & componentes, etc.).</span><span class="sxs-lookup"><span data-stu-id="7c990-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="7c990-159">Todos los atributos de directiva siguen una sintaxis genérica común en la que los valores entre paréntesis son opcionales:</span><span class="sxs-lookup"><span data-stu-id="7c990-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="7c990-160">En la tabla siguiente se resumen los distintos atributos de las directivas de Razor usadas en Blazor .</span><span class="sxs-lookup"><span data-stu-id="7c990-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="7c990-161">Atributo</span><span class="sxs-lookup"><span data-stu-id="7c990-161">Attribute</span></span>    |<span data-ttu-id="7c990-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c990-162">Description</span></span>|<span data-ttu-id="7c990-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c990-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="7c990-164">Representa un diccionario de atributos.</span><span class="sxs-lookup"><span data-stu-id="7c990-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="7c990-165">Crea un enlace de datos bidireccional</span><span class="sxs-lookup"><span data-stu-id="7c990-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="7c990-166">Agrega un controlador de eventos para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="7c990-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="7c990-167">Especifica una clave que va a usar el algoritmo de comparación para conservar los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="7c990-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="7c990-168">Captura una referencia al componente o elemento HTML.</span><span class="sxs-lookup"><span data-stu-id="7c990-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="7c990-169">Los distintos atributos de directiva utilizados por Blazor ( `@onclick` , `@bind` , `@ref` , etc.) se describen en las secciones siguientes y en los capítulos posteriores.</span><span class="sxs-lookup"><span data-stu-id="7c990-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="7c990-170">Muchas de las sintaxis que se usan en los archivos *. aspx* y *. ascx* tienen sintaxis paralelas en Razor.</span><span class="sxs-lookup"><span data-stu-id="7c990-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="7c990-171">A continuación se muestra una comparación sencilla de las sintaxis de los formularios Web Forms de ASP.NET y Razor.</span><span class="sxs-lookup"><span data-stu-id="7c990-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="7c990-172">Característica</span><span class="sxs-lookup"><span data-stu-id="7c990-172">Feature</span></span>                      |<span data-ttu-id="7c990-173">formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="7c990-173">Web Forms</span></span>           |<span data-ttu-id="7c990-174">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c990-174">Syntax</span></span>               |<span data-ttu-id="7c990-175">Razor</span><span class="sxs-lookup"><span data-stu-id="7c990-175">Razor</span></span>         |<span data-ttu-id="7c990-176">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c990-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="7c990-177">Directivas</span><span class="sxs-lookup"><span data-stu-id="7c990-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="7c990-178">Bloques de código</span><span class="sxs-lookup"><span data-stu-id="7c990-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="7c990-179">Expresiones</span><span class="sxs-lookup"><span data-stu-id="7c990-179">Expressions</span></span><br><span data-ttu-id="7c990-180">(Codificado en HTML)</span><span class="sxs-lookup"><span data-stu-id="7c990-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="7c990-181">Explícito `@`</span><span class="sxs-lookup"><span data-stu-id="7c990-181">Implicit: `@`</span></span><br><span data-ttu-id="7c990-182">Explícita `@()`</span><span class="sxs-lookup"><span data-stu-id="7c990-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="7c990-183">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c990-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="7c990-184">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="7c990-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="7c990-185">Para agregar miembros a la clase de componente Razor, use la `@code` Directiva.</span><span class="sxs-lookup"><span data-stu-id="7c990-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="7c990-186">Esta técnica es similar a usar un `<script runat="server">...</script>` bloque en una página o control de usuario de formularios web forms ASP.net.</span><span class="sxs-lookup"><span data-stu-id="7c990-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="7c990-187">Dado que Razor se basa en C#, se debe compilar desde un proyecto de C# (*. csproj*).</span><span class="sxs-lookup"><span data-stu-id="7c990-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="7c990-188">No se pueden compilar archivos *. Razor* desde un proyecto de Visual Basic (*. vbproj*).</span><span class="sxs-lookup"><span data-stu-id="7c990-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="7c990-189">Todavía puede hacer referencia a proyectos de Visual Basic desde el Blazor proyecto.</span><span class="sxs-lookup"><span data-stu-id="7c990-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="7c990-190">Lo contrario también es true.</span><span class="sxs-lookup"><span data-stu-id="7c990-190">The opposite is true too.</span></span>

<span data-ttu-id="7c990-191">Para obtener una referencia de sintaxis Razor completa, consulte [Sintaxis Razor Reference for ASP.net Core](/aspnet/core/mvc/views/razor).</span><span class="sxs-lookup"><span data-stu-id="7c990-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="7c990-192">Uso de componentes</span><span class="sxs-lookup"><span data-stu-id="7c990-192">Use components</span></span>

<span data-ttu-id="7c990-193">Además del HTML normal, los componentes también pueden usar otros componentes como parte de su lógica de representación.</span><span class="sxs-lookup"><span data-stu-id="7c990-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="7c990-194">La sintaxis para usar un componente en Razor es similar a utilizar un control de usuario en una aplicación de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7c990-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="7c990-195">Los componentes se especifican mediante una etiqueta de elemento que coincide con el nombre de tipo del componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="7c990-196">Por ejemplo, puede Agregar un `Counter` componente como este:</span><span class="sxs-lookup"><span data-stu-id="7c990-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="7c990-197">A diferencia de los formularios Web Forms de ASP.NET, los componentes de Blazor :</span><span class="sxs-lookup"><span data-stu-id="7c990-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="7c990-198">No use un prefijo de elemento (por ejemplo, `asp:` ).</span><span class="sxs-lookup"><span data-stu-id="7c990-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="7c990-199">No es necesario registrarse en la página o en el *web.config*.</span><span class="sxs-lookup"><span data-stu-id="7c990-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="7c990-200">Piense en los componentes de Razor como en los tipos de .NET, ya que eso es exactamente lo que son.</span><span class="sxs-lookup"><span data-stu-id="7c990-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="7c990-201">Si se hace referencia al ensamblado que contiene el componente, el componente está disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="7c990-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="7c990-202">Para poner el espacio de nombres del componente en el ámbito, aplique la `@using` Directiva:</span><span class="sxs-lookup"><span data-stu-id="7c990-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="7c990-203">Como se ve en los proyectos predeterminados Blazor , es habitual colocar `@using` directivas en un archivo *_Imports. Razor* para que se importen en todos los archivos *. Razor* en el mismo directorio y en los directorios secundarios.</span><span class="sxs-lookup"><span data-stu-id="7c990-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="7c990-204">Si el espacio de nombres de un componente no está en el ámbito, puede especificar un componente con su nombre de tipo completo, como puede hacerlo en C#:</span><span class="sxs-lookup"><span data-stu-id="7c990-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="7c990-205">Parámetros del componente</span><span class="sxs-lookup"><span data-stu-id="7c990-205">Component parameters</span></span>

<span data-ttu-id="7c990-206">En los formularios Web Forms de ASP.NET, puede fluir los parámetros y los datos a los controles mediante propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="7c990-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="7c990-207">Estas propiedades se pueden establecer en el marcado mediante atributos o establecerse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="7c990-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="7c990-208">Blazor los componentes funcionan de manera similar, aunque las propiedades del componente también se deben marcar con el `[Parameter]` atributo para que se consideren parámetros de componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="7c990-209">El `Counter` componente siguiente define un parámetro de componente denominado `IncrementAmount` que se puede utilizar para especificar la cantidad que `Counter` se debe incrementar cada vez que se haga clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="7c990-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

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

<span data-ttu-id="7c990-210">Para especificar un parámetro de componente en Blazor , utilice un atributo tal como lo haría en formularios Web Forms de ASP.net:</span><span class="sxs-lookup"><span data-stu-id="7c990-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="7c990-211">Controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="7c990-211">Event handlers</span></span>

<span data-ttu-id="7c990-212">Ambos formularios Web Forms ASP.NET y Blazor proporcionan un modelo de programación basado en eventos para controlar los eventos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="7c990-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="7c990-213">Entre los ejemplos de estos eventos se incluyen los clics de botón y la entrada de texto.</span><span class="sxs-lookup"><span data-stu-id="7c990-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="7c990-214">En los formularios Web Forms de ASP.NET, se usan controles de servidor HTML para controlar los eventos de interfaz de usuario expuestos por el DOM, o se pueden controlar los eventos expuestos por los controles de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="7c990-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="7c990-215">Los eventos se muestran en el servidor a través de solicitudes de reenvío de formulario.</span><span class="sxs-lookup"><span data-stu-id="7c990-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="7c990-216">Considere el siguiente ejemplo de clic de botón de formularios Web Forms:</span><span class="sxs-lookup"><span data-stu-id="7c990-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="7c990-217">*Counter. ascx*</span><span class="sxs-lookup"><span data-stu-id="7c990-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="7c990-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="7c990-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="7c990-219">En Blazor , puede registrar Controladores para eventos de la interfaz de usuario Dom directamente mediante atributos de directiva del formulario `@on{event}` .</span><span class="sxs-lookup"><span data-stu-id="7c990-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="7c990-220">El `{event}` marcador de posición representa el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="7c990-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="7c990-221">Por ejemplo, puede realizar escuchas de clics de botón de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7c990-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="7c990-222">Los controladores de eventos pueden aceptar un argumento opcional específico del evento para proporcionar más información sobre el evento.</span><span class="sxs-lookup"><span data-stu-id="7c990-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="7c990-223">Por ejemplo, los eventos del mouse pueden tomar un `MouseEventArgs` argumento, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="7c990-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="7c990-224">En lugar de hacer referencia a un grupo de métodos para un controlador de eventos, puede usar una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="7c990-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="7c990-225">Una expresión lambda permite cerrar otros valores en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="7c990-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="7c990-226">Los controladores de eventos se pueden ejecutar de forma sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7c990-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="7c990-227">Por ejemplo, el siguiente `OnClick` controlador de eventos se ejecuta de forma asincrónica:</span><span class="sxs-lookup"><span data-stu-id="7c990-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="7c990-228">Una vez que se controla un evento, el componente se representa para tener en cuenta los cambios de estado de componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="7c990-229">Con los controladores de eventos asincrónicos, el componente se representa inmediatamente después de que se complete la ejecución del controlador.</span><span class="sxs-lookup"><span data-stu-id="7c990-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="7c990-230">El componente se representará de *nuevo* después de que se complete la asincrónica `Task` .</span><span class="sxs-lookup"><span data-stu-id="7c990-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="7c990-231">Este modo de ejecución asincrónica proporciona una oportunidad para representar una interfaz de usuario adecuada mientras la asincrónica `Task` todavía está en curso.</span><span class="sxs-lookup"><span data-stu-id="7c990-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

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

<span data-ttu-id="7c990-232">Los componentes también pueden definir sus propios eventos definiendo un parámetro de componente de tipo `EventCallback<TValue>` .</span><span class="sxs-lookup"><span data-stu-id="7c990-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="7c990-233">Las devoluciones de llamada de evento admiten todas las variaciones de los controladores de eventos de la interfaz de usuario DOM: argumentos opcionales, sincrónicos o asincrónicos, grupos de métodos o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="7c990-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="7c990-234">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="7c990-234">Data binding</span></span>

<span data-ttu-id="7c990-235">Blazor proporciona un mecanismo sencillo para enlazar datos de un componente de interfaz de usuario al estado del componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="7c990-236">Este enfoque difiere de las características de los formularios Web Forms de ASP.NET para enlazar datos de orígenes de datos a controles de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="7c990-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="7c990-237">Trataremos el control de los datos de diferentes orígenes de datos en la sección tratamiento de los [datos](data.md) .</span><span class="sxs-lookup"><span data-stu-id="7c990-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="7c990-238">Para crear un enlace de datos bidireccional desde un componente de interfaz de usuario al estado del componente, use el `@bind` atributo de directiva.</span><span class="sxs-lookup"><span data-stu-id="7c990-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="7c990-239">En el ejemplo siguiente, el valor de la casilla está enlazado al `isChecked` campo.</span><span class="sxs-lookup"><span data-stu-id="7c990-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="7c990-240">Cuando se representa el componente, el valor de la casilla se establece en el valor del `isChecked` campo.</span><span class="sxs-lookup"><span data-stu-id="7c990-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="7c990-241">Cuando el usuario activa la casilla, `onchange` se activa el evento y el `isChecked` campo se establece en el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="7c990-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="7c990-242">`@bind`En este caso, la sintaxis es equivalente al marcado siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c990-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="7c990-243">Para cambiar el evento utilizado para el enlace, utilice el `@bind:event` atributo.</span><span class="sxs-lookup"><span data-stu-id="7c990-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="7c990-244">Los componentes también pueden admitir el enlace de datos a sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="7c990-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="7c990-245">Para enlazar datos, defina un parámetro de devolución de llamada de evento con el mismo nombre que el parámetro enlazable.</span><span class="sxs-lookup"><span data-stu-id="7c990-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="7c990-246">El sufijo "Changed" se agrega al nombre.</span><span class="sxs-lookup"><span data-stu-id="7c990-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="7c990-247">*PasswordBox. Razor*</span><span class="sxs-lookup"><span data-stu-id="7c990-247">*PasswordBox.razor*</span></span>

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

<span data-ttu-id="7c990-248">Para encadenar un enlace de datos a un elemento de la interfaz de usuario subyacente, establezca el valor y controle el evento directamente en el elemento de la interfaz de usuario en lugar de usar el `@bind` atributo.</span><span class="sxs-lookup"><span data-stu-id="7c990-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="7c990-249">Para enlazar a un parámetro de componente, use un `@bind-{Parameter}` atributo para especificar el parámetro al que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="7c990-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="7c990-250">Cambios de estado</span><span class="sxs-lookup"><span data-stu-id="7c990-250">State changes</span></span>

<span data-ttu-id="7c990-251">Si el estado del componente ha cambiado fuera de un evento de interfaz de usuario o una devolución de llamada de evento normal, el componente debe indicar manualmente que se debe volver a representar.</span><span class="sxs-lookup"><span data-stu-id="7c990-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="7c990-252">Para indicar que el estado de un componente ha cambiado, llame al `StateHasChanged` método en el componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="7c990-253">En el ejemplo siguiente, un componente muestra un mensaje de un `AppState` servicio que puede ser actualizado por otras partes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c990-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="7c990-254">El componente registra su `StateHasChanged` método con el `AppState.OnChange` evento para que se represente el componente cada vez que se actualice el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7c990-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        Message = message;
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

## <a name="component-lifecycle"></a><span data-ttu-id="7c990-255">Ciclo de vida de los componentes</span><span class="sxs-lookup"><span data-stu-id="7c990-255">Component lifecycle</span></span>

<span data-ttu-id="7c990-256">El marco de trabajo de formularios Web Forms de ASP.NET tiene métodos de ciclo de vida bien definidos para módulos, páginas y controles.</span><span class="sxs-lookup"><span data-stu-id="7c990-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="7c990-257">Por ejemplo, el control siguiente implementa controladores de eventos para los `Init` eventos de `Load` ciclo de `UnLoad` vida, y:</span><span class="sxs-lookup"><span data-stu-id="7c990-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="7c990-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="7c990-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="7c990-259">Blazor los componentes también tienen un ciclo de vida bien definido.</span><span class="sxs-lookup"><span data-stu-id="7c990-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="7c990-260">El ciclo de vida de un componente se puede usar para inicializar el estado del componente e implementar comportamientos de componentes avanzados.</span><span class="sxs-lookup"><span data-stu-id="7c990-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="7c990-261">Todos los Blazor métodos de ciclo de vida de los componentes tienen versiones sincrónicas y asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="7c990-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="7c990-262">La representación de componentes es sincrónica.</span><span class="sxs-lookup"><span data-stu-id="7c990-262">Component rendering is synchronous.</span></span> <span data-ttu-id="7c990-263">No se puede ejecutar la lógica asincrónica como parte de la representación de componentes.</span><span class="sxs-lookup"><span data-stu-id="7c990-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="7c990-264">Toda la lógica asincrónica debe ejecutarse como parte de un `async` método de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="7c990-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="7c990-265">Inicializado</span><span class="sxs-lookup"><span data-stu-id="7c990-265">OnInitialized</span></span>

<span data-ttu-id="7c990-266">Los `OnInitialized` `OnInitializedAsync` métodos y se utilizan para inicializar el componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="7c990-267">Normalmente, un componente se inicializa una vez que se representa por primera vez.</span><span class="sxs-lookup"><span data-stu-id="7c990-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="7c990-268">Una vez inicializado un componente, se puede representar varias veces antes de que se elimine.</span><span class="sxs-lookup"><span data-stu-id="7c990-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="7c990-269">El `OnInitialized` método es similar al `Page_Load` evento en las páginas y controles de formularios Web Forms de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="7c990-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="7c990-270">OnParametersSet</span><span class="sxs-lookup"><span data-stu-id="7c990-270">OnParametersSet</span></span>

<span data-ttu-id="7c990-271">`OnParametersSet` `OnParametersSetAsync` Se llama a los métodos y cuando un componente ha recibido parámetros de su elemento primario y el valor se asigna a propiedades.</span><span class="sxs-lookup"><span data-stu-id="7c990-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="7c990-272">Estos métodos se ejecutan después de la inicialización del componente y *cada vez que se representa el componente*.</span><span class="sxs-lookup"><span data-stu-id="7c990-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="7c990-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="7c990-273">OnAfterRender</span></span>

<span data-ttu-id="7c990-274">`OnAfterRender` `OnAfterRenderAsync` Se llama a los métodos y una vez que un componente ha terminado de representar.</span><span class="sxs-lookup"><span data-stu-id="7c990-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="7c990-275">Las referencias de elementos y componentes se rellenan en este punto (más información sobre estos conceptos a continuación).</span><span class="sxs-lookup"><span data-stu-id="7c990-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="7c990-276">En este momento se habilita la interactividad con el explorador.</span><span class="sxs-lookup"><span data-stu-id="7c990-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="7c990-277">Las interacciones con el DOM y la ejecución de JavaScript pueden tener lugar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="7c990-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

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

<span data-ttu-id="7c990-278">`OnAfterRender` no se llama a y `OnAfterRenderAsync` *al representarse en el servidor*.</span><span class="sxs-lookup"><span data-stu-id="7c990-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="7c990-279">El `firstRender` parámetro es `true` la primera vez que se representa el componente; de lo contrario, su valor es `false` .</span><span class="sxs-lookup"><span data-stu-id="7c990-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="7c990-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="7c990-280">IDisposable</span></span>

<span data-ttu-id="7c990-281">Blazor los componentes pueden implementar `IDisposable` para desechar los recursos cuando el componente se quita de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="7c990-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="7c990-282">Un componente de Razor puede implementar mediante `IDispose` la `@implements` Directiva:</span><span class="sxs-lookup"><span data-stu-id="7c990-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

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

## <a name="capture-component-references"></a><span data-ttu-id="7c990-283">Referencias de componentes de captura</span><span class="sxs-lookup"><span data-stu-id="7c990-283">Capture component references</span></span>

<span data-ttu-id="7c990-284">En los formularios Web Forms de ASP.NET, es habitual manipular una instancia de control directamente en el código haciendo referencia a su identificador.</span><span class="sxs-lookup"><span data-stu-id="7c990-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="7c990-285">En Blazor , también es posible capturar y manipular una referencia a un componente, aunque es mucho menos frecuente.</span><span class="sxs-lookup"><span data-stu-id="7c990-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="7c990-286">Para capturar una referencia de componente en Blazor , utilice el `@ref` atributo de directiva.</span><span class="sxs-lookup"><span data-stu-id="7c990-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="7c990-287">El valor del atributo debe coincidir con el nombre de un campo configurable con el mismo tipo que el componente al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7c990-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

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

<span data-ttu-id="7c990-288">Cuando se representa el componente primario, el campo se rellena con la instancia del componente secundario.</span><span class="sxs-lookup"><span data-stu-id="7c990-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="7c990-289">Después, puede llamar a los métodos en la instancia del componente o manipular de otro modo.</span><span class="sxs-lookup"><span data-stu-id="7c990-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="7c990-290">No se recomienda manipular el estado del componente directamente mediante referencias de componentes.</span><span class="sxs-lookup"><span data-stu-id="7c990-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="7c990-291">Al hacerlo, se impide que el componente se represente automáticamente en los momentos correctos.</span><span class="sxs-lookup"><span data-stu-id="7c990-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="7c990-292">Referencias del elemento Capture</span><span class="sxs-lookup"><span data-stu-id="7c990-292">Capture element references</span></span>

<span data-ttu-id="7c990-293">Blazor los componentes pueden capturar referencias a un elemento.</span><span class="sxs-lookup"><span data-stu-id="7c990-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="7c990-294">A diferencia de los controles de servidor HTML en formularios Web Forms de ASP.NET, no se puede manipular el DOM directamente mediante una referencia de elemento en Blazor .</span><span class="sxs-lookup"><span data-stu-id="7c990-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="7c990-295">Blazor controla la mayoría de las interacciones de DOM con su algoritmo de diferenciación DOM.</span><span class="sxs-lookup"><span data-stu-id="7c990-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="7c990-296">Las referencias del elemento capturado en Blazor son opacas.</span><span class="sxs-lookup"><span data-stu-id="7c990-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="7c990-297">Sin embargo, se utilizan para pasar una referencia de elemento específica en una llamada de interoperabilidad de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="7c990-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="7c990-298">Para obtener más información sobre la interoperabilidad de JavaScript, vea [ASP.net Core Blazor interoperabilidad de JavaScript](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="7c990-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="7c990-299">Componentes con plantilla</span><span class="sxs-lookup"><span data-stu-id="7c990-299">Templated components</span></span>

<span data-ttu-id="7c990-300">En los formularios Web Forms de ASP.NET, puede crear *controles con plantilla*.</span><span class="sxs-lookup"><span data-stu-id="7c990-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="7c990-301">Los controles con plantilla permiten al desarrollador especificar una parte del código HTML que se usa para representar un control de contenedor.</span><span class="sxs-lookup"><span data-stu-id="7c990-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="7c990-302">La mecánica de la creación de controles de servidor con plantilla es compleja, pero habilita escenarios eficaces para representar los datos de forma personalizable.</span><span class="sxs-lookup"><span data-stu-id="7c990-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="7c990-303">Entre los ejemplos de controles con plantilla se incluyen `Repeater` y `DataList` .</span><span class="sxs-lookup"><span data-stu-id="7c990-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="7c990-304">Blazor los componentes también se pueden incluir en la plantilla definiendo los parámetros de componente de tipo `RenderFragment` o `RenderFragment<T>` .</span><span class="sxs-lookup"><span data-stu-id="7c990-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="7c990-305">`RenderFragment`Representa un fragmento de marcado de Razor que se puede representar mediante el componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="7c990-306">Un `RenderFragment<T>` es un fragmento de marcado de Razor que toma un parámetro que se puede especificar cuando se representa el fragmento de representación.</span><span class="sxs-lookup"><span data-stu-id="7c990-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="7c990-307">Contenido secundario</span><span class="sxs-lookup"><span data-stu-id="7c990-307">Child content</span></span>

<span data-ttu-id="7c990-308">Blazor los componentes pueden capturar su contenido secundario como `RenderFragment` y representar ese contenido como parte de la representación de componentes.</span><span class="sxs-lookup"><span data-stu-id="7c990-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="7c990-309">Para capturar contenido secundario, defina un parámetro de componente de tipo `RenderFragment` y asígnele el nombre `ChildContent` .</span><span class="sxs-lookup"><span data-stu-id="7c990-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="7c990-310">*ChildContentComponent. Razor*</span><span class="sxs-lookup"><span data-stu-id="7c990-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="7c990-311">Después, un componente primario puede proporcionar contenido secundario mediante sintaxis Razor normales.</span><span class="sxs-lookup"><span data-stu-id="7c990-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <ChildContent>
        <p>The time is @DateTime.Now</p>
    </ChildContent>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="7c990-312">Parámetros de plantilla</span><span class="sxs-lookup"><span data-stu-id="7c990-312">Template parameters</span></span>

<span data-ttu-id="7c990-313">Un Blazor componente con plantilla también puede definir varios parámetros de componente de tipo `RenderFragment` o `RenderFragment<T>` .</span><span class="sxs-lookup"><span data-stu-id="7c990-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="7c990-314">El parámetro de un `RenderFragment<T>` puede especificarse cuando se invoca.</span><span class="sxs-lookup"><span data-stu-id="7c990-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="7c990-315">Para especificar un parámetro de tipo genérico para un componente, use la `@typeparam` Directiva Razor.</span><span class="sxs-lookup"><span data-stu-id="7c990-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="7c990-316">*SimpleListView. Razor*</span><span class="sxs-lookup"><span data-stu-id="7c990-316">*SimpleListView.razor*</span></span>

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

<span data-ttu-id="7c990-317">Cuando se usa un componente con plantilla, los parámetros de plantilla se pueden especificar utilizando los elementos secundarios que coinciden con los nombres de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="7c990-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="7c990-318">Los argumentos de componente de tipo `RenderFragment<T>` pasados como elementos tienen un parámetro implícito denominado `context` .</span><span class="sxs-lookup"><span data-stu-id="7c990-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="7c990-319">Puede cambiar el nombre de este parámetro de implementación mediante el `Context` atributo en el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="7c990-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="7c990-320">Los parámetros de tipo genérico se pueden especificar mediante un atributo que coincida con el nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="7c990-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="7c990-321">Si es posible, se infiere el parámetro de tipo:</span><span class="sxs-lookup"><span data-stu-id="7c990-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Context="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="7c990-322">La salida de este componente tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="7c990-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li><p>The message is: message1</p></li>
    <li><p>The message is: message2</p></li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="7c990-323">Código subyacente</span><span class="sxs-lookup"><span data-stu-id="7c990-323">Code-behind</span></span>

<span data-ttu-id="7c990-324">BlazorNormalmente, un componente se crea en un solo archivo *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="7c990-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="7c990-325">Sin embargo, también es posible separar el código y el marcado mediante un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="7c990-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="7c990-326">Para usar un archivo de componente, agregue un archivo de C# que coincida con el nombre de archivo del archivo de componente, pero con una extensión *. CS* agregada (*Counter.Razor.CS*).</span><span class="sxs-lookup"><span data-stu-id="7c990-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="7c990-327">Use el archivo de C# para definir una clase base para el componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="7c990-328">Puede asignar a la clase base cualquier cosa que desee, pero es habitual asignar un nombre a la clase igual a la clase de componente, pero con una `Base` extensión agregada ( `CounterBase` ).</span><span class="sxs-lookup"><span data-stu-id="7c990-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="7c990-329">La clase basada en componente también debe derivarse de `ComponentBase` .</span><span class="sxs-lookup"><span data-stu-id="7c990-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="7c990-330">Después, en el archivo de componente de Razor, agregue la `@inherits` Directiva para especificar la clase base del componente ( `@inherits CounterBase` ).</span><span class="sxs-lookup"><span data-stu-id="7c990-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="7c990-331">*Counter. Razor*</span><span class="sxs-lookup"><span data-stu-id="7c990-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="7c990-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="7c990-332">*Counter.razor.cs*</span></span>

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

<span data-ttu-id="7c990-333">La visibilidad de los miembros del componente en la clase base debe estar `protected` o `public` ser visible para la clase de componente.</span><span class="sxs-lookup"><span data-stu-id="7c990-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c990-334">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7c990-334">Additional resources</span></span>

<span data-ttu-id="7c990-335">Lo anterior no es un tratamiento exhaustivo de todos los aspectos de los Blazor componentes.</span><span class="sxs-lookup"><span data-stu-id="7c990-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="7c990-336">Para obtener más información sobre cómo [crear y usar ASP.net Core componentes de Razor](/aspnet/core/blazor/components), consulte la Blazor documentación de.</span><span class="sxs-lookup"><span data-stu-id="7c990-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7c990-337">[Anterior](app-startup.md)
>[Siguiente](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="7c990-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
