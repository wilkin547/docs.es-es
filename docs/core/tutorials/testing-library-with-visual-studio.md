---
title: Prueba de una biblioteca de clases .NET Standard con .NET Core en Visual Studio
description: Cree un proyecto de prueba unitaria para la biblioteca de clases .NET Core. Compruebe que la biblioteca de clases de .NET Core funciona correctamente con pruebas unitarias.
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 3a4f25b0d250469102fdac6ee960e42b2d969aed
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559583"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a>Prueba de una biblioteca .NET Standard con .NET Core en Visual Studio

En [Creación de una biblioteca de .NET Standard con C# y el SDK de .NET Core en Visual Studio 2017](library-with-visual-studio.md), ha creado una biblioteca de clases simple que agrega un método de extensión a la clase <xref:System.String>. Ahora, creará una prueba unitaria para asegurarse de que funciona según lo esperado. Agregará su proyecto de prueba unitaria a la solución que ha creado en el artículo anterior.

## <a name="create-a-unit-test-project"></a>Crear un proyecto de prueba unitaria

Para crear el proyecto de prueba unitaria, haga lo siguiente:

1. Abra la solución `ClassLibraryProjects` que creó en el artículo [Creación de una biblioteca de .NET Standard con C# y el SDK de .NET Core en Visual Studio 2017](library-with-visual-studio.md).

1. Agregue un nuevo proyecto de prueba unitaria denominado "StringLibraryTest" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **mstest**. En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**. Elija la plantilla **Proyecto de prueba de Ms (.NET Core)** y, luego, elija **Siguiente**.

   1. En la página **Configurar el nuevo proyecto**, escriba **StringLibraryTest** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

   > [!NOTE]
   > Además de MSTest, también puede crear proyectos de prueba xUnit y nUnit para .NET Core en Visual Studio.

1. Visual Studio crea el proyecto y abre el archivo de clase en la ventana de código con el siguiente código:

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

   El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:

   - Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.

   - Aplica el atributo [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) a la clase `UnitTest1`. Cada método de prueba en una clase de prueba etiquetada con el atributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) se ejecuta automáticamente cuando se ejecute la prueba unitaria.

   - Aplica el atributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) para definir `TestMethod1` en C# o `TestSub` en Visual Basic como método de prueba para la ejecución automática cuando se ejecuta la prueba unitaria.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia** del menú contextual.

   > [!div class="mx-imgBorder"]
   > ![Menú contextual de las dependencias de StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. En el cuadro de diálogo **Administrador de referencias**, expanda el nodo **Proyectos** y marque la casilla junto a **StringLibrary**. Agregar una referencia al ensamblado `StringLibrary` permite al compilador buscar métodos **StringLibrary**. Seleccione el botón **Aceptar**. Se agrega una referencia a su proyecto de biblioteca de clases, `StringLibrary`.

   ![Cuadro de diálogo Administrador de referencias en Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a>Adición y ejecución de métodos de prueba unitaria

Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase de prueba unitaria; la clase a la que se le aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>. Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.

Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba. Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:

| Métodos de aserción     | Función |
| ------------------ | -------- |
| `Assert.AreEqual`  | Comprueba que dos valores u objetos son iguales. La aserción da error si los valores o los objetos no son iguales. |
| `Assert.AreSame`   | Comprueba que dos variables de objeto hacen referencia al mismo objeto. La aserción da error si las variables hacen referencia a objetos diferentes. |
| `Assert.IsFalse`   | Comprueba si una condición es `false`. La aserción produce un error si la condición es `true`. |
| `Assert.IsNotNull` | Comprueba que un objeto no es `null`. La aserción da error si el objeto es `null`. |

También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> en un método de prueba para indicar el tipo de excepción que se espera que produzca. La prueba dará error si no se inicia la excepción especificada.

Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas. Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>. Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas. Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.

Dado que el método de biblioteca administra cadenas, quiere asegurarse también de que administra correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo <xref:System.String.Length> sea 0, y una cadena `null` que no se haya inicializado. Si `StartsWithUpper` se llama como un método de extensión en una instancia <xref:System.String>, no se puede pasar una cadena `null`. En cambio, también se puede llamar directamente como un método estático y pasarse como un argumento <xref:System.String> único.

Definirá tres métodos, cada uno de los cuales llama a su método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> repetidamente para cada elemento de una matriz de cadenas. Dado que el método de prueba produce un error tan pronto como encuentra el primer error, llamará a una sobrecarga de método que le permita pasar una cadena que indique el valor de cadena usado en la llamada al método.

Para crear los métodos de prueba:

1. En la ventana de código *UnitTest1.cs* o *UnitTest1.vb*, reemplace el código por el siguiente:

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C). La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).

