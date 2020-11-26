---
title: Creación de una biblioteca de clases de .NET con Visual Studio Code
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET mediante Visual Studio Code.
ms.date: 11/18/2020
ms.openlocfilehash: 4daa077fc54da3de2f808d831e06ee5f9bb3bde7
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916096"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-code"></a>Tutorial: Creación de una biblioteca de clases de .NET con Visual Studio Code

En este tutorial, creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.

Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación. Si la biblioteca tiene como destino .NET Standard 2.0, se puede llamar mediante cualquier implementación de .NET (incluido .NET Framework) que admita .NET Standard 2.0. Si la biblioteca tiene como destino .NET 5, la puede llamar cualquier aplicación que tenga como destino .NET 5. En este tutorial se muestra cómo seleccionar .NET 5 como destino.

Al crear una biblioteca de clases, puede distribuirla como un componente de terceros o como un componente empaquetado con una o varias aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

1. [Visual Studio Code](https://code.visualstudio.com/) con la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) instalada. Para saber cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [SDK de .NET 5.0 o posterior](https://dotnet.microsoft.com/download)

## <a name="create-a-solution"></a>Crear una solución

Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella. Una solución sirve como contenedor de uno o varios proyectos. Agregará otros proyectos relacionados a la misma solución.

1. Inicie Visual Studio Code.

1. Seleccione **Archivo** > **Abrir carpeta** (**Abrir...** en macOS) en el menú principal.

1. En el cuadro de diálogo **Abrir carpeta**, cree una carpeta *ClassLibraryProjects* y haga clic en **Seleccionar carpeta** (**Abrir** en macOS).

1. Para abrir el **Terminal**  en Visual Studio Code, seleccione **Ver** > **Terminal** en el menú principal.

   Se abre el **terminal** con el símbolo del sistema en la carpeta *ClassLibraryProjects*.

1. En el **Terminal**, escriba este comando:

   ```dotnetcli
   dotnet new sln
   ```

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a>Crear un proyecto de biblioteca de clases

Agregue un nuevo proyecto de biblioteca de clases de .NET denominado "StringLibrary" a la solución.

1. En el terminal, ejecute el siguiente comando para crear un proyecto de biblioteca:

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   El comando `-o` o `--output` especifica la ubicación para colocar la salida generada.

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj (in 328 ms).
   Restore succeeded.
   ```

1. Ejecute el siguiente comando para agregar el proyecto de biblioteca a la solución:

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. Asegúrese de que la biblioteca tiene como destino .NET 5. En **Explorer**, abra el archivo *StringLibrary/StringLibrary.csproj*.

   En el elemento `TargetFramework` se muestra que el proyecto tiene como destino .NET 5.0.

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>net5.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. Abra *Class1.cs* y reemplace el código por el siguiente.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`. Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula. El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas. El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.

1. Guarde el archivo.

1. Ejecute el siguiente comando para compilar la solución y comprobar que el proyecto se compila sin errores.

   ```dotnetcli
   dotnet build
   ```

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\net5.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a>Incorporación de una aplicación de consola a la solución

Agregue una aplicación de consola que use la biblioteca de clases. La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.

1. En el terminal, ejecute el siguiente comando para crear un proyecto de consola de aplicación:

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj (in 210 ms).
   Restore succeeded.
   ```

1. Ejecute el siguiente comando para agregar el proyecto de aplicación de consola a la solución:

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. Abra *ShowCase/Program.cs* y reemplace todo el código por el siguiente.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola. Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.

   El programa le pide al usuario que escriba una cadena. Indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.

1. Guarde los cambios.

## <a name="add-a-project-reference"></a>Agregar una referencia de proyecto

En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases. Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.

1. Ejecute el siguiente comando:

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a>Ejecutar la aplicación

1. Ejecute el siguiente comando en el terminal:

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.

   La salida del terminal se parece al ejemplo siguiente:

   ```output
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   a string that starts with a lowercase letter
   Input: a string that starts with a lowercase letter
   Begins with uppercase? : No
   ```

## <a name="additional-resources"></a>Recursos adicionales

* [Desarrollo de bibliotecas con la CLI de .NET](libraries.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca. En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.

> [!div class="nextstepaction"]
> [Prueba de una biblioteca de clases de .NET con .NET mediante Visual Studio Code](testing-library-with-visual-studio-code.md)
