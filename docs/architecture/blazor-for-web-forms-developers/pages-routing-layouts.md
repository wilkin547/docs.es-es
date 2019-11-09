---
title: Páginas, enrutamiento y diseños
description: Obtenga información acerca de cómo crear páginas en extraordinarias, trabajar con el enrutamiento del lado cliente y administrar diseños de página.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: 693eee270a46ccb56ed5fef8fced1d4a1cf1974f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "73841238"
---
# <a name="pages-routing-and-layouts"></a>Páginas, enrutamiento y diseños

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Las aplicaciones de formularios Web Forms de ASP.NET se componen de páginas definidas en archivos *. aspx* . La dirección de cada página se basa en su ruta de acceso física del archivo en el proyecto. Cuando un explorador realiza una solicitud a la página, el contenido de la página se representa dinámicamente en el servidor. Las cuentas de representación para el marcado HTML de la página y sus controles de servidor.

En increíble, cada página de la aplicación es un componente, que normalmente se define en un archivo *. Razor* , con una o varias rutas especificadas. El enrutamiento se produce principalmente en el lado cliente sin implicar una solicitud de servidor específica. En primer lugar, el explorador realiza una solicitud a la dirección raíz de la aplicación. Un componente de `Router` raíz de la aplicación extraordinariamente controla las solicitudes de navegación de interceptación y el componente correcto.

El increíble también admite la *vinculación profunda*. La vinculación profunda se produce cuando el explorador realiza una solicitud a una ruta específica distinta de la raíz de la aplicación. Las solicitudes de vínculos profundos que se envían al servidor se enrutan a la aplicación extraordinaria, que luego enruta el lado cliente de la solicitud al componente correcto.

Una página simple de formularios Web Forms de ASP.NET podría contener el marcado siguiente:

*Nombre. aspx*

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

*Name.aspx.cs*

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

La página equivalente en una aplicación extraordinaria sería similar a la siguiente:

*Nombre. Razor*

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a>Crear páginas

Para crear una página en increíble, cree un componente y agregue la Directiva de Razor `@page` para especificar la ruta del componente. La Directiva `@page` toma un único parámetro, que es la plantilla de ruta que se va a agregar a ese componente.

```razor
@page "/counter"
```

El parámetro de la plantilla de ruta es obligatorio. A diferencia de los formularios Web Forms de ASP.NET, la ruta a un componente increíblemente *no se* deduce de su ubicación de archivo (aunque puede ser una característica agregada en el futuro).

La sintaxis de la plantilla de ruta es la misma sintaxis básica que se usa para el enrutamiento en ASP.NET Web Forms. Los parámetros de ruta se especifican en la plantilla mediante llaves. Más increíble enlazará los valores de ruta a los parámetros de componente con el mismo nombre (sin distinción de mayúsculas y minúsculas).

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

También puede especificar restricciones en el valor del parámetro Route. Por ejemplo, para restringir el identificador de producto a un `int`:

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

