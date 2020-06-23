---
title: Prueba de una biblioteca de clases .NET Standard con .NET Core mediante Visual Studio
description: Cree un proyecto de prueba unitaria para una biblioteca de clases de .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: f20b089fd22794d5aaeff34502e960fe41a565e1
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84700974"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="194c2-104">Tutorial: Prueba de una biblioteca de clases .NET Standard con .NET Core mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="194c2-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="194c2-105">En este tutorial se muestra cómo automatizar las pruebas unitarias mediante la adición de un proyecto de prueba a una solución.</span><span class="sxs-lookup"><span data-stu-id="194c2-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="194c2-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="194c2-106">Prerequisites</span></span>

- <span data-ttu-id="194c2-107">Este tutorial funciona con la solución que se crea en [Creación de una biblioteca de .NET Standard en Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="194c2-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="194c2-108">Crear un proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="194c2-108">Create a unit test project</span></span>

<span data-ttu-id="194c2-109">Las pruebas unitarias proporcionan pruebas de software automatizadas durante el desarrollo y la publicación.</span><span class="sxs-lookup"><span data-stu-id="194c2-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="194c2-110">[MSTest](https://github.com/Microsoft/testfx-docs) es uno de los tres marcos de pruebas que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="194c2-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="194c2-111">Los otros son [xUnit](https://xunit.net/) y [nUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="194c2-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="194c2-112">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="194c2-112">Start Visual Studio.</span></span>

1. <span data-ttu-id="194c2-113">Abra la solución `ClassLibraryProjects` que creó en [Creación de una biblioteca de .NET Standard en Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="194c2-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="194c2-114">Agregue un nuevo proyecto de prueba unitaria denominado "StringLibraryTest" a la solución.</span><span class="sxs-lookup"><span data-stu-id="194c2-114">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="194c2-115">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="194c2-115">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="194c2-116">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **mstest**.</span><span class="sxs-lookup"><span data-stu-id="194c2-116">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="194c2-117">En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**.</span><span class="sxs-lookup"><span data-stu-id="194c2-117">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="194c2-118">Elija la plantilla **MSTest Test Project (.NET Core)** [Proyecto de prueba de MSTest (.NET Core)] y, luego, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="194c2-118">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="194c2-119">En la página **Configurar el nuevo proyecto**, escriba **StringLibraryTest** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="194c2-119">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="194c2-120">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="194c2-120">Then choose **Create**.</span></span>

1. <span data-ttu-id="194c2-121">Visual Studio crea el proyecto y abre el archivo de clase en la ventana de código con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="194c2-121">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="194c2-122">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="194c2-122">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   <span data-ttu-id="194c2-123">El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="194c2-123">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="194c2-124">Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="194c2-124">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="194c2-125">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="194c2-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="194c2-126">Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> para definir `TestMethod1` en C# o `TestSub` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="194c2-126">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="194c2-127">Cada método etiquetado con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) en una clase de prueba etiquetada con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) se ejecuta automáticamente cuando se ejecuta la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="194c2-127">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="194c2-128">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="194c2-128">Add a project reference</span></span>

<span data-ttu-id="194c2-129">Para que el proyecto de prueba funcione con la clase `StringLibrary`, agregue una referencia del proyecto **StringLibraryTest** al proyecto `StringLibrary`.</span><span class="sxs-lookup"><span data-stu-id="194c2-129">For the test project to work with the `StringLibrary` class, add a reference in the **StringLibraryTest** project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="194c2-130">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia de proyecto** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="194c2-130">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="194c2-131">En el cuadro de diálogo **Administrador de referencias**, expanda el nodo **Proyectos** y active la casilla junto a **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="194c2-131">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="194c2-132">Al agregar una referencia al ensamblado `StringLibrary`, el compilador puede encontrar métodos **StringLibrary** al compilar el proyecto **StringLibraryTest**.</span><span class="sxs-lookup"><span data-stu-id="194c2-132">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="194c2-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="194c2-133">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="194c2-134">Adición y ejecución de métodos de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="194c2-134">Add and run unit test methods</span></span>

<span data-ttu-id="194c2-135">Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase que está marcada con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="194c2-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="194c2-136">Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="194c2-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="194c2-137">Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="194c2-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="194c2-138">Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba.</span><span class="sxs-lookup"><span data-stu-id="194c2-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="194c2-139">Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="194c2-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="194c2-140">Métodos de aserción</span><span class="sxs-lookup"><span data-stu-id="194c2-140">Assert methods</span></span>     | <span data-ttu-id="194c2-141">Función</span><span class="sxs-lookup"><span data-stu-id="194c2-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="194c2-142">Comprueba que dos valores u objetos son iguales.</span><span class="sxs-lookup"><span data-stu-id="194c2-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="194c2-143">La aserción da error si los valores o los objetos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="194c2-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="194c2-144">Comprueba que dos variables de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="194c2-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="194c2-145">La aserción da error si las variables hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="194c2-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="194c2-146">Comprueba si una condición es `false`.</span><span class="sxs-lookup"><span data-stu-id="194c2-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="194c2-147">La aserción produce un error si la condición es `true`.</span><span class="sxs-lookup"><span data-stu-id="194c2-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="194c2-148">Comprueba que un objeto no es `null`.</span><span class="sxs-lookup"><span data-stu-id="194c2-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="194c2-149">La aserción da error si el objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="194c2-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="194c2-150">También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> en un método de prueba para indicar el tipo de excepción que se espera que produzca.</span><span class="sxs-lookup"><span data-stu-id="194c2-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="194c2-151">La prueba dará error si no se inicia la excepción especificada.</span><span class="sxs-lookup"><span data-stu-id="194c2-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="194c2-152">Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="194c2-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="194c2-153">Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="194c2-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="194c2-154">Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="194c2-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="194c2-155">Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="194c2-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="194c2-156">Dado que el método de biblioteca administra cadenas, quiere asegurarse también de que administra correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo <xref:System.String.Length> sea 0, y una cadena `null` que no se haya inicializado.</span><span class="sxs-lookup"><span data-stu-id="194c2-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="194c2-157">Se puede llamar a `StartsWithUpper` directamente como un método estático y pasar un argumento <xref:System.String> único.</span><span class="sxs-lookup"><span data-stu-id="194c2-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="194c2-158">También puede llamar a `StartsWithUpper` como método de extensión en una variable de `string` asignada a `null`.</span><span class="sxs-lookup"><span data-stu-id="194c2-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="194c2-159">Definirá tres métodos, cada uno de los cuales llama a un método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> para cada elemento de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="194c2-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="194c2-160">Llamará a una sobrecarga de método que le permite especificar que se muestre un mensaje de error en caso de error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="194c2-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="194c2-161">El mensaje identifica la cadena que causó el error.</span><span class="sxs-lookup"><span data-stu-id="194c2-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="194c2-162">Para crear los métodos de prueba:</span><span class="sxs-lookup"><span data-stu-id="194c2-162">To create the test methods:</span></span>

1. <span data-ttu-id="194c2-163">En la ventana de código *UnitTest1.cs* o *UnitTest1.vb*, reemplace el código por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="194c2-163">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="194c2-164">La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C).</span><span class="sxs-lookup"><span data-stu-id="194c2-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="194c2-165">La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).</span><span class="sxs-lookup"><span data-stu-id="194c2-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="194c2-166">En la barra de menús, seleccione **Archivo** > **Guardar UnitTest1.cs como** o **Archivo** > **Guardar UnitTest1.vb como**.</span><span class="sxs-lookup"><span data-stu-id="194c2-166">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="194c2-167">En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y seleccione **Guardar con codificación**.</span><span class="sxs-lookup"><span data-stu-id="194c2-167">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="194c2-168">![Cuadro de diálogo Guardar archivo como de Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="194c2-168">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="194c2-169">En el cuadro de diálogo **Confirmar guardar como**, seleccione el botón **Sí** para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="194c2-169">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="194c2-170">En el cuadro de diálogo **Opciones avanzadas para guardar**, seleccione **Unicode (UTF-8 con firma) - Página de códigos 65001** desde la lista desplegable **Codificación** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="194c2-170">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="194c2-171">![Cuadro de diálogo Opciones avanzadas para guardar de Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="194c2-171">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="194c2-172">Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII.</span><span class="sxs-lookup"><span data-stu-id="194c2-172">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="194c2-173">Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán correctos.</span><span class="sxs-lookup"><span data-stu-id="194c2-173">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="194c2-174">En la barra de menús, seleccione **Prueba** > **Ejecutar todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="194c2-174">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="194c2-175">Si no se abre la ventana **Explorador de pruebas**, ábrala mediante **Prueba** > **Explorador de pruebas**.</span><span class="sxs-lookup"><span data-stu-id="194c2-175">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="194c2-176">Las tres pruebas se muestran en la sección **Pruebas superadas** y en la sección **Resumen** se informa del resultado de la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="194c2-176">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="194c2-177">![Ventana Explorador de pruebas con pruebas superadas](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="194c2-177">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="194c2-178">Administración de errores de prueba</span><span class="sxs-lookup"><span data-stu-id="194c2-178">Handle test failures</span></span>

<span data-ttu-id="194c2-179">Si está realizando el desarrollo controlado por pruebas (TDD), escribirá las pruebas, y estas generarán un error cuando las ejecute por primera vez.</span><span class="sxs-lookup"><span data-stu-id="194c2-179">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="194c2-180">Después, agregará un código a la aplicación para que la prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="194c2-180">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="194c2-181">En este tutorial, ha creado la prueba después de escribir el código de la aplicación que valida, por lo que no ha podido comprobar si la prueba genera un error.</span><span class="sxs-lookup"><span data-stu-id="194c2-181">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="194c2-182">Para asegurarse de que una prueba genera un error cuando espera que lo haga, agregue un valor no válido a la entrada de prueba.</span><span class="sxs-lookup"><span data-stu-id="194c2-182">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="194c2-183">Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="194c2-183">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="194c2-184">No necesita guardar el archivo porque Visual Studio guarda automáticamente archivos abiertos cuando se crea una solución para ejecutar pruebas.</span><span class="sxs-lookup"><span data-stu-id="194c2-184">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="194c2-185">Ejecute la prueba seleccionando **Prueba** > **Ejecutar todas las pruebas** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="194c2-185">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="194c2-186">En la ventana **Explorador de pruebas** se indica que dos pruebas se han realizado correctamente y que una ha finalizado con errores.</span><span class="sxs-lookup"><span data-stu-id="194c2-186">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="194c2-187">![Ventana Explorador de pruebas con pruebas no superadas](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="194c2-187">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="194c2-188">Seleccione la prueba con errores, `TestDoesNotStartWith`.</span><span class="sxs-lookup"><span data-stu-id="194c2-188">Select the failed test, `TestDoesNotStartWith`.</span></span>

   <span data-ttu-id="194c2-189">En la ventana **Explorador de pruebas** se muestra el mensaje generado por la instrucción Assert: "Error de Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="194c2-189">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="194c2-190">Se esperaba para "Error": false; real: True".</span><span class="sxs-lookup"><span data-stu-id="194c2-190">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="194c2-191">Debido al error, no se probaron todas las cadenas de la matriz después de "Error".</span><span class="sxs-lookup"><span data-stu-id="194c2-191">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="194c2-192">![Ventana del Explorador de pruebas que muestra el error de aserción IsFalse](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="194c2-192">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="194c2-193">Quite la cadena "Error" que agregó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="194c2-193">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="194c2-194">Vuelva a ejecutar la prueba y se superarán las pruebas.</span><span class="sxs-lookup"><span data-stu-id="194c2-194">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="194c2-195">Prueba de la versión de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="194c2-195">Test the Release version of the library</span></span>

<span data-ttu-id="194c2-196">Ahora que se han superado todas las pruebas al ejecutar la versión de depuración de la biblioteca, ejecute las pruebas una vez más con la versión de lanzamiento de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="194c2-196">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="194c2-197">Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.</span><span class="sxs-lookup"><span data-stu-id="194c2-197">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="194c2-198">Para probar la compilación de versión:</span><span class="sxs-lookup"><span data-stu-id="194c2-198">To test the Release build:</span></span>

1. <span data-ttu-id="194c2-199">En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="194c2-199">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="194c2-200">![Barra de herramientas de Visual Studio con la compilación de versión resaltada](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="194c2-200">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="194c2-201">En el  **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **StringLibrary** y seleccione **Compilar** desde el menú contextual para volver a compilar la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="194c2-201">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="194c2-202">![Menú contextual de StringLibrary con el comando Compilar](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="194c2-202">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="194c2-203">Ejecute las pruebas unitarias mediante **Ejecutar prueba** > **Todas las pruebas** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="194c2-203">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="194c2-204">Las pruebas se superan.</span><span class="sxs-lookup"><span data-stu-id="194c2-204">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="194c2-205">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="194c2-205">Additional resources</span></span>

* [<span data-ttu-id="194c2-206">Conceptos básicos de las pruebas unitarias en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="194c2-206">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
* [<span data-ttu-id="194c2-207">Pruebas unitarias en .NET Core y .NET Standard</span><span class="sxs-lookup"><span data-stu-id="194c2-207">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="194c2-208">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="194c2-208">Next steps</span></span>

<span data-ttu-id="194c2-209">En este tutorial, ha realizado una prueba unitaria de una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="194c2-209">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="194c2-210">Puede poner la biblioteca a disposición de otros usuarios si la publica en [NuGet](https://nuget.org) como un paquete.</span><span class="sxs-lookup"><span data-stu-id="194c2-210">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="194c2-211">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="194c2-211">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="194c2-212">Creación y publicación de un paquete NuGet con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="194c2-212">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="194c2-213">Si publica una biblioteca como un paquete NuGet, otros usuarios pueden instalarla y usarla.</span><span class="sxs-lookup"><span data-stu-id="194c2-213">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="194c2-214">Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:</span><span class="sxs-lookup"><span data-stu-id="194c2-214">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="194c2-215">Instalación y uso de un paquete en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="194c2-215">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="194c2-216">No es necesario distribuir una biblioteca como un paquete.</span><span class="sxs-lookup"><span data-stu-id="194c2-216">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="194c2-217">Se puede agrupar con una aplicación de consola que la use.</span><span class="sxs-lookup"><span data-stu-id="194c2-217">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="194c2-218">Para aprender a publicar una aplicación de consola, vea el tutorial anterior de esta serie:</span><span class="sxs-lookup"><span data-stu-id="194c2-218">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="194c2-219">Publicación de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="194c2-219">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
