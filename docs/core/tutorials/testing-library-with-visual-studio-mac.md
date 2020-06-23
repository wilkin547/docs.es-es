---
title: Prueba de una biblioteca de clases .NET Standard con .NET Core mediante Visual Studio para Mac
description: Cree un proyecto de prueba unitaria para una biblioteca de clases de .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
ms.date: 06/08/2020
ms.openlocfilehash: a183049623df44cbb8c4abd47ce6e78d91adae12
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713308"
---
# <a name="test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="caf72-104">Prueba de una biblioteca de clases .NET Standard con .NET Core mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="caf72-104">Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="caf72-105">En este tutorial se muestra cómo automatizar las pruebas unitarias mediante la adición de un proyecto de prueba a una solución.</span><span class="sxs-lookup"><span data-stu-id="caf72-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="caf72-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="caf72-106">Prerequisites</span></span>

- <span data-ttu-id="caf72-107">Este tutorial funciona con la solución que se crea en [Creación de una biblioteca .NET Standard en Visual Studio para Mac](library-with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="caf72-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="caf72-108">Crear un proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="caf72-108">Create a unit test project</span></span>

<span data-ttu-id="caf72-109">Las pruebas unitarias proporcionan pruebas de software automatizadas durante el desarrollo y la publicación.</span><span class="sxs-lookup"><span data-stu-id="caf72-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="caf72-110">[MSTest](https://github.com/Microsoft/testfx-docs) es uno de los tres marcos de pruebas que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="caf72-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="caf72-111">Los otros son [xUnit](https://xunit.net/) y [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="caf72-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="caf72-112">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="caf72-112">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="caf72-113">Abra la solución `ClassLibraryProjects` que creó en [Creación de una biblioteca .NET Standard en Visual Studio para Mac](library-with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="caf72-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

1. <span data-ttu-id="caf72-114">En el panel **Solución**, presione <kbd>Ctrl</kbd>, haga clic en la solución `ClassLibraryProjects` y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="caf72-114">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="caf72-115">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Pruebas** en el nodo **Web and Console** (Web y consola).</span><span class="sxs-lookup"><span data-stu-id="caf72-115">In the **New Project** dialog, select **Tests** from the **Web and Console** node.</span></span> <span data-ttu-id="caf72-116">Seleccione el **proyecto MSTest** y, luego, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="caf72-116">Select the **MSTest Project** followed by **Next**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="Cuadro de diálogo Nuevo proyecto de Visual Studio para Mac que crea un proyecto de prueba":::

1. <span data-ttu-id="caf72-118">Seleccione **.NET Core 3.1**.</span><span class="sxs-lookup"><span data-stu-id="caf72-118">Select **.NET Core 3.1**.</span></span> <span data-ttu-id="caf72-119">Asigne al nuevo proyecto el nombre "StringLibraryTest" y seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="caf72-119">Name the new project "StringLibraryTest" and select **Create**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="Cuadro de diálogo Nuevo proyecto de Visual Studio para Mac en el que se proporciona el nombre del proyecto":::

   <span data-ttu-id="caf72-121">Visual Studio crea un archivo de clase con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="caf72-121">Visual Studio creates a class file with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   <span data-ttu-id="caf72-122">El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="caf72-122">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="caf72-123">Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="caf72-123">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="caf72-124">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="caf72-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="caf72-125">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> a `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="caf72-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to `TestMethod1`.</span></span>

   <span data-ttu-id="caf72-126">Cada método etiquetado con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) en una clase de prueba etiquetada con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) se ejecuta automáticamente cuando se ejecuta la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="caf72-126">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="caf72-127">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="caf72-127">Add a project reference</span></span>

<span data-ttu-id="caf72-128">Para que el proyecto de prueba funcione con la clase `StringLibrary`, agregue una referencia al proyecto `StringLibrary`.</span><span class="sxs-lookup"><span data-stu-id="caf72-128">For the test project to work with the `StringLibrary` class, add a reference to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="caf72-129">En el panel **Solución**, presione <kbd>Ctrl</kbd> y haga clic en **Dependencias** en **StringLibraryTest**.</span><span class="sxs-lookup"><span data-stu-id="caf72-129">In the **Solution** pad, <kbd>ctrl</kbd>-click **Dependencies** under **StringLibraryTest**.</span></span> <span data-ttu-id="caf72-130">Seleccione **Agregar referencia** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="caf72-130">Select **Add Reference** from the context menu.</span></span>

