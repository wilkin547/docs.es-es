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
# <a name="build-reusable-ui-components-with-blazor"></a>Cree componentes de interfaz de usuario reutilizables con Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Una de las cosas hermosas de ASP.NET formularios Web Forms es cómo permite la encapsulación de partes reutilizables de código de interfaz de usuario (UI) en controles de interfaz de usuario reutilizables. Los controles de usuario personalizados se pueden definir en el marcado mediante archivos *.ascx.* También puede crear controles de servidor elaborados en código con compatibilidad completa con el diseñador.

Blazor también admite la encapsulación de la interfaz de usuario a través de *componentes.* Un componente:

- Es un fragmento independiente de la interfaz de usuario.
- Mantiene su propio estado y lógica de representación.
- Puede definir controladores de eventos de interfaz de usuario, enlazar a datos de entrada y administrar su propio ciclo de vida.
- Normalmente se define en un archivo *.razor* mediante la sintaxis de Razor.

## <a name="an-introduction-to-razor"></a>Una introducción a Razor

Razor es un lenguaje de plantillas de marcado ligero basado en HTML y C. Con Razor, puede realizar una transición sin problemas entre el marcado y el código de C- para definir la lógica de representación de componentes. Cuando se compila el archivo *.razor,* la lógica de representación se captura de forma estructurada en una clase .NET. El nombre de la clase compilada se toma del nombre de archivo *.razor.* El espacio de nombres se toma del espacio de nombres predeterminado para el `@namespace` proyecto y la ruta de acceso de la carpeta, o puede especificar explícitamente el espacio de nombres mediante la directiva (más información sobre las directivas Razor a continuación).

La lógica de representación de un componente se crea mediante el marcado HTML normal con lógica dinámica agregada mediante C. El `@` carácter se utiliza para la transición a C. Razor suele ser inteligente para averiguar cuándo has vuelto a HTML. Por ejemplo, el siguiente `<p>` componente representa una etiqueta con la hora actual:

```razor
<p>@DateTime.Now</p>
```

Para especificar explícitamente el principio y el final de una expresión de C- , utilice paréntesis:

```razor
<p>@(DateTime.Now)</p>
```

Razor también facilita el uso del flujo de control de C- en la lógica de representación. Por ejemplo, puede representar condicionalmente algunos HTML como este:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

O bien, puede generar una lista `foreach` de elementos utilizando un bucle normal de C- como este:

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Las directivas de Razor, como las directivas de ASP.NET formularios Web Forms, controlan muchos aspectos de cómo se compila un componente Razor. Algunos ejemplos son los siguientes:

- Espacio de nombres
- Clase base
- Interfaces implementadas
- Parámetros genéricos
- Espacios de nombres importados
- Rutas

Las directivas de `@` Razor comienzan con el carácter y se usan normalmente al principio de una nueva línea al principio del archivo. Por ejemplo, `@namespace` la directiva define el espacio de nombres del componente:

```razor
@namespace MyComponentNamespace
```

En la tabla siguiente se resumen las diversas directivas Razor utilizadas en Blazor y sus equivalentes de formularios Web Forms ASP.NET, si existen.

|Directiva    |Descripción|Ejemplo|Formularios Web equivalentes|
|-------------|-----------|-------|--------------------|
|`@attribute` |Agrega un atributo de nivel de clase al componente|`@attribute [Authorize]`|None|
|`@code`      |Agrega miembros de clase al componente|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implementa la interfaz especificada|`@implements IDisposable`|Uso de código subyacente|
|`@inherits`  |Hereda de la clase base especificada|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Inyecta un servicio en el componente|`@inject IJSRuntime JS`|None|
|`@layout`    |Especifica un componente de diseño para el componente|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Establece el espacio de nombres para el componente|`@namespace MyNamespace`|None|
|`@page`      |Especifica la ruta del componente|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Especifica un parámetro de tipo genérico para el componente|`@typeparam TItem`|Uso de código subyacente|
|`@using`     |Especifica un espacio de nombres para incorporar al ámbito|`@using MyComponentNamespace`|Agregar espacio de nombres en *web.config*|

