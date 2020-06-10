---
title: Prueba de una biblioteca de clases .NET Standard con .NET Core en Visual Studio
description: Cree un proyecto de prueba unitaria para la biblioteca de clases .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 48ada77b8422030fd93aa29df1df50a3ae5104fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283512"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="92071-104">Tutorial: Prueba de una biblioteca .NET Standard con .NET Core en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92071-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="92071-105">En este tutorial se muestra cómo automatizar las pruebas unitarias mediante la adición de un proyecto de prueba a una solución.</span><span class="sxs-lookup"><span data-stu-id="92071-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92071-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="92071-106">Prerequisites</span></span>

- <span data-ttu-id="92071-107">Este tutorial funciona con la solución que se crea en [Creación de una biblioteca de .NET Standard en Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="92071-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="92071-108">Crear un proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="92071-108">Create a unit test project</span></span>

1. <span data-ttu-id="92071-109">Abra la solución `ClassLibraryProjects` que creó en [Creación de una biblioteca de .NET Standard en Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="92071-109">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="92071-110">Agregue un nuevo proyecto de prueba unitaria denominado "StringLibraryTest" a la solución.</span><span class="sxs-lookup"><span data-stu-id="92071-110">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="92071-111">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="92071-111">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="92071-112">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **mstest**.</span><span class="sxs-lookup"><span data-stu-id="92071-112">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="92071-113">En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**.</span><span class="sxs-lookup"><span data-stu-id="92071-113">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="92071-114">Elija la plantilla **MSTest Test Project (.NET Core)** [Proyecto de prueba de MSTest (.NET Core)] y, luego, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="92071-114">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="92071-115">En la página **Configurar el nuevo proyecto**, escriba **StringLibraryTest** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="92071-115">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="92071-116">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="92071-116">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92071-117">MSTest es uno de los tres marcos de pruebas entre los que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="92071-117">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="92071-118">Los otros son xUnit y nUnit.</span><span class="sxs-lookup"><span data-stu-id="92071-118">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="92071-119">Visual Studio crea el proyecto y abre el archivo de clase en la ventana de código con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="92071-119">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="92071-120">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="92071-120">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   <span data-ttu-id="92071-121">El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="92071-121">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="92071-122">Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="92071-122">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="92071-123">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="92071-123">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="92071-124">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> para definir `TestMethod1` en C# o `TestSub` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="92071-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="92071-125">Cada método etiquetado con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) en una clase de prueba etiquetada con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) se ejecuta automáticamente cuando se ejecuta la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="92071-125">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="92071-126">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia de proyecto** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="92071-126">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="92071-127">En el cuadro de diálogo **Administrador de referencias**, expanda el nodo **Proyectos** y active la casilla junto a **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="92071-127">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="92071-128">Al agregar una referencia al ensamblado `StringLibrary`, el compilador puede encontrar métodos **StringLibrary** al compilar el proyecto **StringLibraryTest**.</span><span class="sxs-lookup"><span data-stu-id="92071-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="92071-129">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="92071-129">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="92071-130">Adición y ejecución de métodos de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="92071-130">Add and run unit test methods</span></span>

