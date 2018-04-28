---
title: Creación de una solución completa de .NET Core en Windows con Visual Studio 2017
description: Obtenga información sobre cómo crear una solución completa de .NET Core en Visual Studio 2017 en Windows.
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 8e37eb578f9c4ac63fbc120e6227098ea69d169d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a><span data-ttu-id="209c7-103">Creación de una solución completa de .NET Core en Windows con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="209c7-103">Building a complete .NET Core solution on Windows, using Visual Studio 2017</span></span>

<span data-ttu-id="209c7-104">Visual Studio 2017 proporciona un entorno de desarrollo completo para las aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="209c7-104">Visual Studio 2017 provides a full-featured development environment for developing .NET Core applications.</span></span> <span data-ttu-id="209c7-105">Los procedimientos de este documento describen los pasos necesarios para compilar una solución típica de .NET Core que incluye bibliotecas reutilizables, pruebas y el uso de bibliotecas de terceros.</span><span class="sxs-lookup"><span data-stu-id="209c7-105">The procedures in this document describe the steps necessary to build a typical .NET Core solution that includes reusable libraries, testing, and using third-party libraries.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="209c7-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="209c7-106">Prerequisites</span></span>

<span data-ttu-id="209c7-107">Siga las instrucciones de [nuestra página de requisitos previos](../windows-prerequisites.md) para actualizar su entorno.</span><span class="sxs-lookup"><span data-stu-id="209c7-107">Follow the instructions on [our prerequisites page](../windows-prerequisites.md) to update your environment.</span></span>

## <a name="a-solution-using-only-net-core-projects"></a><span data-ttu-id="209c7-108">Una solución solo con proyectos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="209c7-108">A solution using only .NET Core projects</span></span>

### <a name="writing-the-library"></a><span data-ttu-id="209c7-109">Escritura de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="209c7-109">Writing the library</span></span>

1. <span data-ttu-id="209c7-110">En Visual Studio, elige **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="209c7-110">In Visual Studio, choose **File**, **New**, **Project**.</span></span> <span data-ttu-id="209c7-111">En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Visual C#**, elija el nodo **.NET Standard** y luego elija **Biblioteca de clases (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="209c7-111">In the **New Project** dialog, expand the **Visual C#** node and choose the **.NET Standard** node, and then choose **Class Library (.NET Standard)**.</span></span> 

2. <span data-ttu-id="209c7-112">Llame "Library" al proyecto y "Golden" a la solución.</span><span class="sxs-lookup"><span data-stu-id="209c7-112">Name the project "Library" and the solution "Golden".</span></span> <span data-ttu-id="209c7-113">Deje desactivada la casilla **Crear directorio para la solución**.</span><span class="sxs-lookup"><span data-stu-id="209c7-113">Leave **Create directory for solution** checked.</span></span> <span data-ttu-id="209c7-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="209c7-114">Click **OK**.</span></span>

3. <span data-ttu-id="209c7-115">En el Explorador de soluciones, abra el menú contextual del nodo **Dependencias** y luego elija **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="209c7-115">In Solution Explorer, open the context menu for the **Dependencies** node and choose **Manage NuGet Packages**.</span></span>

4. <span data-ttu-id="209c7-116">Elija "nuget.org" como **origen del paquete** y elija la pestaña **Examinar**. Busque **Newtonsoft.Json**.</span><span class="sxs-lookup"><span data-stu-id="209c7-116">Choose "nuget.org" as the **Package source**, and choose the **Browse** tab. Browse for **Newtonsoft.Json**.</span></span> <span data-ttu-id="209c7-117">Haga clic en **Instalar** y acepte el acuerdo de licencia.</span><span class="sxs-lookup"><span data-stu-id="209c7-117">Click **Install**, and accept the license agreement.</span></span> <span data-ttu-id="209c7-118">El paquete debe aparecer ahora en **Dependencias/NuGet** y restaurarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="209c7-118">The package should now appear under **Dependencies/NuGet** and be automatically restored.</span></span>

5. <span data-ttu-id="209c7-119">Cambie el nombre del archivo `Class1.cs` a `Thing.cs`.</span><span class="sxs-lookup"><span data-stu-id="209c7-119">Rename the `Class1.cs` file to `Thing.cs`.</span></span> <span data-ttu-id="209c7-120">Acepte el cambio de nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="209c7-120">Accept the rename of the class.</span></span> <span data-ttu-id="209c7-121">Agregue un método: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span><span class="sxs-lookup"><span data-stu-id="209c7-121">Add a method: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span></span>

7. <span data-ttu-id="209c7-122">En el menú **Compilar** , elija **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="209c7-122">On the **Build** menu, choose **Build Solution**.</span></span>

   <span data-ttu-id="209c7-123">La solución se debe compilar sin errores.</span><span class="sxs-lookup"><span data-stu-id="209c7-123">The solution should build without error.</span></span>

### <a name="writing-the-test-project"></a><span data-ttu-id="209c7-124">Escritura del proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="209c7-124">Writing the test project</span></span>