Los componentes de Razor también hacen un uso extensivo de *atributos* de directiva en los elementos para controlar varios aspectos de cómo se compilan los componentes (control de eventos, enlace de datos, referencias de elementos & componentes, etc.). Todos los atributos de directiva siguen una sintaxis genérica común en la que los valores entre paréntesis son opcionales:

```razor
@directive(-suffix(:name))(="value")
```

En la tabla siguiente se resumen los distintos atributos de las directivas Razor utilizadas en Blazor.

|Atributo    |Descripción|Ejemplo|
|-------------|-----------|-------|
|`@attributes`|Representa un diccionario de atributos|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Crea un enlace de datos bidireccional    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Agrega un controlador de eventos para el evento especificado|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Especifica una clave que utilizará el algoritmo de diferenciación para conservar los elementos de una colección|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Captura una referencia al componente o elemento HTML|`<MyDialog @ref="myDialog" />`|

Los distintos atributos de`@onclick`directiva `@bind` `@ref`utilizados por Blazor ( , , , , etc.) se tratan en las secciones siguientes y capítulos posteriores.

Muchas de las sintaxis utilizadas en archivos *.aspx* y *.ascx* tienen sintaxis paralelas en Razor. A continuación se muestra una comparación sencilla de las sintaxis de ASP.NET Web Forms y Razor.

|Característica                      |Formularios Web Forms           |Sintaxis               |Razor         |Sintaxis |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Directivas                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Bloques de código                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Expresiones<br>(codificado en HTML)|`<%: %>`            |`<%:DateTime.Now %>` |Implícita:`@`<br>Explícito:`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Comentarios                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|Enlace de datos                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Para agregar miembros a la `@code` clase de componente Razor, utilice la directiva. Esta técnica es similar `<script runat="server">...</script>` al uso de un bloque en una página o control de usuario de formularios Web Forms ASP.NET.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Debido a que Razor se basa en C- , debe compilarse desde dentro de un proyecto de C - (*.csproj*). No se pueden compilar archivos *.razor* desde un proyecto de Visual Basic (*.vbproj*). Todavía puede hacer referencia a proyectos de Visual Basic desde el proyecto Blazor. Lo contrario también es cierto.

Para obtener una referencia de sintaxis de Razor completa, consulte Referencia de [sintaxis](/aspnet/core/mvc/views/razor)de Razor para ASP.NET Core .

## <a name="use-components"></a>Uso de componentes

Aparte de HTML normal, los componentes también pueden utilizar otros componentes como parte de su lógica de representación. La sintaxis para usar un componente en Razor es similar al uso de un control de usuario en una aplicación de formularios Web Forms ASP.NET. Los componentes se especifican mediante una etiqueta de elemento que coincide con el nombre de tipo del componente. Por ejemplo, puede `Counter` agregar un componente como este:

```razor
<Counter />
```

A diferencia de ASP.NET formularios Web Forms, los componentes de Blazor:

- No utilice un prefijo de elemento `asp:`(por ejemplo, ).
- No es necesario registrarse en la página o en *el archivo web.config*.

Piense en los componentes de Razor como lo haría con los tipos .NET, porque eso es exactamente lo que son. Si se hace referencia al ensamblaje que contiene el componente, el componente está disponible para su uso. Para incorporar el espacio de nombres `@using` del componente en el ámbito, aplique la directiva:

```razor
@using MyComponentLib

