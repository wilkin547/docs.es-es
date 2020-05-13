---
title: Cree componentes de interfaz de usuario reutilizables con un increíble
description: Aprenda a crear componentes de interfaz de usuario reutilizables con más increíble y cómo se comparan con los controles de formularios Web Forms de ASP.NET.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 1a5f6b63143c4fd7a276219b9c4877e9e355c996
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378320"
---
# <a name="build-reusable-ui-components-with-blazor"></a>Cree componentes de interfaz de usuario reutilizables con un increíble

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Una de las cosas atractivas sobre los formularios Web Forms de ASP.NET es cómo permite la encapsulación de partes reutilizables del código de la interfaz de usuario (IU) en controles de interfaz de usuario reutilizables. Los controles de usuario personalizados se pueden definir en el marcado mediante archivos *. ascx* . También puede crear controles de servidor elaborados en el código con compatibilidad completa con el diseñador.

Increíbles también admite la encapsulación de la interfaz de usuario a través de *componentes*. Un componente:

- Es un fragmento independiente de la interfaz de usuario.
- Mantiene su propia lógica de representación y estado.
- Puede definir controladores de eventos de la interfaz de usuario, enlazar a datos de entrada y administrar su propio ciclo de vida.
- Normalmente se define en un archivo *. Razor* mediante sintaxis Razor.

## <a name="an-introduction-to-razor"></a>Introducción a Razor

Razor es un lenguaje de plantillas de marcado ligero basado en HTML y C#. Con Razor, puede realizar una transición sin problemas entre código de marcado y C# para definir la lógica de representación de componentes. Cuando se compila el archivo *. Razor* , la lógica de representación se captura de forma estructurada en una clase .net. El nombre de la clase compilada se toma del nombre de archivo *. Razor* . El espacio de nombres se toma del espacio de nombres predeterminado para el proyecto y la ruta de acceso de la carpeta, o bien se puede especificar explícitamente el espacio de nombres mediante la `@namespace` Directiva (más información sobre las directivas de Razor a continuación).

La lógica de representación de un componente se crea mediante el marcado HTML normal con lógica dinámica agregada mediante C#. El `@` carácter se usa para realizar la transición a C#. Razor suele ser una forma inteligente de averiguar cuándo ha cambiado a HTML. Por ejemplo, el siguiente componente representa una `<p>` etiqueta con la hora actual:

```razor
<p>@DateTime.Now</p>
```

Para especificar explícitamente el principio y el final de una expresión de C#, use paréntesis:

```razor
<p>@(DateTime.Now)</p>
```

Razor también facilita el uso del flujo de control de C# en la lógica de representación. Por ejemplo, puede representar condicionalmente un código HTML similar al siguiente:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

O bien, puede generar una lista de elementos mediante un bucle normal de C# `foreach` como el siguiente:

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Las directivas de Razor, como las directivas de formularios Web Forms de ASP.NET, controlan muchos aspectos de cómo se compila un componente de Razor. Algunos ejemplos son:

- Espacio de nombres
- Clase base
- Interfaces implementadas
- Parámetros genéricos
- Espacios de nombres importados
- Rutas

Las directivas de Razor comienzan con el `@` carácter y suelen usarse al principio de una nueva línea al principio del archivo. Por ejemplo, la `@namespace` Directiva define el espacio de nombres del componente:

```razor
@namespace MyComponentNamespace
```

En la tabla siguiente se resumen las distintas directivas de Razor que se usan en increíble y sus equivalentes de formularios Web Forms ASP.NET, si existen.

|Directiva    |Descripción|Ejemplo|Equivalentes de formularios Web Forms|
|-------------|-----------|-------|--------------------|
|`@attribute` |Agrega un atributo de nivel de clase al componente.|`@attribute [Authorize]`|None|
|`@code`      |Agrega miembros de clase al componente.|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implementa la interfaz especificada.|`@implements IDisposable`|Uso de código subyacente|
|`@inherits`  |Hereda de la clase base especificada|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Inserta un servicio en el componente.|`@inject IJSRuntime JS`|None|
|`@layout`    |Especifica un componente de diseño para el componente|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Establece el espacio de nombres del componente.|`@namespace MyNamespace`|None|
|`@page`      |Especifica la ruta del componente.|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Especifica un parámetro de tipo genérico para el componente.|`@typeparam TItem`|Uso de código subyacente|
|`@using`     |Especifica un espacio de nombres que se va a incluir en el ámbito|`@using MyComponentNamespace`|Agregar espacio de nombres en *Web. config*|