1. En la barra de menús, seleccione **Archivo** > **Guardar UnitTest1.cs como** o **Archivo** > **Guardar UnitTest1.vb como**. En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y seleccione **Guardar con codificación**.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo Guardar archivo como de Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

1. En el cuadro de diálogo **Confirmar guardar como**, seleccione el botón **Sí** para guardar el archivo.

1. En el cuadro de diálogo **Opciones avanzadas para guardar**, seleccione **Unicode (UTF-8 con firma) - Página de códigos 65001** desde la lista desplegable **Codificación** y seleccione **Aceptar**.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo Opciones avanzadas para guardar de Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)

   Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII. Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán correctos.

1. En la barra de menús, seleccione **Prueba** > **Ejecutar** > **Todas las pruebas**. Se abre la ventana del **Explorador de pruebas** y muestra que las pruebas se han ejecutado correctamente. Las tres pruebas se muestran en la sección **Pruebas superadas** y en la sección **Resumen** se informa del resultado de la serie de pruebas.

   > [!div class="mx-imgBorder"]
   > ![Ventana Explorador de pruebas con pruebas superadas](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handle-test-failures"></a>Administración de errores de prueba

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

   > [!div class="mx-imgBorder"]
   > ![Ventana Explorador de pruebas con pruebas no superadas](./media/testing-library-with-visual-studio/failed-test-window.png)

1. Seleccione la prueba con errores, `TestDoesNotStartWith`. En la ventana **Explorador de pruebas** se muestra el mensaje generado por la instrucción Assert: "Error de Assert.IsFalse. Se esperaba para "Error": false; real: True". Debido al error, no se probaron todas las cadenas de la matriz después de "Error".

   > [!div class="mx-imgBorder"]
   > ![Ventana del Explorador de pruebas que muestra el error de aserción IsFalse](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. Deshaga la modificación que hizo en el paso 1 y quite la cadena "Error". Vuelva a ejecutar la prueba y se superarán las pruebas.

## <a name="test-the-release-version-of-the-library"></a>Prueba de la versión de la biblioteca

Ha estado ejecutando sus pruebas con la versión de depuración de la biblioteca. Ahora que todas sus pruebas se han superado y que ha probado adecuadamente la biblioteca, debe ejecutar las pruebas un tiempo adicional con respecto a la compilación de versión de la biblioteca. Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.

Para probar la compilación de versión:

1. En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.

   > [!div class="mx-imgBorder"]
   > ![Barra de herramientas de Visual Studio con la compilación de versión resaltada](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. En el  **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **StringLibrary** y seleccione **Compilar** desde el menú contextual para volver a compilar la biblioteca.

   > [!div class="mx-imgBorder"]
   > ![Menú contextual de StringLibrary con el comando Compilar](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. Ejecute las pruebas unitarias seleccionando **Prueba** > **Ejecutar** > **Todas las pruebas** de la barra de menús. Las pruebas se superan.

Ahora que ha terminado de probar la biblioteca, el siguiente paso es ponerla a disposición de los llamadores. Puede empaquetarla con una o varias aplicaciones o puede distribuirla como un paquete NuGet. Para obtener más información, vea [Consumo de una biblioteca de clases .NET Standard](consuming-library-with-visual-studio.md).

## <a name="see-also"></a>Vea también

- [Conceptos básicos de las pruebas unitarias en Visual Studio](/visualstudio/test/unit-test-basics)