1. <span data-ttu-id="caf72-131">En el cuadro de diálogo **Referencias**, seleccione el proyecto **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="caf72-131">In the **References** dialog, select the **StringLibrary** project.</span></span> <span data-ttu-id="caf72-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="caf72-132">Select **OK**.</span></span>

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="Cuadro de diálogo Editar referencias de Visual Studio para Mac":::

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="caf72-134">Adición y ejecución de métodos de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="caf72-134">Add and run unit test methods</span></span>

<span data-ttu-id="caf72-135">Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase que está marcada con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="caf72-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="caf72-136">Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="caf72-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="caf72-137">Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="caf72-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="caf72-138">Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba.</span><span class="sxs-lookup"><span data-stu-id="caf72-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="caf72-139">Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="caf72-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="caf72-140">Métodos de aserción</span><span class="sxs-lookup"><span data-stu-id="caf72-140">Assert methods</span></span>     | <span data-ttu-id="caf72-141">Función</span><span class="sxs-lookup"><span data-stu-id="caf72-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="caf72-142">Comprueba que dos valores u objetos son iguales.</span><span class="sxs-lookup"><span data-stu-id="caf72-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="caf72-143">La aserción da error si los valores o los objetos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="caf72-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="caf72-144">Comprueba que dos variables de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="caf72-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="caf72-145">La aserción da error si las variables hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="caf72-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="caf72-146">Comprueba si una condición es `false`.</span><span class="sxs-lookup"><span data-stu-id="caf72-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="caf72-147">La aserción produce un error si la condición es `true`.</span><span class="sxs-lookup"><span data-stu-id="caf72-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="caf72-148">Comprueba que un objeto no es `null`.</span><span class="sxs-lookup"><span data-stu-id="caf72-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="caf72-149">La aserción da error si el objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="caf72-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="caf72-150">También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> en un método de prueba para indicar el tipo de excepción que se espera que produzca.</span><span class="sxs-lookup"><span data-stu-id="caf72-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="caf72-151">La prueba dará error si no se inicia la excepción especificada.</span><span class="sxs-lookup"><span data-stu-id="caf72-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="caf72-152">Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="caf72-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="caf72-153">Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="caf72-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="caf72-154">Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="caf72-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="caf72-155">Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="caf72-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="caf72-156">Dado que el método de biblioteca administra cadenas, quiere asegurarse también de que administra correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo <xref:System.String.Length> sea 0, y una cadena `null` que no se haya inicializado.</span><span class="sxs-lookup"><span data-stu-id="caf72-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="caf72-157">Se puede llamar a `StartsWithUpper` directamente como un método estático y pasar un argumento <xref:System.String> único.</span><span class="sxs-lookup"><span data-stu-id="caf72-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="caf72-158">También puede llamar a `StartsWithUpper` como método de extensión en una variable de `string` asignada a `null`.</span><span class="sxs-lookup"><span data-stu-id="caf72-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="caf72-159">Definirá tres métodos, cada uno de los cuales llama a un método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> para cada elemento de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="caf72-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="caf72-160">Llamará a una sobrecarga de método que le permite especificar que se muestre un mensaje de error en caso de error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="caf72-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="caf72-161">El mensaje identifica la cadena que causó el error.</span><span class="sxs-lookup"><span data-stu-id="caf72-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="caf72-162">Para crear los métodos de prueba:</span><span class="sxs-lookup"><span data-stu-id="caf72-162">To create the test methods:</span></span>

1. <span data-ttu-id="caf72-163">Abra el archivo *UnitTest1.cs* y reemplace el código por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="caf72-163">Open the *UnitTest1.cs* file and replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="caf72-164">La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C).</span><span class="sxs-lookup"><span data-stu-id="caf72-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="caf72-165">La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).</span><span class="sxs-lookup"><span data-stu-id="caf72-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="caf72-166">En la barra de menús, seleccione **Archivo** > **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="caf72-166">On the menu bar, select **File** > **Save As**.</span></span> <span data-ttu-id="caf72-167">En el cuadro de diálogo, asegúrese de que **Codificación** esté establecida en **Unicode (UTF-8)** .</span><span class="sxs-lookup"><span data-stu-id="caf72-167">In the dialog, make sure that **Encoding** is set to **Unicode (UTF-8)**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="Cuadro de diálogo Guardar archivo como de Visual Studio":::