Los componentes de Razor también hacen un uso intensivo de *los atributos de la Directiva* en los elementos para controlar diversos aspectos de cómo se compilan los componentes (control de eventos, enlace de datos, referencias de elementos & componentes, etc.). Todos los atributos de directiva siguen una sintaxis genérica común en la que los valores entre paréntesis son opcionales:

```razor
@directive(-suffix(:name))(="value")
```

En la tabla siguiente se resumen los distintos atributos de las directivas de Razor que se usan en extraordinarias.

|Atributo    |Descripción|Ejemplo|
|-------------|-----------|-------|
|`@attributes`|Representa un diccionario de atributos.|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Crea un enlace de datos bidireccional    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Agrega un controlador de eventos para el evento especificado.|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Especifica una clave que va a usar el algoritmo de comparación para conservar los elementos de una colección.|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Captura una referencia al componente o elemento HTML.|`<MyDialog @ref="myDialog" />`|

Los distintos atributos de directiva utilizados por el increíbles ( `@onclick` , `@bind` ,, etc `@ref` .) se describen en las secciones siguientes y en los capítulos posteriores.

Muchas de las sintaxis que se usan en los archivos *. aspx* y *. ascx* tienen sintaxis paralelas en Razor. A continuación se muestra una comparación sencilla de las sintaxis de los formularios Web Forms de ASP.NET y Razor.

|Característica                      |Formularios Web Forms           |Sintaxis               |Razor         |Sintaxis |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Directivas                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Bloques de código                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Expresiones<br>(Codificado en HTML)|`<%: %>`            |`<%:DateTime.Now %>` |Explícito`@`<br>Explícita`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Comentarios                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|Enlace de datos                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Para agregar miembros a la clase de componente Razor, use la `@code` Directiva. Esta técnica es similar a usar un `<script runat="server">...</script>` bloque en una página o control de usuario de formularios web forms ASP.net.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Dado que Razor se basa en C#, se debe compilar desde un proyecto de C# (*. csproj*). No se pueden compilar archivos *. Razor* desde un proyecto de Visual Basic (*. vbproj*). Todavía puede hacer referencia a proyectos de Visual Basic desde el proyecto más brillante. Lo contrario también es true.

Para obtener una referencia de sintaxis Razor completa, consulte [Sintaxis Razor Reference for ASP.net Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>Uso de componentes

Además del HTML normal, los componentes también pueden usar otros componentes como parte de su lógica de representación. La sintaxis para usar un componente en Razor es similar a utilizar un control de usuario en una aplicación de formularios Web Forms ASP.NET. Los componentes se especifican mediante una etiqueta de elemento que coincide con el nombre de tipo del componente. Por ejemplo, puede Agregar un `Counter` componente como este:

```razor
<Counter />
```

A diferencia de los formularios Web Forms de ASP.NET, los componentes de increíbles:

- No use un prefijo de elemento (por ejemplo, `asp:` ).
- No es necesario registrarse en la página o en el *archivo Web. config*.

Piense en los componentes de Razor como en los tipos de .NET, ya que eso es exactamente lo que son. Si se hace referencia al ensamblado que contiene el componente, el componente está disponible para su uso. Para poner el espacio de nombres del componente en el ámbito, aplique la `@using` Directiva:

```razor
@using MyComponentLib

