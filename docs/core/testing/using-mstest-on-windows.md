---
title: Uso de MSTest con .NET Core en Windows
description: "Cómo usar MSTest con .NET Core en Windows con Visual Studio 2015"
keywords: MSTest, .NET, .NET Core
author: ncarandini
manager: wpickett
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
translationtype: Human Translation
ms.sourcegitcommit: 6795f1ace77e6f4d1b2fe07e6281f4acb6d21271
ms.openlocfilehash: c9d6bb1d45b9a6cb88334050669a4c064e53d54e

---

# <a name="unit-testing-with-mstest-and-net-core-on-windows-using-visual-studio-2015"></a>Pruebas unitarias con MSTest y .NET Core en Windows con Visual Studio 2015

Aunque xUnit podría ser la mejor opción al destinarse a varias plataformas, con .NET Core en Windows también es posible usar MSTest.

## <a name="prerequisites"></a>Requisitos previos

Siga las instrucciones de [Introducción a .NET Core en Windows](../tutorials/using-on-windows.md) para crear el proyecto de biblioteca.

### <a name="writing-the-test-project-using-mstest"></a>Escribir el proyecto de prueba con MSTest

1. En el Explorador de soluciones, abra el menú contextual del nodo **Solución** y elija **Agregar**, **Nueva carpeta de soluciones**. Asigne un nombre a la carpeta "test". 
   Esto es solo una carpeta de soluciones, no una carpeta física.

2. Abra el menú contextual de la carpeta **test** y elija **Agregar**. **Nuevo proyecto**. En el cuadro de diálogo **Nuevo proyecto**, elija **Aplicación de consola (.NET Core)**. Asígnele el nombre "TestLibrary" y colóquelo explícitamente en la ruta de acceso `Golden\test`. 

   > [!IMPORTANT]
   > El proyecto debe ser una aplicación de consola, no una biblioteca de clases.

3. En el proyecto **TestLibrary**, abra el menú contextual del nodo **Referencias** y elija **Agregar referencia**. 

4. En el cuadro de diálogo **Administrador de referencias**, active **Biblioteca** bajo el nodo **Proyectos**, **Solución** y, después, haga clic en **Aceptar**. 

5. En el proyecto **TestLibrary**, abra el archivo `project.json` y reemplace `"Library": "1.0.0-*"` por `"Library": {"target": "project"}`. 

   Esto es para evitar la resolución del proyecto `Library` en un paquete NuGet con el mismo nombre. Si se establece explícitamente el destino en "proyecto", se garantiza que las herramientas buscarán primero un proyecto con ese nombre y no un paquete. 

6. Abra el menú contextual del nodo **Referencias** y, después, elija **Administrar paquetes NuGet**.

7. Elija "nuget.org" como **origen del paquete** y elija la pestaña **Examinar**. Active la casilla **Incluir versión preliminar** y, después, busque **MSTest.TestFramework** versión 1.0.1-preview o más reciente y haga clic en **Instalar**. 

8. Busque **dotnet-test-mstest** versión 1.1.1-preview o más reciente y haga clic en **Instalar**.

9. Edite `project.json` para agregar `"testRunner": "mstest",` después de la sección `"version"`.

10. Agregue un archivo de clase `LibraryTests.cs` al proyecto **TestLibrary**, agregue las directivas `using` `Microsoft.VisualStudio.TestTools.UnitTesting;` y `using Library;` en la parte superior del archivo y agregue el código siguiente a la clase:
    ```csharp
    [TestClass]
    public class LibraryTests
    {
        [TestMethod]
        public void ThingGetsObjectValFromNumber()
        {
            Assert.AreEqual(42, new Thing().Get(42));
        }
    }
    ```
    * Opcionalmente, elimine el archivo `Program.cs` en el proyecto **TestLibrary** y quite `"buildOptions": {"emitEntryPoint": true},` de `project.json`.

   Ahora debería poder compilar la solución. 
   
11. En el menú **Prueba**, elija **Windows**, **Explorador de pruebas** y, en el Explorador de pruebas, seleccione **Ejecutar todo**.
   
   La prueba debe realizarse correctamente.



<!--HONumber=Nov16_HO1-->


