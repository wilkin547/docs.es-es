---
title: Prueba de una biblioteca de clases de .NET Standard con .NET Core en Visual Studio 2017
description: Cree un proyecto de prueba unitaria para la biblioteca de clases .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 242234d93bc1b8f9b88749f2e3bcfb37c2bde86d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037972"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio-2017"></a>Prueba de una biblioteca de .NET Standard con .NET Core en Visual Studio 2017

En [Creación de una biblioteca de .NET Standard con C# y .NET Core en Visual Studio 2017](library-with-visual-studio.md) o [Creación de una biblioteca de .NET Standard con Visual Basic y .NET Core en Visual Studio 2017](vb-library-with-visual-studio.md), ha creado una biblioteca de clases simple que agrega un método de extensión a la clase <xref:System.String>. Ahora, creará una prueba unitaria para asegurarse de que funciona según lo esperado. Agregará su proyecto de prueba unitaria a la solución que ha creado en el artículo anterior.

## <a name="creating-a-unit-test-project"></a>Creación de un proyecto de prueba unitaria

Para crear el proyecto de prueba unitaria, haga lo siguiente:

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. En el **Explorador de soluciones**, abra el menú contextual del nodo de solución **ClassLibraryProjects** y seleccione **Agregar** > **Nuevo proyecto**.

1. En el cuadro de diálogo **Agregar nuevo proyecto**, seleccione el nodo **Visual C#** . Después seleccione el nodo **.NET Core** seguido por la plantilla del proyecto **Proyecto de prueba MSTest (.NET Core)** . En el cuadro de texto **Nombre**, escriba "StringLibraryTest" como nombre del proyecto. Seleccione **Aceptar** para crear el proyecto de prueba unitaria.

   ![Cuadro de diálogo Agregar nuevo proyecto en el que se muestra el proyecto de prueba unitaria: C#](./media/testing-library-with-visual-studio/create-new-test-project.png)

   > [!NOTE]  
   > Además de un proyecto de prueba MSTest, también puede usar Visual Studio para crear un proyecto de prueba xUnit para .NET Core.

1. Visual Studio crea el proyecto y abre el archivo *UnitTest1.cs* en la ventana de código.

   ![Ventana de código de Visual Studio para la clase y el método del proyecto de prueba unitaria: C#](./media/testing-library-with-visual-studio/unit-test-editor-window.png)

   El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:

   - Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.

   - Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`. Cada método de prueba en una clase de prueba etiquetada con el atributo \[TestMethod\] se ejecuta automáticamente cuando se ejecute la prueba unitaria.

   - Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> para definir `TestMethod1` como un método de prueba para la ejecución automática cuando se ejecuta la prueba unitaria.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia** del menú contextual.

   ![Menú contextual de las dependencias de StringLibraryTest: C#](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. En el cuadro de diálogo **Administrador de referencias**, expanda el nodo **Proyectos** y marque la casilla junto a **StringLibrary**. Agregar una referencia al ensamblado `StringLibrary` permite al compilador buscar métodos **StringLibrary**. Seleccione el botón **Aceptar**. Se agrega una referencia a su proyecto de biblioteca de clases, `StringLibrary`.

   ![Cuadro de diálogo Agregar referencia de proyecto de Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. En el **Explorador de soluciones**, abra el menú contextual del nodo de solución **ClassLibraryProjects** y seleccione **Agregar** > **Nuevo proyecto**.

1. En el cuadro de diálogo **Agregar nuevo proyecto**, seleccione el nodo **Visual Basic**. Después seleccione el nodo **.NET Core** seguido por la plantilla del proyecto **Proyecto de prueba MSTest (.NET Core)** . En el cuadro de texto **Nombre**, escriba "StringLibraryTest" como nombre del proyecto. Seleccione **Aceptar** para crear el proyecto de prueba unitaria.

   ![Cuadro de diálogo Agregar nuevo proyecto en el que se muestra el proyecto de prueba unitaria: Visual Basic](./media/testing-library-with-visual-studio/vb-create-new-test-project.png)

   > [!NOTE]  
   > Además de un proyecto de prueba MSTest, también puede usar Visual Studio para crear un proyecto de prueba xUnit para .NET Core.

1. Visual Studio crea el proyecto y abre el archivo *UnitTest1.vb* en la ventana de código.

   ![Ventana de código de Visual Studio para la clase y el método del proyecto de prueba unitaria: Visual Basic](./media/testing-library-with-visual-studio/vb-unit-test-editor-window.png)

   El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:

   - Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.

   - Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`. Cada método de prueba en una clase de prueba etiquetada con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> se ejecuta automáticamente cuando se ejecute la prueba unitaria.

   - Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> para definir `TestMethod1` como un método de prueba para la ejecución automática cuando se ejecuta la prueba unitaria.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia** del menú contextual.

   ![Menú contextual de las dependencias de StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. En el cuadro de diálogo **Administrador de referencias**, expanda el nodo **Proyectos** y marque la casilla junto a **StringLibrary**. Agregar una referencia al ensamblado `StringLibrary` permite al compilador buscar métodos **StringLibrary**. Seleccione el botón **Aceptar**. Se agrega una referencia a su proyecto de biblioteca de clases, `StringLibrary`.

   ![Cuadro de diálogo Agregar referencia de proyecto de Visual Studio: Visual Basic](./media/testing-library-with-visual-studio/project-reference-manager.png)

---

## <a name="adding-and-running-unit-test-methods"></a>Adición y ejecución de métodos de prueba unitaria

Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase de prueba unitaria; la clase a la que se le aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>. Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.

Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba. Algunos de sus métodos a los que se llama con más frecuencia se muestran en la tabla siguiente:

Métodos de aserción | Función
--- | ---
`Assert.AreEqual` | Comprueba que dos valores u objetos son iguales. La aserción da error si los valores o los objetos no son iguales.
`Assert.AreSame` | Comprueba que dos variables de objeto hacen referencia al mismo objeto. La aserción da error si las variables hacen referencia a objetos diferentes.
`Assert.IsFalse` | Comprueba si una condición es `false`. La aserción produce un error si la condición es `true`.
`Assert.IsNotNull` | Comprueba que un objeto no es `null`. La aserción da error si el objeto es `null`.

También puede aplicar el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> a un método de prueba. Indica el tipo de excepción que se espera que inicie un método de prueba. La prueba dará error si no se inicia la excepción especificada.

Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas. Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>. Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas. Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.

Dado que el método de biblioteca controla cadenas, quiere asegurarse también de que controla correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo <xref:System.String.Length> sea 0, y una cadena `null` que no se haya inicializado. Si `StartsWithUpper` se llama como un método de extensión en una instancia <xref:System.String>, no se puede pasar una cadena `null`. En cambio, también se puede llamar directamente como un método estático y pasarse como un argumento <xref:System.String> único.

Definirá tres métodos, cada uno de los cuales llama a su método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> repetidamente para cada elemento de una matriz de cadenas. Dado que el método de prueba produce un error tan pronto como encuentra el primer error, llamará a una sobrecarga de método que le permita pasar una cadena que indique el valor de cadena usado en la llamada al método.

Para crear los métodos de prueba:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Reemplace el código de la ventana de código *UnitTest1.cs* por el código siguiente:

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]

   Observe que la prueba de caracteres en mayúsculas del método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U+0391) y la letra mayúscula cirílica EM (U+041C), y la prueba de caracteres en minúsculas del método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U+03B1) y la letra cirílica minúscula Ghe (U+0433).

1. En la barra de menús, seleccione **Archivo** > **Guardar UnitTest1.cs como**. En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y seleccione **Guardar con codificación**.

   ![Cuadro de diálogo Guardar archivo como de Visual Studio: C#](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Reemplace el código de la ventana de código *UnitTest1.vb* por el código siguiente:

    [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   Observe que la prueba de caracteres en mayúsculas del método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U+0391) y la letra mayúscula cirílica EM (U+041C), y la prueba de caracteres en minúsculas del método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U+03B1) y la letra cirílica minúscula Ghe (U+0433).

1. En la barra de menús, seleccione **Archivo** > **Guardar UnitTest1.vb como**. En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y seleccione **Guardar con codificación**.

   ![Cuadro de diálogo Guardar archivo como de Visual Studio: Visual Basic](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

---

1. En el cuadro de diálogo **Confirmar guardar como**, seleccione el botón **Sí** para guardar el archivo.

1. En el cuadro de diálogo **Opciones avanzadas para guardar**, seleccione **Unicode (UTF-8 con firma) - Página de códigos 65001** desde la lista desplegable **Codificación** y seleccione **Aceptar**.

   ![Cuadro de diálogo Opciones avanzadas para guardar de Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)

   Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII. Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán precisos.

1. En la barra de menús, seleccione **Prueba** > **Ejecutar** > **Todas las pruebas**. Se abre la ventana del **Explorador de pruebas** y muestra que las pruebas se han ejecutado correctamente. Las tres pruebas se muestran en la sección **Pruebas superadas** y en la sección **Resumen** se informa del resultado de la serie de pruebas.

   ![Ventana Explorador de pruebas con pruebas superadas](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handling-test-failures"></a>Control de errores en las pruebas

Su serie de pruebas no tuvo errores, pero vamos a cambiarla un poco para que uno de los métodos de prueba produzca un error:

1. Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error". No necesita guardar el archivo porque Visual Studio guarda automáticamente archivos abiertos cuando se crea una solución para ejecutar pruebas.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. Ejecute la prueba seleccionando **Prueba** > **Ejecutar** > **Todas las pruebas** de la barra de menús. En la ventana **Explorador de pruebas** se indica que dos pruebas se han realizado correctamente y que una ha finalizado con errores.

   ![Ventana Explorador de pruebas con pruebas no superadas](./media/testing-library-with-visual-studio/failed-test-window.png)

1. Seleccione la prueba que ha dado error, `TestDoesNotStartWith`, en la sección **Pruebas no superadas**. En la ventana **Explorador de pruebas** se muestra el mensaje generado por la instrucción Assert: "Error de Assert.IsFalse. Se esperaba para "Error": false; real: True". Debido al error, no se probaron todas las cadenas de la matriz después de "Error".

   ![Ventana del Explorador de pruebas que muestra el error de aserción Is False](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. Deshaga la modificación que hizo en el paso 1 y quite la cadena "Error". Vuelva a ejecutar la prueba y se superarán las pruebas.

## <a name="testing-the-release-version-of-the-library"></a>Prueba de la versión de la biblioteca

Ha estado ejecutando sus pruebas con la versión de depuración de la biblioteca. Ahora que todas sus pruebas se han superado y que ha probado adecuadamente la biblioteca, debe ejecutar las pruebas un tiempo adicional con respecto a la compilación de versión de la biblioteca. Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.

Para probar la compilación de versión:

1. En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.

   ![Barra de herramientas de Visual Studio con compilación de versión resaltado](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. En el  **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **StringLibrary** y seleccione **Compilar** desde el menú contextual para volver a compilar la biblioteca.

   ![Menú contextual de StringLibrary con el comando Compilar](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. Ejecute las pruebas unitarias seleccionando **Prueba** > **Ejecutar** > **Todas las pruebas** de la barra de menús. Las pruebas se superan.

Ahora que ha terminado de probar la biblioteca, el siguiente paso es ponerla a disposición de los llamadores. Puede empaquetarla con una o varias aplicaciones o puede distribuirla como un paquete NuGet. Para obtener más información, vea [Consumo de una biblioteca de clases .NET Standard](./consuming-library-with-visual-studio.md).
