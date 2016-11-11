---
title: "Introducción a .NET Core en Windows"
description: "Introducción a .NET Core en Windows con Visual Studio 2015"
keywords: .NET, .NET Core
author: bleroy
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d743134a-08a3-4ff6-aab7-49f71f0568c3
translationtype: Human Translation
ms.sourcegitcommit: 54da8aebd64e86c064214074bc261f72c3b0aedc
ms.openlocfilehash: 299d479ce74a0e1f41ff42a0e6619f4964788194

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2015"></a>Introducción a .NET Core en Windows con Visual Studio 2015

por [Bertrand Le Roy](https://github.com/bleroy) y [Phillip Carter](https://github.com/cartermp)

Visual Studio 2015 proporciona un entorno de desarrollo completo para el desarrollo de aplicaciones .NET Core. Los procedimientos descritos en este documento describen los pasos necesarios para crear un número de soluciones .NET Core típicas o soluciones que incluyen componentes de .NET Core, con Visual Studio. Los escenarios incluyen pruebas y el uso de bibliotecas de terceros que no se han creado explícitamente para la versión más reciente de .NET Core. 

## <a name="prerequisites"></a>Requisitos previos

Siga las instrucciones de [nuestra página de requisitos previos](../windows-prerequisites.md) para actualizar su entorno.

## <a name="getting-started"></a>Introducción

En los pasos siguientes se configurará Visual Studio 2015 para el desarrollo de .NET Core:

1. Abra Visual Studio y, en el menú **Archivo**, elija **Nuevo**, **Proyecto**.

2. En el cuadro de diálogo **Nuevo proyecto**, en la lista **Plantillas**, expanda el nodo **Visual C#** y elija **.NET Core**. Debe ver tres nuevas plantillas de proyecto para **Biblioteca de clases (.NET Core)**, **Aplicación de consola (.NET Core)** y **Aplicación web de ASP.NET Core (.NET Core)**.

<a name="a-solution-using-only-net-core-projects"></a>Una solución solo con proyectos de .NET Core
----------------------------------------

### <a name="writing-the-library"></a>Escritura de la biblioteca

1. En Visual Studio, elija **Archivo**, **Nuevo**, **Proyecto**. En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Visual Basic** o **Visual C#** y elija **Biblioteca de clases (.NET Core)**. 

2. Llame "Library" al proyecto y "Golden" a la solución. Deje desactivada la casilla **Crear directorio para la solución**. Haga clic en **Aceptar**.

3. En el Explorador de soluciones, abra el menú contextual del nodo **Referencias** y, después, elija **Administrar paquetes NuGet**.

4. Elija "nuget.org" como **origen del paquete** y elija la pestaña **Examinar**. Busque **Newtonsoft.Json**. Haga clic en **Instalar**. 

5. Abra el menú contextual del nodo **Referencias** y, después, elija **Restaurar paquetes**.

6. Cambie el nombre del archivo `Class1.cs` a `Thing.cs`. Acepte el cambio de nombre de la clase. Quite el constructor y agregue un método:`public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`

7. En el menú **Compilar** , elija **Compilar solución**.

   La solución se debe compilar sin errores.

### <a name="writing-the-test-project"></a>Escritura del proyecto de prueba

1. En el Explorador de soluciones, abra el menú contextual del nodo **Solución** y elija **Agregar**, **Nueva carpeta de soluciones**. Asigne un nombre a la carpeta "test". 
   Esto es solo una carpeta de soluciones, no una carpeta física.

2. Abra el menú contextual de la carpeta **test** y elija **Agregar**. **Nuevo proyecto**. En el cuadro de diálogo **Nuevo proyecto**, elija **Aplicación de consola (.NET Core)**. Asígnele el nombre "TestLibrary" y colóquelo explícitamente en la ruta de acceso `Golden\test`. 

> [!IMPORTANT]
> El proyecto debe ser una aplicación de consola, no una biblioteca de clases.

3. En el proyecto **TestLibrary**, abra el menú contextual del nodo **Referencias** y elija **Agregar referencia**. 

4. En el cuadro de diálogo **Administrador de referencias**, active **Biblioteca** bajo el nodo **Proyectos**, **Solución** y, después, haga clic en **Aceptar**. 

5. En el proyecto **TestLibrary**, abra el archivo `project.json` y reemplace `"Library": "1.0.0-*"` por `"Library": {"target": "project", "version": "1.0.0-*"}`. 

   Esto es para evitar la resolución del proyecto `Library` en un paquete NuGet con el mismo nombre. Si se establece explícitamente el destino en "proyecto", se garantiza que las herramientas buscarán primero un proyecto con ese nombre y no un paquete. 
   
6. En el proyecto **TestLibrary**, abra el menú contextual del nodo **Referencias** y elija **Restaurar paquetes**.

7. Abra el menú contextual del nodo **Referencias** y, después, elija **Administrar paquetes NuGet**.

8. Elija "nuget.org" como **origen del paquete** y elija la pestaña **Examinar**. Active la casilla **Incluir versión preliminar** y, después, busque **xUnit** versión 2.2.0 o más reciente y haga clic en **Instalar**. 

9. Busque **dotnet-test-xunit** versión 2.2.0 o más reciente y haga clic en **Instalar**.

10. Editar `project.json` y reemplace `"imports": "dnxcore50"` con `"imports": [ "dnxcore50", "portable-net45+win8" ]`. 

   Esto permite que las bibliotecas de xunit se restauren correctamente y se utilicen en el proyecto: se han compilado dichas bibliotecas para usarlas con perfiles portátiles que incluyen "portable-net45+win8", pero no .NET Core, que no existía cuando se compilaron. El `import` relaja las comprobaciones de la versión de herramientas en tiempo de compilación. Ahora, puede restaurar los paquetes sin errores.

11. Edite `project.json` para agregar `"testRunner": "xunit",` después de la sección `"frameworks"`.

12. Agregue un archivo de clase `LibraryTests.cs` al proyecto **TestLibrary**, agregue las directivas `using` `using Xunit;` y `using Library;` en la parte superior del archivo y agregue el código siguiente a la clase:
    ```csharp
    [Fact]
    public void ThingGetsObjectValFromNumber() {
        Assert.Equal(42, new Thing().Get(42));
    }
    ```
    * Opcionalmente, elimine el archivo `Program.cs` en el proyecto **TestLibrary** y quite `"buildOptions": {"emitEntryPoint": true},` de `project.json`.

   Ahora debería poder compilar la solución. 
   
13. En el menú **Prueba**, elija **Windows**, **Explorador de pruebas** y, en el Explorador de pruebas, seleccione **Ejecutar todo**.
   
   La prueba debe realizarse correctamente.

### <a name="writing-the-console-app"></a>Escritura de la aplicación de consola

1. En el Explorador de soluciones, abra el menú contextual de la carpeta `src` y agregue un nuevo proyecto **Aplicación de consola (.NET Core)**. Asígnele el nombre de "App" y establezca la ubicación en `Golden\src`.

2. En el proyecto **App**, abra el menú contextual por el nodo **Referencias** y elija **Agregar**, **Referencia**. 

3. En el cuadro de diálogo **Administrador de referencias**, active **Biblioteca** bajo el nodo **Proyectos**, **Solución** y, después, haga clic en **Aceptar**.

4. En el proyecto **App**, abra el archivo `project.json` y reemplace `"Library": "1.0.0-*"` por `"Library": {"target": "project"}`.

5. Abra el menú contextual por el nodo **Referencias** y, después, elija **Restaurar paquetes**.

6. Abra el menú contextual por el nodo **App** y elija **Establecer como proyecto de inicio**.

7. Abra el archivo `Program.cs`, agregue una directiva `using Library;` en la parte superior del archivo y, después, agregue `Console.WriteLine($"The answer is {new Thing().Get(42)}");` al método `Main`.

8. Establezca un punto de interrupción después de la línea que acaba de agregar.

9. Presione F5 para ejecutar la aplicación.

   La aplicación se debe compilar sin errores y debe alcanzar el punto de interrupción. También debe ser capaz de comprobar que aplicación produce la salida "La respuesta es 42".

<a name="a-mixed-net-core-library-and-net-framework-application"></a>Una biblioteca de .NET Core y una aplicación de .NET Framework mixta
--------------------------------------------------------

A partir de la solución obtenida con el script anterior, ejecute los siguientes pasos:

1. En el Explorador de soluciones, abra el archivo `project.json` para el proyecto **Library** y reemplace `"frameworks": {
    "netstandard1.6" }` por `"frameworks": {
    "netstandard1.4" }`.

2. En el proyecto **Library**, abra el menú contextual del nodo **Referencias** y elija **Restaurar paquetes**.

   La solución todavía debe compilar y funcionar exactamente como lo hizo antes: la prueba debe realizarse correctamente y la consola de aplicación debe ejecutarse y ser depurable.

3. En el proyecto **Library**, abra el menú contextual y elija **Compilar**.

4. En el Explorador de soluciones, abra el menú contextual de la carpeta `src` y elija **Agregar**. , **Nuevo proyecto**.

5. En el cuadro de diálogo **Nuevo proyecto**, elija el nodo **Visual C#** y, después, elija **Aplicación de consola**.

> [!IMPORTANT]
> Asegúrese de elegir una aplicación de consola estándar, no la versión de .NET Core. En esta sección, estará consumiendo la biblioteca desde una aplicación de .NET Framework.

6. Denomine al proyecto "FxApp" y establezca la ubicación en `Golden\src`.

7. En el proyecto **FxApp**, abra el menú contextual por el nodo **Referencias** y elija **Agregar referencia**.

8. En el cuadro de diálogo **Administrador de referencias**, elija **Examinar** y vaya a la ubicación de la compilación `Library.dll` (en la ruta de acceso ..Golden\src\Library\bin\Debug\netstandard1.4) y después haga clic en **Agregar**. 

   También puede empaquetar la biblioteca y hacer referencia al paquete, como otra forma de hacer referencia a .NET Core desde .NET Framework.

9. Abra el menú contextual del nodo **Referencias** y, después, elija **Administrar paquetes NuGet**.

10. Elija "nuget.org" como **origen del paquete** y elija la pestaña **Examinar**. Active la casilla **Incluir versión preliminar** y, después, busque **Newtonsoft.Json**. Haga clic en **Instalar**. 

11. En el proyecto **FxApp**, abra el archivo `Program.cs` y agregue una directiva `using Library;` en la parte superior del archivo y agregue `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` al método `Main` del programa.

12. Establezca un punto de interrupción después de la línea que acaba de agregar.

13. Convierta a **FxApp** en la aplicación de inicio para la solución.

14. Presione F5 para ejecutar la aplicación.

   La aplicación debe crear y llegar al punto de interrupción. El resultado de la aplicación debe ser "La respuesta es 42".
   
   > [!TIP]
   > En la plataforma Windows puede usar MSTest. Obtenga más información en el artículo [sobre el uso de MSTest en documentos de Windows](../testing/using-mstest-on-windows.md).

<a name="moving-a-library-from-netstandard-14-to-13"></a>Traslado de una biblioteca de netstandard 1.4 a 1.3
--------------------------------------------

1. En el Explorador de soluciones, abra el archivo `project.json` para el proyecto **Library**.

2. Reemplace `frameworks": { "netstandard1.4" }` por `frameworks": { "netstandard1.3" }`.

3. En el proyecto **Library**, abra el menú contextual del nodo **Referencias** y elija **Restaurar paquetes**.

4. En el menú **Compilar**, elija **Compilar solución**.

5. Quite la referencia `Library` desde **FxApp** y después agrégala mediante la ruta de acceso ..Golden\src\Library\bin\Debug\netstandard1.3. Ahora hará referencia a la versión 1.3.

6. Presione F5 para ejecutar la aplicación.

   Todo debería seguir funcionando como antes. Compruebe que el resultado de la aplicación es "La respuesta es 42", que se ha alcanzado el punto de interrupción y que se pueden inspeccionar las variables.

<a name="a-mixed-pcl-library-and-net-framework-application"></a>Una biblioteca de PCL y una aplicación de .NET Framework mixta
--------------------------------------------------

Cierre la solución anterior si estaba abierta: se iniciará un nuevo script desde esta sección.

### <a name="writing-the-library"></a>Escritura de la biblioteca

1. En Visual Studio, elija **Archivo**, **Nuevo**, **Proyecto**. En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Visual C#** y elija **Biblioteca de clases (Portable para iOS, Android y Windows)**. 

2. Llame "PCLLibrary" al proyecto y "GoldenPCL" a la solución. Deje desactivada la casilla **Crear directorio para la solución**. Haga clic en **Aceptar**.

3. En el Explorador de soluciones, abra el menú contextual del nodo **Referencias** y, después, elija **Administrar paquetes NuGet**.

4. Elija "nuget.org" como **origen del paquete** y elija la pestaña **Examinar**. Active la casilla **Incluir versión preliminar** y, después, busque **Newtonsoft.Json**. Haga clic en **Instalar**. 

5. Cambie el nombre de la clase "Thing" y agregue un método:`public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`

6. En el menú **Compilar**, elija **Compilar solución** y compruebe que la solución se compila.

### <a name="writing-the-console-app"></a>Escritura de la aplicación de consola

1. En el Explorador de soluciones, abra el menú contextual para el nodo **Solución 'GoldenPCL'** y elija **Agregar**. **Nuevo proyecto**. En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Visual C#**, elija **Aplicación de consola** y llame al proyecto "App". 

2. En el proyecto **App**, abra el menú contextual por el nodo **Referencias** y elija **Agregar**, **Referencia**. 

3. En el cuadro de diálogo **Administrador de referencias**, elija **Examinar** y vaya a la ubicación de la compilación `PCLLibrary.dll` (en la ruta de acceso ..\GoldenPCL\PCLLibrary\bin\Debug) y después haga clic en **Agregar**. 

4. En el proyecto **App**, abra el archivo `Program.cs` y agregue una directiva `using PCLLibrary;` en la parte superior del archivo y agregue `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` al método `Main` del programa.

5. Establezca un punto de interrupción después de la línea que acaba de agregar.

6. En el Explorador de soluciones, abra el menú contextual por el nodo **App** y elija **Establecer como proyecto de inicio**.

7. Presione F5 para ejecutar la aplicación.

   La aplicación debe compilarse, ejecutarse y llegar al punto de interrupción después de dar como resultado "La respuesta es 42".

<a name="moving-a-pcl-to-a-netstandard-library"></a>Traslado de una PCL a una biblioteca de NetStandard
-------------------------------------
Las herramientas de Biblioteca de clases portable pueden modificar automáticamente la PCL en .NET Standard de destino. 

1.  Haga doble clic en el nodo "Propiedades" para abrir la página de propiedades del proyecto 

2.  En el “Targeting header” (Encabezado de destino), haga clic en el hipervínculo “Usar como destino la plataforma del estándar .NET”.

3.  Haga clic en "Sí" cuando se le pida confirmación.

Las herramientas seleccionarán automáticamente la versión de .NET Standard que incluye todos los destinos dirigidos originalmente por la PCL. Se puede tener como destino una versión diferente de .NET Standard mediante la lista desplegable .NET estándar en la página de propiedades del proyecto.
 
* Si anteriormente tenía un archivo packages.config, quizá se le pida que desinstale los paquetes instalados antes de la conversión.

### <a name="manually-edit-projectjson-to-target-net-standard-from-an-existing-portable-class-library"></a>Edite manualmente el archivo project.json para usar como destino .NET Standard desde una biblioteca de clases portable existente.

1.  Si el archivo project.json contiene "dnxcore50" en el elemento "supports", quítelo.

2.  Quite la dependencia en "Microsoft.NETCore".

3.  Modifique la dependencia en "Microsoft.NETCore.Portable.Compatibility" versión "1.0.0" a "1.0.1".

4.  Agregue una dependencia en "NETStandard.Library" versión "1.6.0".

5.  En el elemento "frameworks", quite la plataforma "dotnet" (y el elemento "imports" dentro de ella).

6.  Agregue ` "netstandard1.x” : { } ` al elemento frameworks, donde x se reemplaza por la versión de .NET Standard que desea usar como destino.

### <a name="example-projectjson"></a>Archivo project.json de ejemplo

Este archivo project.json incluye cláusulas para UWP y .NET 4.6 y usa como destino netstandard1.3:
```
{
  "supports": {
    "net46.app": {},
    "uwp.10.0.app": {},
  },
  "dependencies": {
    "NETStandard.Library": "1.6.0",
    "Microsoft.NETCore.Portable.Compatibility": "1.0.1"
  },
  "frameworks": {
    "netstandard1.3" : {}
  }
}
```





<!--HONumber=Nov16_HO1-->