1. <span data-ttu-id="209c7-125">En el Explorador de soluciones, abra el menú contextual del nodo **Solución** y elija **Agregar**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="209c7-125">In Solution Explorer, open the context menu for the **Solution** node and choose **Add**, **New Project**.</span></span> <span data-ttu-id="209c7-126">En el cuadro de diálogo **Nuevo proyecto**, en **Visual C# / .NET Core**, elija **Proyecto de prueba unitaria (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="209c7-126">In the **New Project** dialog, under **Visual C# / .NET Core**, choose **Unit Test Project (.NET Core)**.</span></span> <span data-ttu-id="209c7-127">Asígnele el nombre "TestLibrary" y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="209c7-127">Name it "TestLibrary" and click OK.</span></span> 

2. <span data-ttu-id="209c7-128">En el proyecto **TestLibrary**, abra el menú contextual del nodo **Dependencias** y elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="209c7-128">In the **TestLibrary** project, open the context menu for the **Dependencies** node and choose **Add Reference**.</span></span> <span data-ttu-id="209c7-129">Haga clic en **Proyectos**, marque el proyecto de biblioteca y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="209c7-129">Click **Projects**, then check the Library project and click OK.</span></span> <span data-ttu-id="209c7-130">Se agrega una referencia a la biblioteca desde el proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="209c7-130">This adds a reference to your library from the test project.</span></span>

3. <span data-ttu-id="209c7-131">Cambie el nombre del archivo `UnitTest1.cs` por `LibraryTests.cs` y acepte el cambio de nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="209c7-131">Rename the `UnitTest1.cs` file to `LibraryTests.cs` and accept the class rename.</span></span> <span data-ttu-id="209c7-132">Agregue `using Library;` al principio del archivo y sustituya el método `TestMethod1` por el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="209c7-132">Add `using Library;` to the top of the file, and replace the `TestMethod1` method with the following code:</span></span>
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   <span data-ttu-id="209c7-133">Ahora debería poder compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="209c7-133">You should now be able to build the solution.</span></span> 
   
4. <span data-ttu-id="209c7-134">En el menú **Prueba**, elija **Windows**, **Explorador de pruebas** para introducir la ventana del explorador de pruebas en su área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="209c7-134">On the **Test** menu, choose **Windows**, **Test Explorer** in order to get the test explorer window into your workspace.</span></span> <span data-ttu-id="209c7-135">Al cabo de unos segundos, la prueba `ThingGetsObjectValFromNumber` debe aparecer en el Explorador de pruebas.</span><span class="sxs-lookup"><span data-stu-id="209c7-135">After a few seconds, the `ThingGetsObjectValFromNumber` test should appear in the test explorer.</span></span> <span data-ttu-id="209c7-136">Elija **Ejecutar todas**.</span><span class="sxs-lookup"><span data-stu-id="209c7-136">Choose **Run All**.</span></span>
   
   <span data-ttu-id="209c7-137">La prueba debe realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="209c7-137">The test should pass.</span></span>

### <a name="writing-the-console-app"></a><span data-ttu-id="209c7-138">Escritura de la aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="209c7-138">Writing the console app</span></span>

1. <span data-ttu-id="209c7-139">En el Explorador de soluciones, abra el menú contextual de la solución y agregue un nuevo proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="209c7-139">In Solution Explorer, open the context menu for the solution, and add a new **Console App (.NET Core)** project.</span></span> <span data-ttu-id="209c7-140">Asígnele el nombre "App".</span><span class="sxs-lookup"><span data-stu-id="209c7-140">Name it "App".</span></span>

2. <span data-ttu-id="209c7-141">En el proyecto **App**, abra el menú contextual del nodo **Dependencias** y elija **Agregar**, **Referencia**.</span><span class="sxs-lookup"><span data-stu-id="209c7-141">In the **App** project, open the context menu for the **Dependencies** node and choose **Add**,  **Reference**.</span></span> 

3. <span data-ttu-id="209c7-142">En el cuadro de diálogo **Administrador de referencias**, active **Biblioteca** bajo el nodo **Proyectos**, **Solución** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="209c7-142">In the **Reference Manager** dialog, check **Library** under the **Projects**, **Solution** node, and then click **OK**</span></span>

6. <span data-ttu-id="209c7-143">Abra el menú contextual por el nodo **App** y elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="209c7-143">Open the context menu for the **App** node and choose **Set as StartUp Project**.</span></span> <span data-ttu-id="209c7-144">Esto garantiza que al presionar F5 o CTRL+F5 se iniciará la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="209c7-144">This ensures that hitting F5 or CTRL+F5 will start the console app.</span></span>

7. <span data-ttu-id="209c7-145">Abra el archivo `Program.cs`, agregue una directiva `using Library;` en la parte superior del archivo y, después, agregue `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` al método `Main`.</span><span class="sxs-lookup"><span data-stu-id="209c7-145">Open the `Program.cs` file, add a `using Library;` directive to the top of the file, and then add `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` to the `Main` method.</span></span>

8. <span data-ttu-id="209c7-146">Establezca un punto de interrupción después de la línea que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="209c7-146">Set a breakpoint after the line that you just added.</span></span>

9. <span data-ttu-id="209c7-147">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="209c7-147">Press F5 to run the application..</span></span>

   <span data-ttu-id="209c7-148">La aplicación se debe compilar sin errores y debe alcanzar el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="209c7-148">The application should build without error, and should hit the breakpoint.</span></span> <span data-ttu-id="209c7-149">También debe ser capaz de comprobar que aplicación produce la salida "La respuesta es 42".</span><span class="sxs-lookup"><span data-stu-id="209c7-149">You should also be able to check that the application output "The answer is 42.".</span></span>