<Counter />
```

Como se ve en los proyectos predeterminados de `@using` Blazor, es común poner directivas en un archivo *_Imports.razor* para que se importen en todos los archivos *.razor* en el mismo directorio y en directorios secundarios.

Si el espacio de nombres de un componente no está en el ámbito, puede especificar un componente con su nombre de tipo completo, como puede hacer en C-:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Parámetros del componente

En ASP.NET formularios Web Forms, puede fluir parámetros y datos a controles mediante propiedades públicas. Estas propiedades se pueden establecer en el marcado mediante atributos o establecer directamente en el código. Los componentes Blazor funcionan de forma similar, aunque `[Parameter]` las propiedades del componente también deben marcarse con el atributo que se debe considerar parámetros de componente.

El `Counter` componente siguiente define `IncrementAmount` un parámetro de componente denominado `Counter` que se puede utilizar para especificar la cantidad que se debe incrementar cada vez que se hace clic en el botón.

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

Para especificar un parámetro de componente en Blazor, utilice un atributo como lo haría en ASP.NET formularios Web Forms:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>Controladores de eventos

Tanto ASP.NET formularios Web Forms como Blazor proporcionan un modelo de programación basado en eventos para controlar eventos de interfaz de usuario. Algunos ejemplos de estos eventos son los clics de botón y la entrada de texto. En ASP.NET formularios Web Forms, se usan controles de servidor HTML para controlar los eventos de interfaz de usuario expuestos por el DOM, o puede controlar los eventos expuestos por los controles de servidor web. Los eventos se exponen en el servidor a través de solicitudes de devolución de formulario. Considere el siguiente botón de formularios Web Forms haga clic en ejemplo:

*Counter.ascx*

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

En Blazor, puede registrar controladores para eventos de interfaz de usuario DE DOM directamente mediante atributos de directiva del formulario. `@on{event}` El `{event}` marcador de posición representa el nombre del evento. Por ejemplo, puede escuchar clics de botón como este:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

Los controladores de eventos pueden aceptar un argumento opcional específico del evento para proporcionar más información sobre el evento. Por ejemplo, los eventos `MouseEventArgs` del mouse pueden tomar un argumento, pero no es necesario.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

En lugar de hacer referencia a un grupo de métodos para un controlador de eventos, puede usar una expresión lambda. Una expresión lambda permite cerrar otros valores en el ámbito.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

Los controladores de eventos se pueden ejecutar de forma sincrónica o asincrónica. Por ejemplo, `OnClick` el siguiente controlador de eventos se ejecuta de forma asincrónica:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

Después de controlar un evento, el componente se representa para tener en cuenta los cambios de estado del componente. Con los controladores de eventos asincrónicos, el componente se representa inmediatamente después de que se complete la ejecución del controlador. El componente se representa de `Task` nuevo una *vez* completada la asincrónica. Este modo de ejecución asincrónica proporciona una oportunidad `Task` para representar alguna interfaz de usuario adecuada mientras la asincrónica todavía está en curso.

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

Los componentes también pueden definir sus propios `EventCallback<TValue>`eventos definiendo un parámetro de componente de tipo . Las devoluciones de llamada de eventos admiten todas las variaciones de los controladores de eventos de la interfaz de usuario de DOM: argumentos opcionales, sincrónicos o asincrónicos, grupos de métodos o expresiones lambda.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>Enlace de datos

Blazor proporciona un mecanismo sencillo para enlazar datos de un componente de interfaz de usuario al estado del componente. Este enfoque difiere de las características de ASP.NET formularios Web Forms para enlazar datos de orígenes de datos a controles de interfaz de usuario. Trataremos el manejo de datos de diferentes fuentes de datos en la sección [Tratamiento de datos.](data.md)

Para crear un enlace de datos bidireccional desde un componente de `@bind` interfaz de usuario al estado del componente, utilice el atributo directive. En el ejemplo siguiente, el valor de `isChecked` la casilla de verificación está enlazado al campo.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

Cuando se representa el componente, el valor de la `isChecked` casilla de verificación se establece en el valor del campo. Cuando el usuario alterna la `onchange` casilla de `isChecked` verificación, se desencadena el evento y el campo se establece en el nuevo valor. La `@bind` sintaxis en este caso es equivalente al siguiente marcado:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Para cambiar el evento utilizado para `@bind:event` el enlace, utilice el atributo.

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

Los componentes también pueden admitir el enlace de datos a sus parámetros. Para enlazar datos, defina un parámetro de devolución de llamada de evento con el mismo nombre que el parámetro enlazable. El sufijo "Changed" se agrega al nombre.

*PasswordBox.razor*

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

Para encadenar un enlace de datos a un elemento de interfaz de usuario `@bind` subyacente, establezca el valor y controle el evento directamente en el elemento de interfaz de usuario en lugar de usar el atributo.

Para enlazar a un parámetro `@bind-{Parameter}` de componente, utilice un atributo para especificar el parámetro al que desea enlazar.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Cambios de estado

Si el estado del componente ha cambiado fuera de un evento de interfaz de usuario normal o devolución de llamada de eventos, el componente debe indicar manualmente que debe representarse de nuevo. Para indicar que el estado de un `StateHasChanged` componente ha cambiado, llame al método en el componente.

En el ejemplo siguiente, un componente `AppState` muestra un mensaje de un servicio que se puede actualizar por otras partes de la aplicación. El componente registra `StateHasChanged` su `AppState.OnChange` método con el evento para que el componente se represente cada vez que se actualiza el mensaje.

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

## <a name="component-lifecycle"></a>Ciclo de vida de los componentes

El marco de trabajo de formularios Web Forms ASP.NET tiene métodos de ciclo de vida bien definidos para módulos, páginas y controles. Por ejemplo, el siguiente control implementa `Init`controladores de eventos para los eventos , `Load`, y `UnLoad` lifecycle:

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Los componentes de Blazor también tienen un ciclo de vida bien definido. El ciclo de vida de un componente se puede utilizar para inicializar el estado del componente e implementar comportamientos avanzados de los componentes.

Todos los métodos de ciclo de vida de componentes de Blazor tienen versiones sincrónicas y asincrónicas. La representación de componentes es sincrónica. No se puede ejecutar la lógica asincrónica como parte de la representación de componentes. Toda la lógica asincrónica debe `async` ejecutarse como parte de un método de ciclo de vida.

### <a name="oninitialized"></a>OnInitialized

Los `OnInitialized` `OnInitializedAsync` métodos y se utilizan para inicializar el componente. Normalmente, un componente se inicializa después de que se representa por primera vez. Después de inicializar un componente, se puede representar varias veces antes de que finalmente se elimine. El `OnInitialized` método es `Page_Load` similar al evento en ASP.NET páginas y controles de formularios Web Forms.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

Los `OnParametersSet` `OnParametersSetAsync` métodos y se llaman cuando un componente ha recibido parámetros de su elemento primario y el valor se asigna a las propiedades. Estos métodos se ejecutan después de la inicialización del componente y *cada vez que se representa el componente.*

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

Los `OnAfterRender` `OnAfterRenderAsync` métodos y se llaman después de que un componente haya terminado de renderizar. Las referencias de elementos y componentes se rellenan en este punto (más información sobre estos conceptos a continuación). La interactividad con el navegador se habilita en este momento. Las interacciones con la ejecución de DOM y JavaScript pueden tener lugar de forma segura.

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

`OnAfterRender`y `OnAfterRenderAsync` *no se llaman al preprocesamiento en el servidor.*

El `firstRender` parámetro `true` es la primera vez que se representa el componente; de lo contrario, su valor es `false`.

### <a name="idisposable"></a>IDisposable

Los componentes de `IDisposable` Blazor se pueden implementar para eliminar recursos cuando el componente se quita de la interfaz de usuario. Un componente Razor `IDispose` se `@implements` puede implementar mediante la directiva:

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

## <a name="capture-component-references"></a>Capturar referencias de componentes

En ASP.NET formularios Web Forms, es común manipular una instancia de control directamente en el código haciendo referencia a su identificador. En Blazor, también es posible capturar y manipular una referencia a un componente, aunque es mucho menos común.

Para capturar una referencia de componente `@ref` en Blazor, utilice el atributo directive. El valor del atributo debe coincidir con el nombre de un campo configurable con el mismo tipo que el componente al que se hace referencia.

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

Cuando se representa el componente primario, el campo se rellena con la instancia del componente secundario. A continuación, puede llamar a métodos en la instancia del componente o manipularla de otro modo.

No se recomienda manipular el estado del componente directamente mediante referencias de componentes. Al hacerlo, se evita que el componente se represente automáticamente en los momentos correctos.

## <a name="capture-element-references"></a>Capturar referencias de elementos

Los componentes blazor pueden capturar referencias a un elemento. A diferencia de los controles de servidor HTML en ASP.NET formularios Web Forms, no se puede manipular el DOM directamente mediante una referencia de elemento en Blazor. Blazor maneja la mayoría de las interacciones DOM por usted usando su algoritmo de diferenciación DOM. Las referencias de elementos capturadas en Blazor son opacas. Sin embargo, se usan para pasar una referencia de elemento específica en una llamada de interoperabilidad de JavaScript. Para obtener más información acerca de la interoperabilidad de JavaScript, vea [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).

## <a name="templated-components"></a>Componentes con plantilla

En ASP.NET formularios Web Forms, puede crear *controles con plantilla.* Los controles con plantilla permiten al desarrollador especificar una parte del código HTML utilizado para representar un control contenedor. La mecánica de creación de controles de servidor con plantilla es compleja, pero permiten escenarios eficaces para representar datos de una manera personalizable por el usuario. Entre los ejemplos `Repeater` de `DataList`controles con plantilla se incluyen y .

Los componentes Blazor también se pueden plantillar definiendo parámetros de componente de tipo `RenderFragment` o `RenderFragment<T>`. A `RenderFragment` representa un fragmento de marcado Razor que el componente puede representar. A `RenderFragment<T>` es un fragmento de marcado de Razor que toma un parámetro que se puede especificar cuando se representa el fragmento de representación.

### <a name="child-content"></a>Contenido infantil

Los componentes de Blazor `RenderFragment` pueden capturar su contenido secundario como a y representar ese contenido como parte de la representación de componentes. Para capturar contenido secundario, defina `RenderFragment` un parámetro `ChildContent`de componente de tipo y asímócelo.

*ChildContentComponent.razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

A continuación, un componente primario puede proporcionar contenido secundario mediante la sintaxis normal de Razor.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>Parámetros de plantilla

Un componente Blazor con plantilla también puede `RenderFragment` `RenderFragment<T>`definir varios parámetros de componente de tipo o . El parámetro `RenderFragment<T>` para a se puede especificar cuando se invoca. Para especificar un parámetro de tipo `@typeparam` genérico para un componente, utilice la directiva Razor.

*SimpleListView.razor*

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

Cuando se utiliza un componente con plantilla, los parámetros de plantilla se pueden especificar mediante elementos secundarios que coinciden con los nombres de los parámetros. Los argumentos `RenderFragment<T>` de componente de tipo `context`pasados como elementos tienen un parámetro implícito denominado . Puede cambiar el nombre de este `Context` parámetro implement mediante el atributo del elemento secundario. Los parámetros de tipo genérico se pueden especificar mediante un atributo que coincida con el nombre del parámetro type. El parámetro type se deducirá si es posible:

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

La salida de este componente tiene este aspecto:

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>Código subyacente

Un componente Blazor se crea normalmente en un único archivo *.razor.* Sin embargo, también es posible separar el código y el marcado mediante un archivo de código subyacente. Para utilizar un archivo de componente, agregue un archivo de Cá que coincida con el nombre de archivo del archivo de componente pero con una extensión *.cs* agregada (*Counter.razor.cs*). Utilice el archivo de C- para definir una clase base para el componente. Puede asignar a la clase base el nombre que desee, pero es común asignar a `Base` la`CounterBase`clase el mismo nombre que la clase de componente, pero con una extensión agregada ( ). La clase basada en componentes también debe derivar de `ComponentBase`. A continuación, en el archivo `@inherits` de componente Razor, agregue`@inherits CounterBase`la directiva para especificar la clase base para el componente ( ).

*Counter.razor*

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

*Counter.razor.cs*

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

La visibilidad de los miembros del componente `protected` `public` en la clase base debe ser o para ser visible para la clase de componente.

## <a name="additional-resources"></a>Recursos adicionales

Lo anterior no es un tratamiento exhaustivo de todos los aspectos de los componentes de Blazor. Para obtener más información sobre cómo [crear y utilizar componentes de ASP.NET Core Razor,](/aspnet/core/blazor/components)consulte la documentación de Blazor.

>[!div class="step-by-step"]
>[Anterior](app-startup.md)
>[Siguiente](pages-routing-layouts.md)
