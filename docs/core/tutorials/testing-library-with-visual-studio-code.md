---
title: Prueba de una biblioteca de clases .NET Standard con .NET Core en Visual Studio Code
description: Cree un proyecto de prueba unitaria para una biblioteca de clases de .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
ms.date: 05/29/2020
ms.openlocfilehash: be227453bd441028cc6ce348c00fad944140238f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292166"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio-code"></a><span data-ttu-id="a9f6e-104">Tutorial: Prueba de una biblioteca .NET Standard con .NET Core en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9f6e-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>

<span data-ttu-id="a9f6e-105">En este tutorial se muestra cómo automatizar las pruebas unitarias mediante la adición de un proyecto de prueba a una solución.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9f6e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a9f6e-106">Prerequisites</span></span>

- <span data-ttu-id="a9f6e-107">Este tutorial funciona con la solución que se crea en [Creación de una biblioteca de .NET Standard en Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="a9f6e-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="a9f6e-108">Crear un proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="a9f6e-108">Create a unit test project</span></span>

1. <span data-ttu-id="a9f6e-109">Abra Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-109">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="a9f6e-110">Abra la solución `ClassLibraryProjects` que creó en [Creación de una biblioteca de .NET Standard en Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a9f6e-110">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="a9f6e-111">Cree un proyecto de prueba unitaria denominado "StringLibraryTest".</span><span class="sxs-lookup"><span data-stu-id="a9f6e-111">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="a9f6e-112">La plantilla de proyecto crea un archivo UnitTest1.cs con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-112">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="a9f6e-113">El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-113">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="a9f6e-114">Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-114">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="a9f6e-115">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-115">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="a9f6e-116">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> para definir `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-116">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="a9f6e-117">Cada método etiquetado con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) en una clase de prueba etiquetada con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) se ejecuta automáticamente cuando se ejecuta la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-117">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a9f6e-118">MSTest es uno de los tres marcos de pruebas entre los que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-118">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="a9f6e-119">Los otros son xUnit y nUnit.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-119">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="a9f6e-120">Agregue el proyecto de prueba a la solución:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-120">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

1. <span data-ttu-id="a9f6e-121">Cree una referencia de proyecto al proyecto de biblioteca de clases; para ello, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-121">Create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="a9f6e-122">Adición y ejecución de métodos de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="a9f6e-122">Add and run unit test methods</span></span>

<span data-ttu-id="a9f6e-123">Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase que está marcada con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-123">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="a9f6e-124">Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-124">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="a9f6e-125">Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-125">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="a9f6e-126">Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-126">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="a9f6e-127">Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-127">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="a9f6e-128">Métodos de aserción</span><span class="sxs-lookup"><span data-stu-id="a9f6e-128">Assert methods</span></span>     | <span data-ttu-id="a9f6e-129">Función</span><span class="sxs-lookup"><span data-stu-id="a9f6e-129">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="a9f6e-130">Comprueba que dos valores u objetos son iguales.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-130">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="a9f6e-131">La aserción da error si los valores o los objetos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-131">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="a9f6e-132">Comprueba que dos variables de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-132">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="a9f6e-133">La aserción da error si las variables hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-133">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="a9f6e-134">Comprueba si una condición es `false`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-134">Verifies that a condition is `false`.</span></span> <span data-ttu-id="a9f6e-135">La aserción produce un error si la condición es `true`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-135">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="a9f6e-136">Comprueba que un objeto no es `null`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-136">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="a9f6e-137">La aserción da error si el objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-137">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="a9f6e-138">También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> en un método de prueba para indicar el tipo de excepción que se espera que produzca.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-138">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="a9f6e-139">La prueba dará error si no se inicia la excepción especificada.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-139">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="a9f6e-140">Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-140">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="a9f6e-141">Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-141">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a9f6e-142">Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-142">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="a9f6e-143">Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-143">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a9f6e-144">Dado que el método de biblioteca controla cadenas, también se recomienda asegurarse de que controla correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty) y una cadena `null`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-144">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="a9f6e-145">Una cadena vacía es aquella que no tiene ningún carácter y cuyo valor de <xref:System.String.Length> es 0.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-145">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="a9f6e-146">Una cadena `null` es aquella que no se ha inicializado.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-146">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="a9f6e-147">Se puede llamar a `StartsWithUpper` directamente como un método estático y pasar un argumento <xref:System.String> único.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-147">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="a9f6e-148">También puede llamar a `StartsWithUpper` como método de extensión en una variable de `string` asignada a `null`.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-148">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="a9f6e-149">Definirá tres métodos, cada uno de los cuales llama a su método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> repetidamente para cada elemento de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-149">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="a9f6e-150">Dado que el método de prueba produce un error tan pronto como encuentra el primer error, llamará a una sobrecarga de método que le permita pasar una cadena que indique el valor de cadena usado en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-150">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="a9f6e-151">Para crear los métodos de prueba:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-151">To create the test methods:</span></span>

1. <span data-ttu-id="a9f6e-152">Abra *StringLibraryTest/UnitTest1.cs* y reemplace todo el código por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-152">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="a9f6e-153">La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C).</span><span class="sxs-lookup"><span data-stu-id="a9f6e-153">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="a9f6e-154">La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).</span><span class="sxs-lookup"><span data-stu-id="a9f6e-154">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="a9f6e-155">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-155">Save your changes.</span></span>

1. <span data-ttu-id="a9f6e-156">Ejecute las pruebas:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-156">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="a9f6e-157">en la salida del terminal se indica que se han superado todas las pruebas.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-157">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="a9f6e-158">Administración de errores de prueba</span><span class="sxs-lookup"><span data-stu-id="a9f6e-158">Handle test failures</span></span>

<span data-ttu-id="a9f6e-159">Si está realizando el desarrollo controlado por pruebas (TDD), escribirá las pruebas, y estas generarán un error cuando las ejecute por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-159">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="a9f6e-160">Después, agregará un código a la aplicación para que la prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-160">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="a9f6e-161">En este caso, ha creado la prueba después de escribir el código de la aplicación que valida, por lo que no ha podido comprobar si la prueba genera un error.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-161">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="a9f6e-162">Para asegurarse de que una prueba genera un error cuando espera que lo haga, agregue un valor no válido a la entrada de prueba.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-162">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="a9f6e-163">Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="a9f6e-163">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="a9f6e-164">Ejecute las pruebas:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-164">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="a9f6e-165">en la salida del terminal se indica que se produce un error en una prueba y se proporciona un mensaje de error para la prueba con errores.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-165">The terminal output shows that one test fails, and it provides an error message for the failed test.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.
     X TestDoesNotStartWithUpper [283ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
     at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper()
       in C:\Projects\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Test Run Failed.
   Total tests: 3
        Passed: 2
        Failed: 1
   Total time: 1.7825 Seconds
   ```

1. <span data-ttu-id="a9f6e-166">Deshaga la modificación que hizo en el paso 1 y quite la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="a9f6e-166">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="a9f6e-167">Vuelva a ejecutar la prueba y se superarán las pruebas.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-167">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="a9f6e-168">Prueba de la versión de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="a9f6e-168">Test the Release version of the library</span></span>

<span data-ttu-id="a9f6e-169">Ahora que se han superado todas las pruebas al ejecutar la versión de depuración de la biblioteca, ejecute las pruebas una vez más en la versión de lanzamiento de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-169">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="a9f6e-170">Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-170">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="a9f6e-171">Ejecute las pruebas con la configuración de compilación Versión:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-171">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="a9f6e-172">Las pruebas se superan.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-172">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9f6e-173">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a9f6e-173">Additional resources</span></span>

- [<span data-ttu-id="a9f6e-174">Pruebas unitarias en .NET Core y .NET Standard</span><span class="sxs-lookup"><span data-stu-id="a9f6e-174">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="a9f6e-175">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a9f6e-175">Next steps</span></span>

<span data-ttu-id="a9f6e-176">En este tutorial, ha realizado una prueba unitaria de una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-176">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="a9f6e-177">Puede poner la biblioteca a disposición de otros usuarios si la publica en [NuGet](https://nuget.org) como un paquete.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-177">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="a9f6e-178">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-178">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a9f6e-179">Creación y publicación de un paquete con la CLI de dotnet</span><span class="sxs-lookup"><span data-stu-id="a9f6e-179">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="a9f6e-180">Si publica una biblioteca como un paquete NuGet, otros usuarios pueden instalarla y usarla.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-180">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="a9f6e-181">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-181">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a9f6e-182">Instalar y usar un paquete con la CLI de dotnet</span><span class="sxs-lookup"><span data-stu-id="a9f6e-182">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="a9f6e-183">No es necesario distribuir una biblioteca como un paquete.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-183">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="a9f6e-184">Se puede agrupar con una aplicación de consola que la use.</span><span class="sxs-lookup"><span data-stu-id="a9f6e-184">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="a9f6e-185">Para aprender a publicar una aplicación de consola, vea el tutorial anterior de esta serie:</span><span class="sxs-lookup"><span data-stu-id="a9f6e-185">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a9f6e-186">Publicación de una aplicación de consola de .NET Core con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a9f6e-186">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