<span data-ttu-id="92071-131">Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase que está marcada con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="92071-131">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="92071-132">Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="92071-132">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="92071-133">Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="92071-133">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="92071-134">Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba.</span><span class="sxs-lookup"><span data-stu-id="92071-134">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="92071-135">Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="92071-135">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="92071-136">Métodos de aserción</span><span class="sxs-lookup"><span data-stu-id="92071-136">Assert methods</span></span>     | <span data-ttu-id="92071-137">Función</span><span class="sxs-lookup"><span data-stu-id="92071-137">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="92071-138">Comprueba que dos valores u objetos son iguales.</span><span class="sxs-lookup"><span data-stu-id="92071-138">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="92071-139">La aserción da error si los valores o los objetos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="92071-139">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="92071-140">Comprueba que dos variables de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="92071-140">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="92071-141">La aserción da error si las variables hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="92071-141">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="92071-142">Comprueba si una condición es `false`.</span><span class="sxs-lookup"><span data-stu-id="92071-142">Verifies that a condition is `false`.</span></span> <span data-ttu-id="92071-143">La aserción produce un error si la condición es `true`.</span><span class="sxs-lookup"><span data-stu-id="92071-143">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="92071-144">Comprueba que un objeto no es `null`.</span><span class="sxs-lookup"><span data-stu-id="92071-144">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="92071-145">La aserción da error si el objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="92071-145">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="92071-146">También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> en un método de prueba para indicar el tipo de excepción que se espera que produzca.</span><span class="sxs-lookup"><span data-stu-id="92071-146">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="92071-147">La prueba dará error si no se inicia la excepción especificada.</span><span class="sxs-lookup"><span data-stu-id="92071-147">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="92071-148">Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="92071-148">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="92071-149">Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="92071-149">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="92071-150">Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="92071-150">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="92071-151">Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="92071-151">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="92071-152">Dado que el método de biblioteca administra cadenas, quiere asegurarse también de que administra correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo <xref:System.String.Length> sea 0, y una cadena `null` que no se haya inicializado.</span><span class="sxs-lookup"><span data-stu-id="92071-152">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="92071-153">Si `StartsWithUpper` se llama como un método de extensión en una instancia <xref:System.String>, no se puede pasar una cadena `null`.</span><span class="sxs-lookup"><span data-stu-id="92071-153">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="92071-154">En cambio, también se puede llamar directamente como un método estático y pasarse como un argumento <xref:System.String> único.</span><span class="sxs-lookup"><span data-stu-id="92071-154">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="92071-155">Definirá tres métodos, cada uno de los cuales llama a su método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> repetidamente para cada elemento de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="92071-155">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="92071-156">Dado que el método de prueba produce un error tan pronto como encuentra el primer error, llamará a una sobrecarga de método que le permita pasar una cadena que indique el valor de cadena usado en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="92071-156">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="92071-157">Para crear los métodos de prueba:</span><span class="sxs-lookup"><span data-stu-id="92071-157">To create the test methods:</span></span>

