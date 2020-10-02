---
title: Prueba de una biblioteca de clases .NET Standard con .NET Core mediante Visual Studio Code
description: Cree un proyecto de prueba unitaria para una biblioteca de clases de .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
ms.date: 06/08/2020
ms.openlocfilehash: 6ae8f6637319cd2c8c24f3e673fb6094f36b9f2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180460"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio-code"></a><span data-ttu-id="6440e-104">Tutorial: Prueba de una biblioteca de clases .NET Standard con .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6440e-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="6440e-105">En este tutorial se muestra cómo automatizar las pruebas unitarias mediante la adición de un proyecto de prueba a una solución.</span><span class="sxs-lookup"><span data-stu-id="6440e-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6440e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6440e-106">Prerequisites</span></span>

- <span data-ttu-id="6440e-107">Este tutorial funciona con la solución que se crea en [Creación de una biblioteca de .NET Standard con Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="6440e-107">This tutorial works with the solution that you create in [Create a .NET Standard library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="6440e-108">Crear un proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="6440e-108">Create a unit test project</span></span>

<span data-ttu-id="6440e-109">Las pruebas unitarias proporcionan pruebas de software automatizadas durante el desarrollo y la publicación.</span><span class="sxs-lookup"><span data-stu-id="6440e-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="6440e-110">El marco de trabajo de pruebas que se usa en este tutorial es MSTest.</span><span class="sxs-lookup"><span data-stu-id="6440e-110">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="6440e-111">[MSTest](https://github.com/Microsoft/testfx-docs) es uno de los tres marcos de pruebas que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="6440e-111">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="6440e-112">Los otros son [xUnit](https://xunit.net/) y [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="6440e-112">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="6440e-113">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="6440e-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="6440e-114">Abra la solución `ClassLibraryProjects` que creó en [Creación de una biblioteca .NET Standard con Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="6440e-114">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library using Visual Studio Code](library-with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="6440e-115">Cree un proyecto de prueba unitaria denominado "StringLibraryTest".</span><span class="sxs-lookup"><span data-stu-id="6440e-115">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="6440e-116">La plantilla de proyecto crea un archivo UnitTest1.cs con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6440e-116">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="6440e-117">El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6440e-117">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="6440e-118">Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="6440e-118">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="6440e-119">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="6440e-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="6440e-120">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> para definir `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="6440e-120">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="6440e-121">Cada método etiquetado con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) en una clase de prueba etiquetada con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) se ejecuta automáticamente cuando se ejecuta la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="6440e-121">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="6440e-122">Agregue el proyecto de prueba a la solución:</span><span class="sxs-lookup"><span data-stu-id="6440e-122">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="6440e-123">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="6440e-123">Add a project reference</span></span>

<span data-ttu-id="6440e-124">Para que el proyecto de prueba funcione con la clase `StringLibrary`, agregue una referencia del proyecto `StringLibraryTest` al proyecto `StringLibrary`.</span><span class="sxs-lookup"><span data-stu-id="6440e-124">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="6440e-125">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="6440e-125">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="6440e-126">Adición y ejecución de métodos de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="6440e-126">Add and run unit test methods</span></span>

<span data-ttu-id="6440e-127">Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase que está marcada con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6440e-127">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="6440e-128">Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6440e-128">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="6440e-129">Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="6440e-129">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="6440e-130">Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba.</span><span class="sxs-lookup"><span data-stu-id="6440e-130">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="6440e-131">Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6440e-131">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="6440e-132">Métodos de aserción</span><span class="sxs-lookup"><span data-stu-id="6440e-132">Assert methods</span></span>     | <span data-ttu-id="6440e-133">Función</span><span class="sxs-lookup"><span data-stu-id="6440e-133">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="6440e-134">Comprueba que dos valores u objetos son iguales.</span><span class="sxs-lookup"><span data-stu-id="6440e-134">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="6440e-135">La aserción da error si los valores o los objetos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="6440e-135">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="6440e-136">Comprueba que dos variables de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="6440e-136">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="6440e-137">La aserción da error si las variables hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="6440e-137">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="6440e-138">Comprueba si una condición es `false`.</span><span class="sxs-lookup"><span data-stu-id="6440e-138">Verifies that a condition is `false`.</span></span> <span data-ttu-id="6440e-139">La aserción produce un error si la condición es `true`.</span><span class="sxs-lookup"><span data-stu-id="6440e-139">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="6440e-140">Comprueba que un objeto no es `null`.</span><span class="sxs-lookup"><span data-stu-id="6440e-140">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="6440e-141">La aserción da error si el objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="6440e-141">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="6440e-142">También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> en un método de prueba para indicar el tipo de excepción que se espera que produzca.</span><span class="sxs-lookup"><span data-stu-id="6440e-142">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="6440e-143">La prueba dará error si no se inicia la excepción especificada.</span><span class="sxs-lookup"><span data-stu-id="6440e-143">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="6440e-144">Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6440e-144">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="6440e-145">Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6440e-145">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6440e-146">Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6440e-146">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="6440e-147">Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6440e-147">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="6440e-148">Dado que el método de biblioteca controla cadenas, también se recomienda asegurarse de que controla correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty) y una cadena `null`.</span><span class="sxs-lookup"><span data-stu-id="6440e-148">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="6440e-149">Una cadena vacía es aquella que no tiene ningún carácter y cuyo valor de <xref:System.String.Length> es 0.</span><span class="sxs-lookup"><span data-stu-id="6440e-149">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="6440e-150">Una cadena `null` es aquella que no se ha inicializado.</span><span class="sxs-lookup"><span data-stu-id="6440e-150">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="6440e-151">Se puede llamar a `StartsWithUpper` directamente como un método estático y pasar un argumento <xref:System.String> único.</span><span class="sxs-lookup"><span data-stu-id="6440e-151">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="6440e-152">También puede llamar a `StartsWithUpper` como método de extensión en una variable de `string` asignada a `null`.</span><span class="sxs-lookup"><span data-stu-id="6440e-152">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="6440e-153">Definirá tres métodos, cada uno de los cuales llama a un método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> para cada elemento de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6440e-153">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="6440e-154">Llamará a una sobrecarga de método que le permite especificar que se muestre un mensaje de error en caso de error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="6440e-154">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="6440e-155">El mensaje identifica la cadena que causó el error.</span><span class="sxs-lookup"><span data-stu-id="6440e-155">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="6440e-156">Para crear los métodos de prueba:</span><span class="sxs-lookup"><span data-stu-id="6440e-156">To create the test methods:</span></span>

1. <span data-ttu-id="6440e-157">Abra *StringLibraryTest/UnitTest1.cs* y reemplace todo el código por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="6440e-157">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="6440e-158">La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C).</span><span class="sxs-lookup"><span data-stu-id="6440e-158">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="6440e-159">La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).</span><span class="sxs-lookup"><span data-stu-id="6440e-159">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="6440e-160">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="6440e-160">Save your changes.</span></span>