Para obtener una lista completa de las restricciones de ruta admitidas por el increíbles, consulte [restricciones de ruta](/aspnet/core/blazor/routing#route-constraints).

## <a name="router-component"></a>Componente de enrutador

El componente `Router` controla el enrutamiento en increíble. El componente de `Router` se usa normalmente en el componente raíz de la aplicación (*app. Razor*).

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

El componente `Router` detecta los componentes enrutables en el `AppAssembly` especificado y en la `AdditionalAssemblies`especificada opcionalmente. Cuando el explorador navega, el `Router` intercepta la navegación y representa el contenido de su parámetro `Found` con el `RouteData` extraído si una ruta coincide con la dirección; de lo contrario, el `Router` representa su parámetro `NotFound`.

El componente `RouteView` controla la representación del componente coincidente especificado por el `RouteData` con su diseño si tiene uno. Si el componente coincidente no tiene un diseño, se utiliza el `DefaultLayout` opcionalmente especificado.

El componente `LayoutView` representa su contenido secundario dentro del diseño especificado. Veremos los diseños más detalladamente más adelante en este capítulo.

## <a name="navigation"></a>Navegación

En los formularios Web Forms de ASP.NET, se desencadena la navegación a una página diferente devolviendo una respuesta de redirección al explorador. Por ejemplo:

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

Normalmente, no es posible devolver una respuesta de redirección en increíble. El increíbles no usa un modelo de solicitud-respuesta. Sin embargo, puede desencadenar directamente las navegaciones del explorador, como se puede hacer con JavaScript.

Increíble proporciona un servicio `NavigationManager` que se puede usar para:

- Obtener la dirección del explorador actual
- Obtención de la dirección base
- Navegación de desencadenador
- Recibir una notificación cuando cambie la dirección

Para navegar a una dirección diferente, utilice el método `NavigateTo`:

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

Para obtener una descripción de todos los miembros de `NavigationManager`, vea [aplicaciones auxiliares de URI y de estado de navegación](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).

## <a name="base-urls"></a>Direcciones URL base

Si la aplicación increíblemente se implementa en una ruta de acceso base, debe especificar la dirección URL base en los metadatos de la página con la etiqueta `<base>` para la propiedad enrutamiento a trabajo. Si la página host de la aplicación se representa en el servidor mediante Razor, puede usar la sintaxis de `~/` para especificar la dirección base de la aplicación. Si la página host es HTML estático, debe especificar explícitamente la dirección URL base.

```html
<base href="~/" />
```

## <a name="page-layout"></a>Diseño de página

El diseño de página en formularios Web Forms de ASP.NET se controla mediante páginas maestras. Las páginas maestras definen una plantilla con uno o varios marcadores de posición de contenido que las páginas individuales pueden proporcionar. Las páginas maestras se definen en los archivos *. Master* y comienzan con la Directiva `<%@ Master %>`. El contenido de los archivos *. Master* se codifica como lo haría con una página *. aspx* , pero con la adición de controles `<asp:ContentPlaceHolder>` para marcar dónde pueden proporcionar contenido las páginas.

*Site. Master*

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

En increíble, se controla el diseño de página mediante componentes de diseño. Los componentes de diseño heredan de `LayoutComponentBase`, que define una única propiedad `Body` de tipo `RenderFragment`, que se puede utilizar para representar el contenido de la página.

*MainLayout. Razor*

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

Cuando se representa la página con un diseño, la página se representa en el contenido del diseño especificado en la ubicación en la que el diseño representa su `Body` propiedad.

Para aplicar un diseño a una página, use la Directiva `@layout`:

```razor
@layout MainLayout
```

Puede especificar el diseño de todos los componentes de una carpeta y subcarpetas mediante un archivo *_Imports. Razor* . También puede especificar un diseño predeterminado para todas las páginas mediante el [componente del enrutador](#router-component).

Las páginas maestras pueden definir varios marcadores de posición de contenido, pero los diseños de increíble solo tienen una única propiedad de `Body`. Esta limitación de los componentes de diseño de Extraordinariaidad se solucionará en una futura versión.

Las páginas maestras en formularios Web Forms de ASP.NET se pueden anidar. Es decir, una página maestra también puede usar una página maestra. Los componentes de diseño de increíbles también pueden estar anidados. Puede aplicar un componente de diseño a un componente de diseño. El contenido del diseño interno se representará dentro del diseño exterior.

*ChildLayout. Razor*

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

*Index. Razor*

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

La salida representada de la página sería:

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

Normalmente, los diseños de más increíblemente no definen los elementos HTML raíz de una página (`<html>`, `<body>`, `<head>`, etc.). En su lugar, los elementos HTML raíz se definen en la página del host de una aplicación, que se usa para representar el contenido HTML inicial de la aplicación (consulte [bootstrap](project-structure.md#bootstrap-blazor)). La página host puede representar varios componentes raíz para la aplicación con el marcado circundante.

Los componentes de extraordinarias, incluidas las páginas, no pueden representar etiquetas `<script>`. Esta restricción de representación existe porque `<script>` etiquetas se cargan una vez y, después, no se pueden cambiar. Puede producirse un comportamiento inesperado si intenta representar las etiquetas dinámicamente mediante sintaxis Razor. En su lugar, se deben agregar todas las etiquetas de `<script>` a la página host de la aplicación.

>[!div class="step-by-step"]
>[Anterior](components.md)
>[Siguiente](state-management.md)