1. <span data-ttu-id="92071-158">En la ventana de código *UnitTest1.cs* o *UnitTest1.vb*, reemplace el código por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="92071-158">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="92071-159">La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C).</span><span class="sxs-lookup"><span data-stu-id="92071-159">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="92071-160">La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).</span><span class="sxs-lookup"><span data-stu-id="92071-160">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="92071-161">En la barra de menús, seleccione **Archivo** > **Guardar UnitTest1.cs como** o **Archivo** > **Guardar UnitTest1.vb como**.</span><span class="sxs-lookup"><span data-stu-id="92071-161">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="92071-162">En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y seleccione **Guardar con codificación**.</span><span class="sxs-lookup"><span data-stu-id="92071-162">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92071-163">![Cuadro de diálogo Guardar archivo como de Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="92071-163">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="92071-164">En el cuadro de diálogo **Confirmar guardar como**, seleccione el botón **Sí** para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="92071-164">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="92071-165">En el cuadro de diálogo **Opciones avanzadas para guardar**, seleccione **Unicode (UTF-8 con firma) - Página de códigos 65001** desde la lista desplegable **Codificación** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="92071-165">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92071-166">![Cuadro de diálogo Opciones avanzadas para guardar de Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="92071-166">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="92071-167">Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII.</span><span class="sxs-lookup"><span data-stu-id="92071-167">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="92071-168">Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán correctos.</span><span class="sxs-lookup"><span data-stu-id="92071-168">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="92071-169">En la barra de menús, seleccione **Prueba** > **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="92071-169">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="92071-170">Si no se abre la ventana **Explorador de pruebas**, ábrala mediante **Prueba** > **Explorador de pruebas**.</span><span class="sxs-lookup"><span data-stu-id="92071-170">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="92071-171">Las tres pruebas se muestran en la sección **Pruebas superadas** y en la sección **Resumen** se informa del resultado de la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="92071-171">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92071-172">![Ventana Explorador de pruebas con pruebas superadas](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="92071-172">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="92071-173">Administración de errores de prueba</span><span class="sxs-lookup"><span data-stu-id="92071-173">Handle test failures</span></span>

<span data-ttu-id="92071-174">Si está realizando el desarrollo controlado por pruebas (TDD), escribirá las pruebas y estas generarán un error cuando las ejecute por primera vez.</span><span class="sxs-lookup"><span data-stu-id="92071-174">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="92071-175">Después, agregará un código a la aplicación para que la prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="92071-175">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="92071-176">En este caso, ha creado la prueba después de escribir el código de la aplicación que valida, por lo que no ha podido comprobar si la prueba genera un error.</span><span class="sxs-lookup"><span data-stu-id="92071-176">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="92071-177">Para asegurarse de que una prueba genera un error cuando quiere que lo haga, agregue un valor no válido a la entrada de prueba.</span><span class="sxs-lookup"><span data-stu-id="92071-177">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="92071-178">Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="92071-178">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="92071-179">No necesita guardar el archivo porque Visual Studio guarda automáticamente archivos abiertos cuando se crea una solución para ejecutar pruebas.</span><span class="sxs-lookup"><span data-stu-id="92071-179">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="92071-180">Ejecute la prueba seleccionando **Prueba** > **Ejecutar todas las pruebas** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="92071-180">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="92071-181">En la ventana **Explorador de pruebas** se indica que dos pruebas se han realizado correctamente y que una ha finalizado con errores.</span><span class="sxs-lookup"><span data-stu-id="92071-181">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92071-182">![Ventana Explorador de pruebas con pruebas no superadas](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="92071-182">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="92071-183">Seleccione la prueba con errores, `TestDoesNotStartWith`.</span><span class="sxs-lookup"><span data-stu-id="92071-183">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="92071-184">En la ventana **Explorador de pruebas** se muestra el mensaje generado por la instrucción Assert: "Error de Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="92071-184">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="92071-185">Se esperaba para "Error": false; real: True".</span><span class="sxs-lookup"><span data-stu-id="92071-185">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="92071-186">Debido al error, no se probaron todas las cadenas de la matriz después de "Error".</span><span class="sxs-lookup"><span data-stu-id="92071-186">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92071-187">![Ventana del Explorador de pruebas que muestra el error de aserción IsFalse](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="92071-187">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="92071-188">Deshaga la modificación que hizo en el paso 1 y quite la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="92071-188">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="92071-189">Vuelva a ejecutar la prueba y se superarán las pruebas.</span><span class="sxs-lookup"><span data-stu-id="92071-189">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="92071-190">Prueba de la versión de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="92071-190">Test the Release version of the library</span></span>

<span data-ttu-id="92071-191">Ahora que se han superado todas las pruebas al ejecutar la versión de depuración de la biblioteca, ejecute las pruebas una vez más en la versión de lanzamiento de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="92071-191">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="92071-192">Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.</span><span class="sxs-lookup"><span data-stu-id="92071-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="92071-193">Para probar la compilación de versión:</span><span class="sxs-lookup"><span data-stu-id="92071-193">To test the Release build:</span></span>

1. <span data-ttu-id="92071-194">En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="92071-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92071-195">![Barra de herramientas de Visual Studio con la compilación de versión resaltada](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="92071-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="92071-196">En el  **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **StringLibrary** y seleccione **Compilar** desde el menú contextual para volver a compilar la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="92071-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92071-197">![Menú contextual de StringLibrary con el comando Compilar](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="92071-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="92071-198">Ejecute las pruebas unitarias mediante **Ejecutar prueba** > **Todas las pruebas** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="92071-198">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="92071-199">Las pruebas se superan.</span><span class="sxs-lookup"><span data-stu-id="92071-199">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92071-200">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="92071-200">Additional resources</span></span>

- [<span data-ttu-id="92071-201">Conceptos básicos de las pruebas unitarias en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92071-201">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)

## <a name="next-steps"></a><span data-ttu-id="92071-202">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="92071-202">Next steps</span></span>

<span data-ttu-id="92071-203">En este tutorial, ha realizado una prueba unitaria de una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="92071-203">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="92071-204">Puede poner la biblioteca a disposición de otros usuarios si la publica en [NuGet](https://nuget.org) como un paquete.</span><span class="sxs-lookup"><span data-stu-id="92071-204">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="92071-205">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="92071-205">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92071-206">Creación y publicación de un paquete NuGet con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92071-206">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="92071-207">Si publica una biblioteca como un paquete NuGet, otros usuarios pueden instalarla y usarla.</span><span class="sxs-lookup"><span data-stu-id="92071-207">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="92071-208">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="92071-208">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92071-209">Instalación y uso de un paquete en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92071-209">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="92071-210">No es necesario distribuir una biblioteca como un paquete.</span><span class="sxs-lookup"><span data-stu-id="92071-210">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="92071-211">Se puede agrupar con una aplicación de consola que la use.</span><span class="sxs-lookup"><span data-stu-id="92071-211">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="92071-212">Para aprender a publicar una aplicación de consola, vea el tutorial anterior de esta serie:</span><span class="sxs-lookup"><span data-stu-id="92071-212">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92071-213">Publicación de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92071-213">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
