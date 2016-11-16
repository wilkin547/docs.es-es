---
title: "Introducción a .NET Core en macOS"
description: "Introducción a .NET Core en macOS con Visual Studio Code"
keywords: .NET, .NET Core
author: bleroy
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
translationtype: Human Translation
ms.sourcegitcommit: 2339be6aef7e2ff942f1f1999a12f48ee4a77ee8
ms.openlocfilehash: 12b7bed380db53aad04f0615c6efa6152b3035b7

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-code"></a>Introducción a .NET Core en macOS con Visual Studio Code

por [Bertrand Le Roy](https://github.com/bleroy),  [Phillip Carter](https://github.com/cartermp), [Bill Wagner](https://github.com/billwagner)

Contribuciones de [Toni Solarin-Sodara](https://github.com/tsolarin)

En este documento se proporciona una descripción de los pasos y del flujo de trabajo para crear una solución de .NET Core con [Visual Studio Code](http://code.visualstudio.com).
Aprenderá a crear proyectos, crear pruebas unitarias, utilizar las herramientas de depuración e incorporar bibliotecas de terceros a través de [NuGet](http://nuget.org).

En este artículo se usa Visual Studio Code en Mac OS. Cuando haya diferencias, se destacan las correspondientes a la plataforma Windows.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, debe instalar el [SDK de .NET Core](https://www.microsoft.com/net/core), actualmente en versión preliminar. El SDK de .NET Core incluye la última versión de la plataforma de .NET Core y el tiempo de ejecución.

También debe instalar [Visual Studio Code](http://code.visualstudio.com).
Durante el transcurso de este artículo, también deberá instalar las extensiones que mejorarán la experiencia de desarrollo de .NET Core.

Puede encontrar los vínculos a todos estos elementos en la [página principal de .NET](http://dot.net).

## <a name="getting-started"></a>Introducción

El código fuente de este tutorial está disponible en [GitHub](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden).

Inicie Visual Studio Code. Presione Ctrl + '\`' (el carácter de comilla invertida) para abrir un terminal incrustado en VS Code. (Como alternativa, puede utilizar una ventana de terminal independiente, si lo prefiere).

Cuando haya terminado, podrá crear tres proyectos: un proyecto de biblioteca, pruebas para ese proyecto de biblioteca y una aplicación de consola que utiliza la biblioteca. Se va a seguir una estructura de carpetas estándar para los tres proyectos. La estructura de esta carpeta estándar significa que las herramientas del SDK de .NET Core comprenden la relación entre los proyectos de código de producción y los proyectos de código de prueba. Con todo esto su experiencia de desarrollo es mucho más productiva.

Comencemos por crear las carpetas. En el terminal, cree un directorio "golden". En ese directorio cree los directorios `src` y `test`. En `src` cree los directorios `app` y `library`. En `test` cree un directorio `test-library`. Puede hacerlo mediante el terminal en VS Code o haciendo clic en la carpeta principal en VS Code y seleccionando el icono "Nueva carpeta".

En VS Code, abra el directorio 'golden'. Este directorio es la raíz de la solución.

A continuación, cree un archivo `global.json` en el directorio raíz de la solución.
El contenido de `global.json` es:

```json
{
    "projects": [
        "src",
        "test"
    ]
}
```

En este punto, el árbol de directorios debe tener el siguiente aspecto:


```
/golden
|__global.json
|__/src
   |__/app
   |__/library
|__/test
   |__/test-library
```

### <a name="writing-the-library"></a>Escritura de la biblioteca

La siguiente tarea consiste en crear la biblioteca. En la ventana de terminal (tanto el terminal incrustado en VS Code como cualquier otro terminal), cambie al directorio `golden/src/library` y escriba el comando `dotnet new -t lib`.
Esto crea un proyecto de biblioteca con dos archivos: `project.json` y `Library.cs`.

`project.json`contiene la siguiente información:

```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "debugType": "portable"
  },
  "dependencies": {},
  "frameworks": {
    "netstandard1.6": {
      "dependencies": {
        "NETStandard.Library": "1.6.0"
      }
    }
  }
}
```


Este proyecto de biblioteca utilizará la representación de objetos de JSON, por lo que deberá agregar una referencia al paquete NuGet `Newtonsoft.Json`. En`project.json` agregue la versión preliminar más reciente del paquete como una dependencia:

```json
"dependencies": {
    "Newtonsoft.Json": "9.0.1-beta1"
},
```

Una vez haya terminado de agregar esas dependencias, debe instalar esos paquetes en el área de trabajo. Ejecute el comando `dotnet restore` para actualizar todas las dependencias y escriba un archivo `project.lock.json` en el directorio del proyecto. Este archivo contiene el árbol de dependencias completo de todas las dependencias del proyecto. No es necesario que lea este archivo, se utiliza con herramientas del SDK de .NET Core.

Ahora, vamos a actualizar el código de C#. Vamos a crear una clase `Thing` que contiene un método público. Este método devuelve la suma de dos números, pero para ello, convierte ese número en una cadena JSON y, después, lo deserializa. Cambie el nombre del archivo `Library.cs` a `Thing.cs`. A continuación, reemplace el código existente (para la Class1 generada por plantilla) por lo siguiente:

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

Ahora tiene un archivo `library.dll` generado en `golden/src/library/bin/Debug/netstandard1.6`.

### <a name="writing-the-test-project"></a>Escritura del proyecto de prueba

Vamos a crear un proyecto de prueba para esta biblioteca que ha creado. Cambie al directorio `test/test-library`. Ejecute `dotnet new -t xunittest` para crear un proyecto de prueba. 

Necesitará agregar un nodo de dependencia para la biblioteca que escribió en los pasos anteriores. Abra `project.json` y actualice la sección de dependencias de la siguiente forma (incluido el nodo `library`, que es el último nodo que aparece a continuación):

```json
"dependencies": {
  "System.Runtime.Serialization.Primitives": "4.1.1",
  "xunit": "2.1.0",
  "dotnet-test-xunit": "1.0.0-rc2-192208-24",
  "library": {
    "target": "project"
  }
}
```

El nodo `library` especifica que se debe resolver esta dependencia en un proyecto en el área de trabajo actual. Sin especificar explícitamente esto, es posible que el proyecto de prueba se cree en un paquete NuGet del mismo nombre.

Ahora que se han configurado correctamente las dependencias, vamos a crear las pruebas para la biblioteca. Abra `Tests.cs` y reemplace el contenido por el código siguiente:

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

Ahora, ejecute `dotnet restore`, `dotnet build` y `dotnet test`.
El ejecutor de pruebas de la consola xUnit ejecutará una prueba e informará de ello. 

### <a name="writing-the-console-app"></a>Escritura de la aplicación de consola

En el terminal, cambie al directorio `golden/src/app`. Ejecute `dotnet new` para crear una aplicación de consola nueva.

La aplicación de consola depende de la biblioteca que creó y comprobó en los pasos anteriores. Debe indicarlo editando `project.json` para agregar esta dependencia.  En el nodo `dependencies`, agregue el nodo `library` de la siguiente forma:

```json
"dependencies": {
  "library": {
    "target": "project"
  }
}
```

El nodo `project` es importante aquí, como ya lo era en la biblioteca de prueba. Indica que se trata de un proyecto en la solución actual y no un paquete NuGet.

Ejecute `dotnet restore` para restaurar todas las dependencias. Abra `program.cs` y reemplace el contenido del método `Main` por esta línea:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

Necesitará agregar un par de directivas `using` en la parte superior del archivo:

```csharp
using static System.Console;
using Library;
```

Después, ejecute `dotnet build`. Con ello creará los ensamblados y puede escribir `dotnet run` para ejecutar el archivo ejecutable.

### <a name="debugging-your-application"></a>Depuración de la aplicación

Puede depurar el código en VS Code mediante la extensión de C#.
Instale esta extensión presionando `F1` para abrir la paleta de VS Code. Escriba `ext install` para ver la lista de extensiones. Seleccione la extensión de C#. (Hay más detalles disponibles en la página de [documentación de la extensión C# de Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)).

Después de instalar la extensión, VS Code le pedirá que reinicie la aplicación para cargar la nueva extensión. Una vez instalada la extensión, puede abrir la pestaña del depurador (consulte la figura).

![Depurador de VS Code](./media/using-on-macos/vscodedebugger.png)


Al iniciar el depurador, VS Code le pedirá que lo configure. Al hacerlo, crea un directorio `.vscode` con dos archivos: `tasks.json` y `launch.json`. Estos dos archivos controlan la configuración de depurador. En la mayoría de los proyectos, este directorio no se incluye en el control de código fuente.
Se incluye en el ejemplo asociado a este tutorial, para que pueda ver los cambios que necesite hacer.

La solución contiene varios proyectos, por lo que deberá modificar cada uno de estos archivos para realizar los comandos correctos. En primer lugar, abra `tasks.json`. La tarea de compilación predeterminada ejecuta `dotnet build` en el directorio de origen del área de trabajo. Sin embargo, desea ejecutarlo en el directorio `src/app`. Debe agregar un nodo `options` para establecer el directorio de trabajo actual en:

```json
"options": {
    "cwd": "${workspaceRoot}/src/app"
}
```

Después, deberá abrir `launch.json` y actualizar la ruta de acceso del programa. Verá un nodo bajo "configurations" que describe el programa. Verá:

```json
"program": "${workspaceRoot}/bin/Debug/<target-framework>/<project-name.dll>",
```

Va a cambiar esto por:

```json
"program": "${workspaceRoot}/src/app/bin/Debug/netcoreapp1.0/app.dll",
```

Si se ejecuta en Windows, debe actualizar el archivo `project.json` de la aplicación (en el directorio `src/app`) para generar archivos PDB portables (esto sucede de forma predeterminada en Mac OSX y Linux).
Agregue el nodo `debugType` dentro de `buildOptions`. Debe agregar el nodo `debugType` en `project.json` para las carpetas `src/app` y `src/library`.

```json
  "buildOptions": {
    "debugType": "portable"
  },
```

Establezca un punto de interrupción en la instrucción `WriteLine` de `Main`. Para ello, presione la tecla `F9` o haga clic con el mouse en el margen izquierdo en la línea en la que desee el punto de interrupción. Abra el depurador presionando el icono de depuración situado a la izquierda de la pantalla de VS Code (véase la figura). A continuación, presione el botón Reproducir para iniciar la aplicación en el depurador.

Debe alcanzar el punto de interrupción. Recorra paso a paso el método `Get` y asegúrese de que hayan pasado los argumentos correctos. Asegúrese de que la respuesta es realmente 42.



<!--HONumber=Nov16_HO1-->