1. <span data-ttu-id="caf72-169">Cuando se le pregunte si quiere reemplazar el archivo existente, seleccione **Reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="caf72-169">When you're asked if you want to replace the existing file, select **Replace**.</span></span>

   <span data-ttu-id="caf72-170">Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII.</span><span class="sxs-lookup"><span data-stu-id="caf72-170">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="caf72-171">Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán correctos.</span><span class="sxs-lookup"><span data-stu-id="caf72-171">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="caf72-172">Abra el panel **Pruebas unitarias** en el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="caf72-172">Open the **Unit Tests** panel on the right side of the screen.</span></span> <span data-ttu-id="caf72-173">En el menú, seleccione **Ver** > **Pruebas**.</span><span class="sxs-lookup"><span data-stu-id="caf72-173">Select **View** > **Tests** from the menu.</span></span>

1. <span data-ttu-id="caf72-174">Haga clic en el icono **Acoplar** para mantener abierto el panel.</span><span class="sxs-lookup"><span data-stu-id="caf72-174">Click the **Dock** icon to keep the panel open.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="Icono de acoplamiento del panel Pruebas unitarias de Visual Studio para Mac":::

1. <span data-ttu-id="caf72-176">Haga clic en el botón **Ejecutar todas**.</span><span class="sxs-lookup"><span data-stu-id="caf72-176">Click the **Run All** button.</span></span>

   <span data-ttu-id="caf72-177">Todas las pruebas se superan.</span><span class="sxs-lookup"><span data-stu-id="caf72-177">All tests pass.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="Prueba superada esperada de Visual Studio para Mac":::

## <a name="handle-test-failures"></a><span data-ttu-id="caf72-179">Administración de errores de prueba</span><span class="sxs-lookup"><span data-stu-id="caf72-179">Handle test failures</span></span>

<span data-ttu-id="caf72-180">Si está realizando el desarrollo controlado por pruebas (TDD), escribirá las pruebas, y estas generarán un error cuando las ejecute por primera vez.</span><span class="sxs-lookup"><span data-stu-id="caf72-180">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="caf72-181">Después, agregará un código a la aplicación para que la prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="caf72-181">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="caf72-182">En este tutorial, ha creado la prueba después de escribir el código de la aplicación que valida, por lo que no ha podido comprobar si la prueba genera un error.</span><span class="sxs-lookup"><span data-stu-id="caf72-182">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="caf72-183">Para asegurarse de que una prueba genera un error cuando espera que lo haga, agregue un valor no válido a la entrada de prueba.</span><span class="sxs-lookup"><span data-stu-id="caf72-183">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="caf72-184">Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="caf72-184">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="caf72-185">No necesita guardar el archivo porque Visual Studio guarda automáticamente archivos abiertos cuando se crea una solución para ejecutar pruebas.</span><span class="sxs-lookup"><span data-stu-id="caf72-185">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="caf72-186">Vuelva a ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="caf72-186">Run the tests again.</span></span>

   <span data-ttu-id="caf72-187">Esta vez, en la ventana **Explorador de pruebas** se indica que dos pruebas se han realizado correctamente y que una ha finalizado con errores.</span><span class="sxs-lookup"><span data-stu-id="caf72-187">This time, the **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="Ventana Explorador de pruebas con pruebas no superadas":::

1. <span data-ttu-id="caf72-189">Presione <kbd>Ctrl</kbd> y haga clic en la prueba con errores, `TestDoesNotStartWithUpper`, y seleccione **Mostrar el panel de resultados** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="caf72-189"><kbd>ctrl</kbd>-click the failed test, `TestDoesNotStartWithUpper`, and select **Show Results Pad** from the context menu.</span></span>

   <span data-ttu-id="caf72-190">El panel **Resultados** muestra el mensaje generado por la aserción: "Error de Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="caf72-190">The **Results** pad displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="caf72-191">Se esperaba para "Error": false; real: True".</span><span class="sxs-lookup"><span data-stu-id="caf72-191">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="caf72-192">Debido al error, no se probaron todas las cadenas de la matriz después de "Error".</span><span class="sxs-lookup"><span data-stu-id="caf72-192">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="Ventana del Explorador de pruebas que muestra el error de aserción IsFalse":::

1. <span data-ttu-id="caf72-194">Quite la cadena "Error" que agregó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="caf72-194">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="caf72-195">Vuelva a ejecutar la prueba y se superarán las pruebas.</span><span class="sxs-lookup"><span data-stu-id="caf72-195">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="caf72-196">Prueba de la versión de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="caf72-196">Test the Release version of the library</span></span>

