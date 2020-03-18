---
title: 'Tutorial: Creación de una solución de .NET Core en macOS con Visual Studio Code'
description: En este documento se proporcionan los pasos y el flujo de trabajo para crear una solución de .NET Core con Visual Studio Code.
ms.date: 12/19/2019
ms.openlocfilehash: f5da16d413ddc25587ff35550fe9f308dc87f4bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156600"
---
# <a name="tutorial-create-a-net-core-solution-in-macos-using-visual-studio-code"></a>Tutorial: Creación de una solución de .NET Core en macOS con Visual Studio Code

En este documento se proporcionan los pasos y el flujo de trabajo para crear una solución de .NET Core para macOS. Obtendrá información sobre cómo crear proyectos, pruebas unitarias, usar las herramientas de depuración e incorporar bibliotecas de terceros a través de [NuGet](https://www.nuget.org/).

> [!NOTE]
> En este artículo se usa [Visual Studio Code](https://code.visualstudio.com) en macOS.

## <a name="prerequisites"></a>Requisitos previos

Instale el [SDK de .NET Core](https://dotnet.microsoft.com/download). El SDK de .NET Core incluye la última versión de la plataforma de .NET Core y el tiempo de ejecución.

Instale [Visual Studio Code](https://code.visualstudio.com). Durante el transcurso de este artículo, también instalará las extensiones de Visual Studio Code que mejoran la experiencia de desarrollo de .NET Core.

Instale la extensión de C# de Visual Studio Code; para ello, abra Visual Studio Code y presione <kbd>Fn</kbd>+<kbd>F1</kbd> para abrir la paleta de Visual Studio Code. Escriba **ext install** para ver la lista de extensiones. Seleccione la extensión de C#. Reinicie Visual Studio Code para activar la extensión. Para obtener más información, vea la [documentación de la extensión de C# enVisual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="get-started"></a>Primeros pasos

En este tutorial, creará tres proyectos: un proyecto de biblioteca, pruebas para ese proyecto de biblioteca y una aplicación de consola que usa la biblioteca. Puede [ver o descargar el origen](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) de este artículo en el repositorio dotnet/samples de GitHub. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Inicie Visual Studio Code. Presione <kbd>Ctrl</kbd><kbd>\`</kbd> (carácter de comilla inversa o tilde aguda) o seleccione **Ver** > **Terminal** en el menú para abrir un terminal insertado en Visual Studio Code. Puede abrir un shell externo con el comando **Abrir en símbolo del sistema** del explorador (**Abrir en terminal** en macOS o Linux) si prefiere trabajar fuera de Visual Studio Code.

Comience creando un archivo de solución, que actúa como un contenedor para uno o más proyectos de .NET Core. En el terminal, ejecute el comando [`dotnet new`](../tools/dotnet-new.md) para crear una solución *golden.sln* dentro de una nueva carpeta denominada *golden*:

```dotnetcli
dotnet new sln -o golden
```

Navegue a la nueva carpeta *golden* y ejecute el siguiente comando para crear un proyecto de biblioteca, que produce dos archivos,*library.csproj* y *Class1.cs*, en la carpeta *library*:

```dotnetcli
dotnet new classlib -o library
```

Ejecute el comando [`dotnet sln`](../tools/dotnet-sln.md) para agregar el proyecto *library.csproj* recién creado a la solución:

```dotnetcli
dotnet sln add library/library.csproj
```

El archivo *library.csproj* contiene la información siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Nuestros métodos de biblioteca serializan y deserializan objetos en formato JSON. Para admitir la serialización y deserialización JSON, agregue una referencia al paquete NuGet `Newtonsoft.Json`. El comando `dotnet add` agrega elementos nuevos a un proyecto. Para agregar una referencia a un paquete NuGet, use el comando [`dotnet add package`](../tools/dotnet-add-package.md) y especifique el nombre del paquete:

```dotnetcli
dotnet add library package Newtonsoft.Json
```

Esto agrega `Newtonsoft.Json` y sus dependencias al proyecto de biblioteca. De manera alternativa, edite manualmente el archivo *library.csproj* y agregue el nodo siguiente:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

Ejecute [`dotnet restore`](../tools/dotnet-restore.md) ([vea la nota](#dotnet-restore-note)), lo que restaura las dependencias y crea una carpeta *obj* dentro de *library* con tres archivos, incluido un archivo *project.assets.json*:

```dotnetcli
dotnet restore
```

En la carpeta *library*, cambie el nombre del archivo *Class1.cs* a *Thing.cs*. Reemplace el código por el siguiente:

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

La clase `Thing` contiene un método público, `Get`, que devuelve la suma de dos números pero lo hace convirtiendo la suma en una cadena y, después, deserializándola en un entero. Esto usa varias características de C# recientes, como las  [directivas `using static`](../../csharp/language-reference/keywords/using-static.md), los [miembros con forma de expresión](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) y la [interpolación de cadenas](../../csharp/language-reference/tokens/interpolated.md).

Compile la biblioteca con el comando [`dotnet build`](../tools/dotnet-build.md). Esto crea un archivo *library.dll* en *golden/library/bin/Debug/netstandard1.4*:

```dotnetcli
dotnet build
```

## <a name="create-the-test-project"></a>Crear el proyecto de prueba

Cree un proyecto de prueba para la biblioteca. Desde la carpeta *golden*, cree un nuevo proyecto de prueba:

```dotnetcli
dotnet new xunit -o test-library
```

Agregue el proyecto de prueba a la solución:

```dotnetcli
dotnet sln add test-library/test-library.csproj
```

Agregue una referencia del proyecto a la biblioteca que ha creado en la sección anterior, de manera que el compilador pueda buscar y usar el proyecto de biblioteca. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add test-library/test-library.csproj reference library/library.csproj
```

De manera alternativa, edite manualmente el archivo *test-library.csproj* y agregue el nodo siguiente:

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

Ahora que se han configurado correctamente las dependencias, cree las pruebas para la biblioteca. Abra *UnitTest1.cs* y reemplace el contenido por el código siguiente:

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing()
        {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

Tenga en cuenta que afirma que el valor 42 no es igual a 19+23 (o 42) cuando se crea la prueba unitaria por primera vez (`Assert.NotEqual`), lo que producirá un error. Un paso importante en la creación de las pruebas unitarias es crear la prueba para que produzca un error la primera vez para confirmar su lógica.

Desde la carpeta *golden*, ejecute los comandos siguientes:

```dotnetcli
dotnet restore
dotnet test test-library/test-library.csproj
```

Estos comandos buscarán de manera recursiva todos los proyectos para restaurar dependencias, compilarlos y activar el ejecutor de pruebas xUnit para ejecutar las pruebas. Se produce un error en la prueba, como se esperaba.

Edite el archivo *UnitTest1.cs* y cambie la aserción de `Assert.NotEqual` a `Assert.Equal`. Ejecute el comando siguiente desde la carpeta *golden* para volver a ejecutar la prueba, que se pasa esta vez:

```dotnetcli
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a>Crear la aplicación de consola

La aplicación de consola que crea con los pasos siguientes toma una dependencia del proyecto de biblioteca que ha creado anteriormente y llama a su método de biblioteca cuando se ejecuta. Con este patrón de desarrollo, ve cómo crear bibliotecas reutilizables en varios proyectos.

Cree una aplicación de consola nueva desde la carpeta *golden*:

```dotnetcli
dotnet new console -o app
```

Agregue el proyecto de la aplicación de consola a la solución:

```dotnetcli
dotnet sln add app/app.csproj
```

Cree la dependencia en la biblioteca ejecutando el comando `dotnet add reference`:

```dotnetcli
dotnet add app/app.csproj reference library/library.csproj
```

Ejecute `dotnet restore` ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias de los tres proyectos en la solución. Abra *Program.cs* y reemplace el contenido del método `Main` por la siguiente línea:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

Agregue dos directivas `using` en la parte superior del archivo *Program.cs*:

```csharp
using static System.Console;
using Library;
```

Ejecute el siguiente comando `dotnet run` para ejecutar el ejecutable, donde la opción `-p` en `dotnet run` especifica el proyecto para la aplicación principal. La aplicación genera la cadena "La respuesta es 42".

```dotnetcli
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a>Depurar la aplicación

Establezca un punto de interrupción en la instrucción `WriteLine` del método `Main`. Haga esto presionando la tecla <kbd>Fn</kbd>+<kbd>F9</kbd> cuando el cursor se encuentre encima de la línea `WriteLine` o haciendo clic con el mouse en el margen izquierdo de la línea donde quiera establecer el punto de interrupción. Aparecerá un círculo rojo en el margen junto a la línea de código. Cuando se alcance el punto de interrupción, la ejecución de código se detendrá *antes* de que se ejecute la línea del punto de interrupción.

Abra la pestaña del depurador; para ello, seleccione el icono Depurar en la barra de herramientas de Visual Studio Code, seleccione **Ver** > **Depurar** en la barra de menús o use el método abreviado de teclado <kbd>&#8679;</kbd><kbd>&#8984;</kbd><kbd>D</kbd>:

![Depurador de Visual Studio Code](./media/using-on-macos/visual-studio-code-debugger.png)

Presione el botón Reproducir para iniciar la aplicación en el depurador. En este proyecto ha creado un proyecto de prueba y una aplicación. El depurador pregunta qué proyecto desea iniciar. Seleccione el proyecto "aplicación". La aplicación comienza la ejecución y se ejecuta hasta el punto de interrupción, donde se detiene. Recorra paso a paso el método `Get` y asegúrese de que hayan pasado los argumentos correctos. Confirme que la respuesta es 42.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