<Counter />
```

Como se ve en los proyectos increíblemente predeterminados, es habitual colocar `@using` directivas en un archivo *_Imports. Razor* para que se importen en todos los archivos *. Razor* en el mismo directorio y en los directorios secundarios.

Si el espacio de nombres de un componente no está en el ámbito, puede especificar un componente con su nombre de tipo completo, como puede hacerlo en C#:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Parámetros del componente

En los formularios Web Forms de ASP.NET, puede fluir los parámetros y los datos a los controles mediante propiedades públicas. Estas propiedades se pueden establecer en el marcado mediante atributos o establecerse directamente en el código. Los componentes increíbles funcionan de manera similar, aunque las propiedades del componente también se deben marcar con el `[Parameter]` atributo para que se consideren parámetros de componente.

El `Counter` componente siguiente define un parámetro de componente denominado `IncrementAmount` que se puede utilizar para especificar la cantidad que `Counter` se debe incrementar cada vez que se haga clic en el botón.

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

Para especificar un parámetro de componente en increíble, use un atributo tal como lo haría en los formularios Web Forms de ASP.NET:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>Controladores de eventos

Tanto los formularios Web Forms de ASP.NET como el increíbles proporcionan un modelo de programación basado en eventos para controlar los eventos de la interfaz de usuario. Entre los ejemplos de estos eventos se incluyen los clics de botón y la entrada de texto. En los formularios Web Forms de ASP.NET, se usan controles de servidor HTML para controlar los eventos de interfaz de usuario expuestos por el DOM, o se pueden controlar los eventos expuestos por los controles de servidor Web. Los eventos se muestran en el servidor a través de solicitudes de reenvío de formulario. Considere el siguiente ejemplo de clic de botón de formularios Web Forms:

*Counter. ascx*

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

En increíble, puede registrar Controladores para eventos de la interfaz de usuario DOM directamente mediante atributos de directiva del formulario `@on{event}` . El `{event}` marcador de posición representa el nombre del evento. Por ejemplo, puede realizar escuchas de clics de botón de la siguiente manera:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

Los controladores de eventos pueden aceptar un argumento opcional específico del evento para proporcionar más información sobre el evento. Por ejemplo, los eventos del mouse pueden tomar un `MouseEventArgs` argumento, pero no es necesario.

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

Los controladores de eventos se pueden ejecutar de forma sincrónica o asincrónica. Por ejemplo, el siguiente `OnClick` controlador de eventos se ejecuta de forma asincrónica:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

Una vez que se controla un evento, el componente se representa para tener en cuenta los cambios de estado de componente. Con los controladores de eventos asincrónicos, el componente se representa inmediatamente después de que se complete la ejecución del controlador. El componente se representará de *nuevo* después de que se complete la asincrónica `Task` . Este modo de ejecución asincrónica proporciona una oportunidad para representar una interfaz de usuario adecuada mientras la asincrónica `Task` todavía está en curso.

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

Los componentes también pueden definir sus propios eventos definiendo un parámetro de componente de tipo `EventCallback<TValue>` . Las devoluciones de llamada de evento admiten todas las variaciones de los controladores de eventos de la interfaz de usuario DOM: argumentos opcionales, sincrónicos o asincrónicos, grupos de métodos o expresiones lambda.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>Enlace de datos

Increíbles proporciona un mecanismo sencillo para enlazar datos de un componente de interfaz de usuario al estado del componente. Este enfoque difiere de las características de los formularios Web Forms de ASP.NET para enlazar datos de orígenes de datos a controles de interfaz de usuario. Trataremos el control de los datos de diferentes orígenes de datos en la sección tratamiento de los [datos](data.md) .

Para crear un enlace de datos bidireccional desde un componente de interfaz de usuario al estado del componente, use el `@bind` atributo de directiva. En el ejemplo siguiente, el valor de la casilla está enlazado al `isChecked` campo.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

Cuando se representa el componente, el valor de la casilla se establece en el valor del `isChecked` campo. Cuando el usuario activa la casilla, `onchange` se activa el evento y el `isChecked` campo se establece en el nuevo valor. `@bind`En este caso, la sintaxis es equivalente al marcado siguiente:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Para cambiar el evento utilizado para el enlace, utilice el `@bind:event` atributo.

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

Los componentes también pueden admitir el enlace de datos a sus parámetros. Para enlazar datos, defina un parámetro de devolución de llamada de evento con el mismo nombre que el parámetro enlazable. El sufijo "Changed" se agrega al nombre.

*PasswordBox. Razor*

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

Para encadenar un enlace de datos a un elemento de la interfaz de usuario subyacente, establezca el valor y controle el evento directamente en el elemento de la interfaz de usuario en lugar de usar el `@bind` atributo.

Para enlazar a un parámetro de componente, use un `@bind-{Parameter}` atributo para especificar el parámetro al que desea enlazar.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Cambios de estado

Si el estado del componente ha cambiado fuera de un evento de interfaz de usuario o una devolución de llamada de evento normal, el componente debe indicar manualmente que se debe volver a representar. Para indicar que el estado de un componente ha cambiado, llame al `StateHasChanged` método en el componente.

En el ejemplo siguiente, un componente muestra un mensaje de un `AppState` servicio que puede ser actualizado por otras partes de la aplicación. El componente registra su `StateHasChanged` método con el `AppState.OnChange` evento para que se represente el componente cada vez que se actualice el mensaje.

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

## <a name="component-lifecycle"></a>Ciclo de vida de los componentes

El marco de trabajo de formularios Web Forms de ASP.NET tiene métodos de ciclo de vida bien definidos para módulos, páginas y controles. Por ejemplo, el control siguiente implementa controladores de eventos para los `Init` eventos de `Load` ciclo de `UnLoad` vida, y:

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Los componentes increíbles también tienen un ciclo de vida bien definido. El ciclo de vida de un componente se puede usar para inicializar el estado del componente e implementar comportamientos de componentes avanzados.

Todos los métodos del ciclo de vida de los componentes de la extraordinariamente tienen versiones sincrónicas y asincrónicas. La representación de componentes es sincrónica. No se puede ejecutar la lógica asincrónica como parte de la representación de componentes. Toda la lógica asincrónica debe ejecutarse como parte de un `async` método de ciclo de vida.

### <a name="oninitialized"></a>Inicializado

Los `OnInitialized` `OnInitializedAsync` métodos y se utilizan para inicializar el componente. Normalmente, un componente se inicializa una vez que se representa por primera vez. Una vez inicializado un componente, se puede representar varias veces antes de que se elimine. El `OnInitialized` método es similar al `Page_Load` evento en las páginas y controles de formularios Web Forms de ASP.net.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

`OnParametersSet` `OnParametersSetAsync` Se llama a los métodos y cuando un componente ha recibido parámetros de su elemento primario y el valor se asigna a propiedades. Estos métodos se ejecutan después de la inicialización del componente y *cada vez que se representa el componente*.

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

`OnAfterRender` `OnAfterRenderAsync` Se llama a los métodos y una vez que un componente ha terminado de representar. Las referencias de elementos y componentes se rellenan en este punto (más información sobre estos conceptos a continuación). En este momento se habilita la interactividad con el explorador. Las interacciones con el DOM y la ejecución de JavaScript pueden tener lugar de forma segura.

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

`OnAfterRender`no se llama a y `OnAfterRenderAsync` *al representarse en el servidor*.

El `firstRender` parámetro es `true` la primera vez que se representa el componente; de lo contrario, su valor es `false` .

### <a name="idisposable"></a>IDisposable

Los componentes increíbles pueden implementar `IDisposable` para desechar los recursos cuando el componente se quita de la interfaz de usuario. Un componente de Razor puede implementar mediante `IDispose` la `@implements` Directiva:

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

## <a name="capture-component-references"></a>Referencias de componentes de captura

En los formularios Web Forms de ASP.NET, es habitual manipular una instancia de control directamente en el código haciendo referencia a su identificador. En increíble, también es posible capturar y manipular una referencia a un componente, aunque es mucho menos frecuente.

Para capturar una referencia de componente en extraordinaria, use el `@ref` atributo de directiva. El valor del atributo debe coincidir con el nombre de un campo configurable con el mismo tipo que el componente al que se hace referencia.

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

Cuando se representa el componente primario, el campo se rellena con la instancia del componente secundario. Después, puede llamar a los métodos en la instancia del componente o manipular de otro modo.

No se recomienda manipular el estado del componente directamente mediante referencias de componentes. Al hacerlo, se impide que el componente se represente automáticamente en los momentos correctos.

## <a name="capture-element-references"></a>Referencias del elemento Capture

Los componentes increíbles pueden capturar referencias a un elemento. A diferencia de los controles de servidor HTML en formularios Web Forms de ASP.NET, no se puede manipular el DOM directamente mediante una referencia de elemento en increíble. La mayoría de las interacciones de DOM se manejan con el algoritmo de diferenciación DOM. Las referencias de elemento capturadas en Increíblementeers son opacas. Sin embargo, se utilizan para pasar una referencia de elemento específica en una llamada de interoperabilidad de JavaScript. Para obtener más información sobre la interoperabilidad de JavaScript, vea [ASP.net Core la interoperabilidad de JavaScript](/aspnet/core/blazor/javascript-interop)increíble.

## <a name="templated-components"></a>Componentes con plantilla

En los formularios Web Forms de ASP.NET, puede crear *controles con plantilla*. Los controles con plantilla permiten al desarrollador especificar una parte del código HTML que se usa para representar un control de contenedor. La mecánica de la creación de controles de servidor con plantilla es compleja, pero habilita escenarios eficaces para representar los datos de forma personalizable. Entre los ejemplos de controles con plantilla se incluyen `Repeater` y `DataList` .

Los componentes increíbles también se pueden incluir en la plantilla definiendo los parámetros de componente de tipo `RenderFragment` o `RenderFragment<T>` . `RenderFragment`Representa un fragmento de marcado de Razor que se puede representar mediante el componente. Un `RenderFragment<T>` es un fragmento de marcado de Razor que toma un parámetro que se puede especificar cuando se representa el fragmento de representación.

### <a name="child-content"></a>Contenido secundario

Los componentes increíbles pueden capturar su contenido secundario como `RenderFragment` y representar ese contenido como parte de la representación de componentes. Para capturar contenido secundario, defina un parámetro de componente de tipo `RenderFragment` y asígnele el nombre `ChildContent` .

*ChildContentComponent. Razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

Después, un componente primario puede proporcionar contenido secundario mediante sintaxis Razor normales.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>Parámetros de plantilla

Un componente increíblemente con plantilla también puede definir varios parámetros de componente de tipo `RenderFragment` o `RenderFragment<T>` . El parámetro de un `RenderFragment<T>` puede especificarse cuando se invoca. Para especificar un parámetro de tipo genérico para un componente, use la `@typeparam` Directiva Razor.

*SimpleListView. Razor*

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

Cuando se usa un componente con plantilla, los parámetros de plantilla se pueden especificar utilizando los elementos secundarios que coinciden con los nombres de los parámetros. Los argumentos de componente de tipo `RenderFragment<T>` pasados como elementos tienen un parámetro implícito denominado `context` . Puede cambiar el nombre de este parámetro de implementación mediante el `Context` atributo en el elemento secundario. Los parámetros de tipo genérico se pueden especificar mediante un atributo que coincida con el nombre del parámetro de tipo. Si es posible, se infiere el parámetro de tipo:

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

La salida de este componente tiene el siguiente aspecto:

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>Código subyacente

Normalmente, un componente más rápido se crea en un solo archivo *. Razor* . Sin embargo, también es posible separar el código y el marcado mediante un archivo de código subyacente. Para usar un archivo de componente, agregue un archivo de C# que coincida con el nombre de archivo del archivo de componente, pero con una extensión *. CS* agregada (*Counter.Razor.CS*). Use el archivo de C# para definir una clase base para el componente. Puede asignar a la clase base cualquier cosa que desee, pero es habitual asignar un nombre a la clase igual a la clase de componente, pero con una `Base` extensión agregada ( `CounterBase` ). La clase basada en componente también debe derivarse de `ComponentBase` . Después, en el archivo de componente de Razor, agregue la `@inherits` Directiva para especificar la clase base del componente ( `@inherits CounterBase` ).

*Counter. Razor*

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

La visibilidad de los miembros del componente en la clase base debe estar `protected` o `public` ser visible para la clase de componente.

## <a name="additional-resources"></a>Recursos adicionales

Lo anterior no es un tratamiento exhaustivo de todos los aspectos de los componentes increíbles. Para obtener más información sobre cómo [crear y usar los componentes de Razor ASP.net Core](/aspnet/core/blazor/components), consulte la documentación de extraordinarias.

>[!div class="step-by-step"]
>[Anterior](app-startup.md)
>[Siguiente](pages-routing-layouts.md)