<span data-ttu-id="caf72-197">Ahora que se han superado todas las pruebas al ejecutar la versión de depuración de la biblioteca, ejecute las pruebas una vez más con la versión de lanzamiento de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="caf72-197">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="caf72-198">Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.</span><span class="sxs-lookup"><span data-stu-id="caf72-198">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="caf72-199">Para probar la compilación de versión:</span><span class="sxs-lookup"><span data-stu-id="caf72-199">To test the Release build:</span></span>

1. <span data-ttu-id="caf72-200">En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="caf72-200">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra de herramientas de Visual Studio con la compilación de versión resaltada":::

1. <span data-ttu-id="caf72-202">En el panel **Solución**, presione <kbd>Ctrl</kbd> y haga clic en el proyecto **StringLibrary** y seleccione **Compilación** en el menú contextual para volver a compilar la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="caf72-202">In the **Solution** pad, <kbd>ctrl</kbd>-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="Menú contextual de StringLibrary con el comando Compilar":::

1. <span data-ttu-id="caf72-204">Ejecute de nuevo las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="caf72-204">Run the unit tests again.</span></span>

   <span data-ttu-id="caf72-205">Las pruebas se superan.</span><span class="sxs-lookup"><span data-stu-id="caf72-205">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="caf72-206">Depuración de pruebas</span><span class="sxs-lookup"><span data-stu-id="caf72-206">Debug tests</span></span>

<span data-ttu-id="caf72-207">Puede usar el mismo proceso que se muestra en el [Tutorial: Depuración de una aplicación de consola de .NET Core con Visual Studio para Mac](debugging-with-visual-studio-mac.md) para depurar el código mediante el proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="caf72-207">You can use the same process shown in [Tutorial: Debug a .NET Core console application using Visual Studio for Mac](debugging-with-visual-studio-mac.md) to debug code using your unit test project.</span></span> <span data-ttu-id="caf72-208">En lugar de iniciar el proyecto de aplicación ShowCase, presione <kbd>Ctrl</kbd> y haga clic en el proyecto **StringLibraryTests** y seleccione **Iniciar depuración del proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="caf72-208">Instead of starting the ShowCase app project, <kbd>ctrl</kbd>-click the **StringLibraryTests** project, and select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="caf72-209">Visual Studio inicia el proyecto de prueba con el depurador asociado.</span><span class="sxs-lookup"><span data-stu-id="caf72-209">Visual Studio starts the test project with the debugger attached.</span></span> <span data-ttu-id="caf72-210">La ejecución se detendrá en cualquier punto de interrupción que haya agregado al proyecto de prueba o al código de la biblioteca subyacente.</span><span class="sxs-lookup"><span data-stu-id="caf72-210">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="caf72-211">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="caf72-211">Additional resources</span></span>

* [<span data-ttu-id="caf72-212">Pruebas unitarias en .NET Core y .NET Standard</span><span class="sxs-lookup"><span data-stu-id="caf72-212">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="caf72-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="caf72-213">Next steps</span></span>

<span data-ttu-id="caf72-214">En este tutorial, ha realizado una prueba unitaria de una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="caf72-214">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="caf72-215">Puede poner la biblioteca a disposición de otros usuarios si la publica en [NuGet](https://nuget.org) como un paquete.</span><span class="sxs-lookup"><span data-stu-id="caf72-215">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="caf72-216">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="caf72-216">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="caf72-217">Crear y publicar un paquete (CLI de dotnet)</span><span class="sxs-lookup"><span data-stu-id="caf72-217">Create and publish a package (dotnet CLI)</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="caf72-218">Si publica una biblioteca como un paquete NuGet, otros usuarios pueden instalarla y usarla.</span><span class="sxs-lookup"><span data-stu-id="caf72-218">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="caf72-219">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="caf72-219">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="caf72-220">Instalación y uso de un paquete en Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="caf72-220">Install and use a package in Visual Studio for Mac</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

<span data-ttu-id="caf72-221">No es necesario distribuir una biblioteca como un paquete.</span><span class="sxs-lookup"><span data-stu-id="caf72-221">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="caf72-222">Se puede agrupar con una aplicación de consola que la use.</span><span class="sxs-lookup"><span data-stu-id="caf72-222">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="caf72-223">Para aprender a publicar una aplicación de consola, vea el tutorial anterior de esta serie:</span><span class="sxs-lookup"><span data-stu-id="caf72-223">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="caf72-224">Publicación de una aplicación de consola de .NET Core con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="caf72-224">Publish a .NET Core console application with Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
