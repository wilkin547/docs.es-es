---
title: "Introducción a .NET Core en macOS"
description: "Introducción a .NET Core en macOS con Visual Studio Code"
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 02/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: c4d1b7690ca87f2a1a9ced4d82e47aee2f7ecc9f
ms.lasthandoff: 03/07/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-code"></a>Introducción a .NET Core en macOS con Visual Studio Code

En este documento se proporciona una descripción de los pasos y del flujo de trabajo para crear una solución de .NET Core con [Visual Studio Code](http://code.visualstudio.com).
Aprenderá a crear proyectos, crear pruebas unitarias, utilizar las herramientas de depuración e incorporar bibliotecas de terceros a través de [NuGet](http://nuget.org).

En este artículo se usa Visual Studio Code en Mac OS. Cuando haya diferencias, se destacan las correspondientes a la plataforma Windows.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, necesitará instalar el [SDK de .NET Core](https://www.microsoft.com/net/core). El SDK de .NET Core incluye la última versión de la plataforma de .NET Core y el tiempo de ejecución.

También debe instalar [Visual Studio Code](http://code.visualstudio.com).
Durante el transcurso de este artículo, también deberá instalar las extensiones que mejorarán la experiencia de desarrollo de .NET Core.

## <a name="getting-started"></a>Introducción

El código fuente de este tutorial está disponible en [GitHub](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden).

Inicie Visual Studio Code. Presione Ctrl + '\`' (el carácter de comilla invertida) para abrir un terminal incrustado en VS Code. (Como alternativa, puede utilizar una ventana de terminal independiente, si lo prefiere).

Cuando haya terminado, podrá crear tres proyectos: un proyecto de biblioteca, pruebas para ese proyecto de biblioteca y una aplicación de consola que utiliza la biblioteca. 

Comencemos por crear las carpetas. En el terminal, cree un directorio "golden". En VS Code, abra el directorio *golden*. Este directorio es la raíz de la solución. Ejecute el comando [`dotnet new`](../tools/dotnet-new.md) para crear una nueva solución:

```
dotnet new sln
```

Este comando crea un archivo *golden.sln* para la solución completa.

La siguiente tarea consiste en crear la biblioteca. En la ventana de terminal (tanto el terminal incrustado en VS Code como cualquier otro terminal), cambie a *golden/* y escriba el comando:

```
dotnet new classlib -o library
```

Esto crea un proyecto de biblioteca, con dos archivos: *library.csproj* y *Class1.cs* en el directorio *library*. Quiere ese proyecto de biblioteca incluido en la solución. Ejecute el comando [`dotnet sln`](../tools/dotnet-sln.md) para agregar el proyecto *library.csproj* recién creado a la solución:

```
dotnet sln add library/library.csproj
```

Vamos a examinar el proyecto que ha creado. El archivo *library.csproj* contiene la información siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

Este proyecto de biblioteca utilizará la representación de objetos de JSON, por lo que deberá agregar una referencia al paquete NuGet `Newtonsoft.Json`. El comando `dotnet add` agrega elementos nuevos a un proyecto. Para agregar una referencia a un paquete NuGet, use el comando `package` y especifique el nombre del paquete. 

```
dotnet add library package Newtonsoft.Json
```

Esto agrega `Newtonsoft.Json` y sus dependencias al proyecto de biblioteca. De manera alternativa, puede editar manualmente el archivo *library.csproj* y agregar el nodo siguiente:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
  </PackageReference>
</ItemGroup>
```

Una vez haya terminado de agregar esas dependencias, debe instalar esos paquetes en el área de trabajo. Ejecute el comando `dotnet restore` para actualizar todas las dependencias y escriba un archivo *obj/project.assets.json* en el directorio del proyecto. Este archivo contiene el árbol de dependencias completo de todas las dependencias del proyecto. No es necesario que lea este archivo, se utiliza con herramientas del SDK de .NET Core.

Ahora, vamos a actualizar el código de C#. Vamos a crear una clase `Thing` que contiene un método público. Este método devuelve la suma de dos números, pero para ello, convierte ese número en una cadena JSON y, después, lo deserializa. Cambie el nombre del archivo *Class1.cs* a *Thing.cs*. A continuación, reemplace el código existente (para la Class1 generada por plantilla) por lo siguiente:

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

Esto usa varias características de C# recientes como los usos estáticos, los miembros con cuerpo de expresión y las cadenas interpoladas, de las que puede obtener información en la sección [Aprender C#](../../csharp/index.md).

Ahora que ha actualizado el código, puede generar la biblioteca con `dotnet build`.

Ahora tiene un archivo *library.dll* compilado en *golden/library/bin/Debug/netstandard1.4*.

### <a name="writing-the-test-project"></a>Escritura del proyecto de prueba

Vamos a crear un proyecto de prueba para esta biblioteca que ha creado. Cambie al directorio *golden*. Ejecute `dotnet new xunit -o test-library` para crear un proyecto de prueba. Querrá agregar este proyecto a la solución también mediante la ejecución de `dotnet sln add test-library/test-library.csproj`.

Necesitará agregar un nodo de dependencia para la biblioteca que escribió en los pasos anteriores. El comando `dotnet add reference` hace eso:

```
dotnet add test-library/test-library.csproj reference library/library.csproj
```

O puede editar manualmente el archivo *test-library.csproj* y agregar el nodo siguiente:

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

El nodo `library` especifica que se debe resolver esta dependencia en un proyecto en el área de trabajo actual. Sin especificar explícitamente esto, es posible que el proyecto de prueba se cree en un paquete NuGet del mismo nombre.

Ahora que se han configurado correctamente las dependencias, vamos a crear las pruebas para la biblioteca. Abra *UnitTest1.cs* y reemplace el contenido por el código siguiente:

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.Equal(42, new Thing().Get(19, 23));
        }
    }
}
```

Ahora, ejecute `dotnet restore` y `dotnet build`. Estos comandos buscarán de manera recursiva todos los proyectos para restaurar las dependencias y compilarlas.
Por último, ejecute `dotnet test test-library/test-library.csproj` para ejecutar las pruebas.
El ejecutor de pruebas de la consola xUnit ejecutará una prueba e informará de ello. 

### <a name="writing-the-console-app"></a>Escritura de la aplicación de consola

En su terminal, ejecute `dotnet new console -o app` para crear una aplicación de consola nueva. Este proyecto también forma parte de la solución, así que ejecute `dotnet sln add app/app.csproj` para agregar el proyecto a la solución.

La aplicación de consola depende de la biblioteca que creó y comprobó en los pasos anteriores. Necesita indicarlo ejecutando `dotnet add reference` de nuevo:

```
dotnet add app/app.csproj reference library/library.csproj
```

Ejecute `dotnet restore` para restaurar todas las dependencias. Abra *program.cs* y reemplace el contenido del método `Main` por esta línea:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

Necesitará agregar un par de directivas `using` en la parte superior del archivo:

```csharp
using static System.Console;
using Library;
```

Después, ejecute `dotnet build`. Con ello creará los ensamblados y puede escribir `dotnet run -p app/app.csproj` para ejecutar el archivo ejecutable.
El argumento `-p` para `dotnet run` especifica el proyecto para la aplicación principal.

### <a name="debugging-your-application"></a>Depuración de la aplicación

Puede depurar el código en VS Code mediante la extensión de C#.
Instale esta extensión presionando `F1` para abrir la paleta de VS Code. Escriba `ext install` para ver la lista de extensiones. Seleccione la extensión de C#. (Hay más detalles disponibles en la página de [documentación de la extensión C# de Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)).

Después de instalar la extensión, VS Code le pedirá que reinicie la aplicación para cargar la nueva extensión. Una vez instalada la extensión, puede abrir la pestaña del depurador (consulte la figura).

![Depurador de VS Code](./media/using-on-macos/vscodedebugger.png)

Establezca un punto de interrupción en la instrucción `WriteLine` de `Main`. Para ello, presione la tecla `F9` o haga clic con el mouse en el margen izquierdo en la línea en la que desee el punto de interrupción. Abra el depurador presionando el icono de depuración situado a la izquierda de la pantalla de VS Code (véase la figura). A continuación, presione el botón Reproducir para iniciar la aplicación en el depurador.

Debe alcanzar el punto de interrupción. Recorra paso a paso el método `Get` y asegúrese de que hayan pasado los argumentos correctos. Asegúrese de que la respuesta es realmente 42.