1. <span data-ttu-id="6440e-161">Ejecute las pruebas:</span><span class="sxs-lookup"><span data-stu-id="6440e-161">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="6440e-162">en la salida del terminal se indica que se han superado todas las pruebas.</span><span class="sxs-lookup"><span data-stu-id="6440e-162">The terminal output shows that all tests passed.</span></span>

   ```output
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
    Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="6440e-163">Administración de errores de prueba</span><span class="sxs-lookup"><span data-stu-id="6440e-163">Handle test failures</span></span>

<span data-ttu-id="6440e-164">Si está realizando el desarrollo controlado por pruebas (TDD), escribirá las pruebas, y estas generarán un error cuando las ejecute por primera vez.</span><span class="sxs-lookup"><span data-stu-id="6440e-164">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="6440e-165">Después, agregará un código a la aplicación para que la prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="6440e-165">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="6440e-166">En este tutorial, ha creado la prueba después de escribir el código de la aplicación que valida, por lo que no ha podido comprobar si la prueba genera un error.</span><span class="sxs-lookup"><span data-stu-id="6440e-166">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="6440e-167">Para asegurarse de que una prueba genera un error cuando espera que lo haga, agregue un valor no válido a la entrada de prueba.</span><span class="sxs-lookup"><span data-stu-id="6440e-167">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="6440e-168">Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="6440e-168">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="6440e-169">Ejecute las pruebas:</span><span class="sxs-lookup"><span data-stu-id="6440e-169">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="6440e-170">en la salida del terminal se indica que una de las pruebas no se supera y se proporciona un mensaje de error al respecto: "Error de Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="6440e-170">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="6440e-171">Se esperaba para "Error": false; real: True".</span><span class="sxs-lookup"><span data-stu-id="6440e-171">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="6440e-172">Debido al error, no se probaron todas las cadenas de la matriz después de "Error".</span><span class="sxs-lookup"><span data-stu-id="6440e-172">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   ```output
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.
     X TestDoesNotStartWithUpper [283ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
        at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper() in C:\
   Projects\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Test Run Failed.
   Total tests: 3
        Passed: 2
        Failed: 1
    Total time: 1.7825 Seconds
   ```

1. <span data-ttu-id="6440e-173">Quite la cadena "Error" que agregó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="6440e-173">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="6440e-174">Vuelva a ejecutar la prueba y se superarán las pruebas.</span><span class="sxs-lookup"><span data-stu-id="6440e-174">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="6440e-175">Prueba de la versión de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="6440e-175">Test the Release version of the library</span></span>

<span data-ttu-id="6440e-176">Ahora que se han superado todas las pruebas al ejecutar la versión de depuración de la biblioteca, ejecute las pruebas una vez más con la versión de lanzamiento de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6440e-176">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="6440e-177">Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.</span><span class="sxs-lookup"><span data-stu-id="6440e-177">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="6440e-178">Ejecute las pruebas con la configuración de compilación Versión:</span><span class="sxs-lookup"><span data-stu-id="6440e-178">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="6440e-179">Las pruebas se superan.</span><span class="sxs-lookup"><span data-stu-id="6440e-179">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="6440e-180">Depuración de pruebas</span><span class="sxs-lookup"><span data-stu-id="6440e-180">Debug tests</span></span>

<span data-ttu-id="6440e-181">Si usa Visual Studio Code como IDE, puede emplear el mismo proceso que se muestra en [Tutorial: Depuración de una aplicación de consola de .NET Core con Visual Studio Code](debugging-with-visual-studio-code.md) para depurar código mediante el proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="6440e-181">If you're using Visual Studio Code as your IDE, you can use the same process shown in [Debug a .NET Core console application using Visual Studio Code](debugging-with-visual-studio-code.md) to debug code using your unit test project.</span></span> <span data-ttu-id="6440e-182">En lugar de iniciar el proyecto de aplicación *Showcase*, abra *StringLibraryTest/UnitTest1.cs* y seleccione **Ejecutar todas las pruebas** entre las líneas 7 y 8.</span><span class="sxs-lookup"><span data-stu-id="6440e-182">Instead of starting the *ShowCase* app project, open *StringLibraryTest/UnitTest1.cs*, and select **Run All Tests** between lines 7 and 8.</span></span> <span data-ttu-id="6440e-183">Si no puede encontrarlo, presione <kbd>Ctrl</kbd>+<kbd>Mayús</kbd>+<kbd>P</kbd> para abrir la paleta de comandos y escriba **Recargar ventana**.</span><span class="sxs-lookup"><span data-stu-id="6440e-183">If you're unable to find it, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the command palette and enter **Reload Window**.</span></span>

<span data-ttu-id="6440e-184">Visual Studio Code inicia el proyecto de prueba con el depurador asociado.</span><span class="sxs-lookup"><span data-stu-id="6440e-184">Visual Studio Code starts the test project with the debugger attached.</span></span> <span data-ttu-id="6440e-185">La ejecución se detendrá en cualquier punto de interrupción que haya agregado al proyecto de prueba o al código de la biblioteca subyacente.</span><span class="sxs-lookup"><span data-stu-id="6440e-185">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6440e-186">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6440e-186">Additional resources</span></span>

* [<span data-ttu-id="6440e-187">Pruebas unitarias en .NET Core y .NET Standard</span><span class="sxs-lookup"><span data-stu-id="6440e-187">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="6440e-188">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6440e-188">Next steps</span></span>

<span data-ttu-id="6440e-189">En este tutorial, ha realizado una prueba unitaria de una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="6440e-189">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="6440e-190">Puede poner la biblioteca a disposición de otros usuarios si la publica en [NuGet](https://nuget.org) como un paquete.</span><span class="sxs-lookup"><span data-stu-id="6440e-190">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="6440e-191">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="6440e-191">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6440e-192">Creación y publicación de un paquete con la CLI de dotnet</span><span class="sxs-lookup"><span data-stu-id="6440e-192">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="6440e-193">Si publica una biblioteca como un paquete NuGet, otros usuarios pueden instalarla y usarla.</span><span class="sxs-lookup"><span data-stu-id="6440e-193">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="6440e-194">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="6440e-194">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6440e-195">Instalar y usar un paquete con la CLI de dotnet</span><span class="sxs-lookup"><span data-stu-id="6440e-195">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="6440e-196">No es necesario distribuir una biblioteca como un paquete.</span><span class="sxs-lookup"><span data-stu-id="6440e-196">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="6440e-197">Se puede agrupar con una aplicación de consola que la use.</span><span class="sxs-lookup"><span data-stu-id="6440e-197">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="6440e-198">Para aprender a publicar una aplicación de consola, vea el tutorial anterior de esta serie:</span><span class="sxs-lookup"><span data-stu-id="6440e-198">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6440e-199">Publicación de una aplicación de consola de .NET Core con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6440e-199">Publish a .NET Core console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
