---
title: Prueba de una biblioteca de clases .NET Standard con .NET Core en Visual Studio
description: Cree un proyecto de prueba unitaria para la biblioteca de clases .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 307261088f5c7c69c0e69fbd6b99940c04842eec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156626"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="b1ac5-104">Prueba de una biblioteca .NET Standard con .NET Core en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b1ac5-104">Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="b1ac5-105">En [Creación de una biblioteca de .NET Standard con C# y el SDK de .NET Core en Visual Studio 2017](library-with-visual-studio.md), ha creado una biblioteca de clases simple que agrega un método de extensión a la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-105">In [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="b1ac5-106">Ahora, creará una prueba unitaria para asegurarse de que funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="b1ac5-107">Agregará su proyecto de prueba unitaria a la solución que ha creado en el artículo anterior.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="b1ac5-108">Crear un proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="b1ac5-108">Create a unit test project</span></span>

<span data-ttu-id="b1ac5-109">Para crear el proyecto de prueba unitaria, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-109">To create the unit test project, do the following:</span></span>

1. <span data-ttu-id="b1ac5-110">Abra la solución `ClassLibraryProjects` que creó en el artículo [Creación de una biblioteca de .NET Standard con C# y el SDK de .NET Core en Visual Studio 2017](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-110">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="b1ac5-111">Agregue un nuevo proyecto de prueba unitaria denominado "StringLibraryTest" a la solución.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-111">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="b1ac5-112">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-112">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="b1ac5-113">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **mstest**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-113">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="b1ac5-114">En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-114">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="b1ac5-115">Elija la plantilla **Proyecto de prueba de Ms (.NET Core)** y, luego, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-115">Choose the **MsTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="b1ac5-116">En la página **Configurar el nuevo proyecto**, escriba **StringLibraryTest** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-116">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="b1ac5-117">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-117">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1ac5-118">Además de MSTest, también puede crear proyectos de prueba xUnit y nUnit para .NET Core en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-118">In addition to an MSTest, you can also create xUnit and nUnit test projects for .NET Core in Visual Studio.</span></span>

1. <span data-ttu-id="b1ac5-119">Visual Studio crea el proyecto y abre el archivo de clase en la ventana de código con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-119">Visual Studio creates the project and opens the class file in the code window with the following code:</span></span>

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

   <span data-ttu-id="b1ac5-120">El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-120">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="b1ac5-121">Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="b1ac5-122">Aplica el atributo [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) a la clase `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-122">It applies the [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="b1ac5-123">Cada método de prueba en una clase de prueba etiquetada con el atributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) se ejecuta automáticamente cuando se ejecute la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-123">Each test method in a test class tagged with the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="b1ac5-124">Aplica el atributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) para definir `TestMethod1` en C# o `TestSub` en Visual Basic como método de prueba para la ejecución automática cuando se ejecuta la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-124">It applies the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="b1ac5-125">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia** del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-126">![Menú contextual de las dependencias de StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-126">![Context menu of StringLibraryTest dependencies](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span></span>

1. <span data-ttu-id="b1ac5-127">En el cuadro de diálogo **Administrador de referencias**, expanda el nodo **Proyectos** y marque la casilla junto a **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="b1ac5-128">Agregar una referencia al ensamblado `StringLibrary` permite al compilador buscar métodos **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="b1ac5-129">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-129">Select the **OK** button.</span></span> <span data-ttu-id="b1ac5-130">Se agrega una referencia a su proyecto de biblioteca de clases, `StringLibrary`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-130">A reference is added to your class library project, `StringLibrary`.</span></span>

   ![Cuadro de diálogo Administrador de referencias en Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="b1ac5-132">Adición y ejecución de métodos de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="b1ac5-132">Add and run unit test methods</span></span>

<span data-ttu-id="b1ac5-133">Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase de prueba unitaria; la clase a la que se le aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-133">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="b1ac5-134">Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-134">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="b1ac5-135">Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-135">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="b1ac5-136">Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-136">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="b1ac5-137">Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-137">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="b1ac5-138">Métodos de aserción</span><span class="sxs-lookup"><span data-stu-id="b1ac5-138">Assert methods</span></span>     | <span data-ttu-id="b1ac5-139">Función</span><span class="sxs-lookup"><span data-stu-id="b1ac5-139">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="b1ac5-140">Comprueba que dos valores u objetos son iguales.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-140">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="b1ac5-141">La aserción da error si los valores o los objetos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-141">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="b1ac5-142">Comprueba que dos variables de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-142">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="b1ac5-143">La aserción da error si las variables hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-143">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="b1ac5-144">Comprueba si una condición es `false`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-144">Verifies that a condition is `false`.</span></span> <span data-ttu-id="b1ac5-145">La aserción produce un error si la condición es `true`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-145">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="b1ac5-146">Comprueba que un objeto no es `null`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-146">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="b1ac5-147">La aserción da error si el objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-147">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="b1ac5-148">También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> en un método de prueba para indicar el tipo de excepción que se espera que produzca.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-148">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="b1ac5-149">La prueba dará error si no se inicia la excepción especificada.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-149">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="b1ac5-150">Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-150">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="b1ac5-151">Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-151">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="b1ac5-152">Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-152">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="b1ac5-153">Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-153">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="b1ac5-154">Dado que el método de biblioteca administra cadenas, quiere asegurarse también de que administra correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo <xref:System.String.Length> sea 0, y una cadena `null` que no se haya inicializado.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-154">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="b1ac5-155">Si `StartsWithUpper` se llama como un método de extensión en una instancia <xref:System.String>, no se puede pasar una cadena `null`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-155">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="b1ac5-156">En cambio, también se puede llamar directamente como un método estático y pasarse como un argumento <xref:System.String> único.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-156">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="b1ac5-157">Definirá tres métodos, cada uno de los cuales llama a su método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> repetidamente para cada elemento de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-157">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="b1ac5-158">Dado que el método de prueba produce un error tan pronto como encuentra el primer error, llamará a una sobrecarga de método que le permita pasar una cadena que indique el valor de cadena usado en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-158">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="b1ac5-159">Para crear los métodos de prueba:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-159">To create the test methods:</span></span>

1. <span data-ttu-id="b1ac5-160">En la ventana de código *UnitTest1.cs* o *UnitTest1.vb*, reemplace el código por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-160">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="b1ac5-161">La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-161">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="b1ac5-162">La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-162">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="b1ac5-163">En la barra de menús, seleccione **Archivo** > **Guardar UnitTest1.cs como** o **Archivo** > **Guardar UnitTest1.vb como**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-163">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="b1ac5-164">En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y seleccione **Guardar con codificación**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-164">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-165">![Cuadro de diálogo Guardar archivo como de Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-165">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="b1ac5-166">En el cuadro de diálogo **Confirmar guardar como**, seleccione el botón **Sí** para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-166">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="b1ac5-167">En el cuadro de diálogo **Opciones avanzadas para guardar**, seleccione **Unicode (UTF-8 con firma) - Página de códigos 65001** desde la lista desplegable **Codificación** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-167">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-168">![Cuadro de diálogo Opciones avanzadas para guardar de Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-168">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="b1ac5-169">Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-169">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="b1ac5-170">Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán correctos.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-170">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="b1ac5-171">En la barra de menús, seleccione **Prueba** > **Ejecutar** > **Todas las pruebas**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-171">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="b1ac5-172">Se abre la ventana del **Explorador de pruebas** y muestra que las pruebas se han ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-172">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="b1ac5-173">Las tres pruebas se muestran en la sección **Pruebas superadas** y en la sección **Resumen** se informa del resultado de la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-173">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-174">![Ventana Explorador de pruebas con pruebas superadas](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-174">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="b1ac5-175">Administración de errores de prueba</span><span class="sxs-lookup"><span data-stu-id="b1ac5-175">Handle test failures</span></span>

<span data-ttu-id="b1ac5-176">Su serie de pruebas no tuvo errores, pero vamos a cambiarla un poco para que uno de los métodos de prueba produzca un error:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-176">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="b1ac5-177">Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="b1ac5-177">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="b1ac5-178">No necesita guardar el archivo porque Visual Studio guarda automáticamente archivos abiertos cuando se crea una solución para ejecutar pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-178">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="b1ac5-179">Ejecute la prueba seleccionando **Prueba** > **Ejecutar** > **Todas las pruebas** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-179">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="b1ac5-180">En la ventana **Explorador de pruebas** se indica que dos pruebas se han realizado correctamente y que una ha finalizado con errores.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-180">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-181">![Ventana Explorador de pruebas con pruebas no superadas](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-181">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="b1ac5-182">Seleccione la prueba con errores, `TestDoesNotStartWith`.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-182">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="b1ac5-183">En la ventana **Explorador de pruebas** se muestra el mensaje generado por la aserción: "Error de Assert.IsFalse.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-183">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="b1ac5-184">Se esperaba para "Error": false; real: True".</span><span class="sxs-lookup"><span data-stu-id="b1ac5-184">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="b1ac5-185">Debido al error, no se probaron todas las cadenas de la matriz después de "Error".</span><span class="sxs-lookup"><span data-stu-id="b1ac5-185">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-186">![Ventana del Explorador de pruebas que muestra el error de aserción IsFalse](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-186">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="b1ac5-187">Deshaga la modificación que hizo en el paso 1 y quite la cadena "Error".</span><span class="sxs-lookup"><span data-stu-id="b1ac5-187">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="b1ac5-188">Vuelva a ejecutar la prueba y se superarán las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-188">Rerun the test and the tests will pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="b1ac5-189">Prueba de la versión de la biblioteca</span><span class="sxs-lookup"><span data-stu-id="b1ac5-189">Test the Release version of the library</span></span>

<span data-ttu-id="b1ac5-190">Ha estado ejecutando sus pruebas con la versión de depuración de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-190">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="b1ac5-191">Ahora que todas sus pruebas se han superado y que ha probado adecuadamente la biblioteca, debe ejecutar las pruebas un tiempo adicional con respecto a la compilación de versión de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-191">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="b1ac5-192">Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="b1ac5-193">Para probar la compilación de versión:</span><span class="sxs-lookup"><span data-stu-id="b1ac5-193">To test the Release build:</span></span>

1. <span data-ttu-id="b1ac5-194">En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-195">![Barra de herramientas de Visual Studio con la compilación de versión resaltada](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="b1ac5-196">En el  **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **StringLibrary** y seleccione **Compilar** desde el menú contextual para volver a compilar la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1ac5-197">![Menú contextual de StringLibrary con el comando Compilar](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="b1ac5-198">Ejecute las pruebas unitarias seleccionando **Prueba** > **Ejecutar** > **Todas las pruebas** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-198">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="b1ac5-199">Las pruebas se superan.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-199">The tests pass.</span></span>

<span data-ttu-id="b1ac5-200">Ahora que ha terminado de probar la biblioteca, el siguiente paso es ponerla a disposición de los llamadores.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-200">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="b1ac5-201">Puede empaquetarla con una o varias aplicaciones o puede distribuirla como un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-201">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="b1ac5-202">Para obtener más información, vea [Consumo de una biblioteca de clases .NET Standard](consuming-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-202">For more information, see [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1ac5-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1ac5-203">See also</span></span>

- [<span data-ttu-id="b1ac5-204">Conceptos básicos de las pruebas unitarias en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b1ac5-204">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
