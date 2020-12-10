---
title: Prueba de una biblioteca de clases de .NET con Visual Studio para Mac
description: Cree un proyecto de prueba unitaria para una biblioteca de clases de .NET. Compruebe que la biblioteca de clases de .NET funciona correctamente con pruebas unitarias.
ms.date: 11/18/2020
ms.openlocfilehash: 02d5aa74258ec15c5447b23246a3c7e9c61a6760
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599531"
---
# <a name="test-a-net-class-library-using-visual-studio"></a>Prueba de una biblioteca de clases de .NET con Visual Studio

En este tutorial se muestra cómo automatizar las pruebas unitarias mediante la adición de un proyecto de prueba a una solución.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la solución que se crea en [Creación de una biblioteca de clases de .NET con Visual Studio para Mac](library-with-visual-studio-mac.md).

## <a name="create-a-unit-test-project"></a>Crear un proyecto de prueba unitaria

Las pruebas unitarias proporcionan pruebas de software automatizadas durante el desarrollo y la publicación. [MSTest](https://github.com/Microsoft/testfx-docs) es uno de los tres marcos de pruebas que puede elegir. Los otros son [xUnit](https://xunit.net/) y [nUnit](https://nunit.org/).

1. Inicie Visual Studio para Mac:

1. Abra la solución `ClassLibraryProjects` que ha creado en [Creación de una biblioteca de clases de .NET con Visual Studio para Mac](library-with-visual-studio-mac.md).

1. En el panel **Solución**, presione <kbd>Ctrl</kbd>, haga clic en la solución `ClassLibraryProjects` y seleccione **Agregar** > **Nuevo proyecto**.

1. En el cuadro de diálogo **Nuevo proyecto**, seleccione **Pruebas** en el nodo **Web and Console** (Web y consola). Seleccione el **proyecto MSTest** y, luego, **Siguiente**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="Cuadro de diálogo Nuevo proyecto de Visual Studio para Mac que crea un proyecto de prueba":::

1. Seleccione **.NET 5.0** como **Marco de destino** y, a continuación, elija **Siguiente**.

1. Asigne al nuevo proyecto el nombre "StringLibraryTest" y seleccione **Crear**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="Cuadro de diálogo Nuevo proyecto de Visual Studio para Mac en el que se proporciona el nombre del proyecto":::

   Visual Studio crea un archivo de clase con el código siguiente:

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

   El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:

   - Importa el espacio de nombres de <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, que contiene los tipos utilizados para las pruebas unitarias.
   - Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> a la clase `UnitTest1`.
   - Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> a `TestMethod1`.

   Cada método etiquetado con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) en una clase de prueba etiquetada con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) se ejecuta automáticamente cuando se ejecuta la prueba unitaria.

## <a name="add-a-project-reference"></a>Agregar una referencia de proyecto

Para que el proyecto de prueba funcione con la clase `StringLibrary`, agregue una referencia al proyecto `StringLibrary`.

1. En el panel **Solución**, presione <kbd>Ctrl</kbd> y haga clic en **Dependencias** en **StringLibraryTest**. Seleccione **Agregar referencia** en el menú contextual.

1. En el cuadro de diálogo **Referencias**, seleccione el proyecto **StringLibrary**. Seleccione **Aceptar**.

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="Cuadro de diálogo Editar referencias de Visual Studio para Mac":::

## <a name="add-and-run-unit-test-methods"></a>Adición y ejecución de métodos de prueba unitaria

Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> en una clase que está marcada con el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>. Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.

Las pruebas más comunes llaman a los miembros de la clase <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba. Algunos de los métodos `Assert` a los que se llama con más frecuencia se muestran en la tabla siguiente:

| Métodos de aserción     | Función |
| ------------------ | -------- |
| `Assert.AreEqual`  | Comprueba que dos valores u objetos son iguales. La aserción da error si los valores o los objetos no son iguales. |
| `Assert.AreSame`   | Comprueba que dos variables de objeto hacen referencia al mismo objeto. La aserción da error si las variables hacen referencia a objetos diferentes. |
| `Assert.IsFalse`   | Comprueba si una condición es `false`. La aserción produce un error si la condición es `true`. |
| `Assert.IsNotNull` | Comprueba que un objeto no es `null`. La aserción da error si el objeto es `null`. |

También puede usar el método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> en un método de prueba para indicar el tipo de excepción que se espera que produzca. La prueba dará error si no se inicia la excepción especificada.

Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas. Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>. Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas. Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.

Dado que el método de biblioteca administra cadenas, quiere asegurarse también de que administra correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo <xref:System.String.Length> sea 0, y una cadena `null` que no se haya inicializado. Se puede llamar a `StartsWithUpper` directamente como un método estático y pasar un argumento <xref:System.String> único. También puede llamar a `StartsWithUpper` como método de extensión en una variable de `string` asignada a `null`.

Definirá tres métodos, cada uno de los cuales llama a un método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> para cada elemento de una matriz de cadenas. Llamará a una sobrecarga de método que le permite especificar que se muestre un mensaje de error en caso de error en la prueba. El mensaje identifica la cadena que causó el error.

Para crear los métodos de prueba:

1. Abra el archivo *UnitTest1.cs* y reemplace el código por el siguiente:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C). La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).

1. En la barra de menús, seleccione **Archivo** > **Guardar como**. En el cuadro de diálogo, asegúrese de que **Codificación** esté establecida en **Unicode (UTF-8)** .

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="Cuadro de diálogo Guardar archivo como de Visual Studio":::

1. Cuando se le pregunte si quiere reemplazar el archivo existente, seleccione **Reemplazar**.

   Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII. Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán correctos.

1. Abra el panel **Pruebas unitarias** en el lado derecho de la pantalla. En el menú, seleccione **Ver** > **Pruebas**.

1. Haga clic en el icono **Acoplar** para mantener abierto el panel.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="Icono de acoplamiento del panel Pruebas unitarias de Visual Studio para Mac":::

1. Haga clic en el botón **Ejecutar todas**.

   Todas las pruebas se superan.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="Prueba superada esperada de Visual Studio para Mac":::

## <a name="handle-test-failures"></a>Administración de errores de prueba

Si está realizando el desarrollo controlado por pruebas (TDD), escribirá las pruebas, y estas generarán un error cuando las ejecute por primera vez. Después, agregará un código a la aplicación para que la prueba se realice correctamente. En este tutorial, ha creado la prueba después de escribir el código de la aplicación que valida, por lo que no ha podido comprobar si la prueba genera un error. Para asegurarse de que una prueba genera un error cuando espera que lo haga, agregue un valor no válido a la entrada de prueba.

1. Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error". No necesita guardar el archivo porque Visual Studio guarda automáticamente archivos abiertos cuando se crea una solución para ejecutar pruebas.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Vuelva a ejecutar las pruebas.

   Esta vez, en la ventana **Explorador de pruebas** se indica que dos pruebas se han realizado correctamente y que una ha finalizado con errores.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="Ventana Explorador de pruebas con pruebas no superadas":::

1. Presione <kbd>Ctrl</kbd> y haga clic en la prueba con errores, `TestDoesNotStartWithUpper`, y seleccione **Mostrar el panel de resultados** en el menú contextual.

   El panel **Resultados** muestra el mensaje generado por la aserción: "Error de Assert.IsFalse. Se esperaba para "Error": false; real: True". Debido al error, no se probaron todas las cadenas de la matriz después de "Error".

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="Ventana del Explorador de pruebas que muestra el error de aserción IsFalse":::

1. Quite la cadena "Error" que agregó en el paso 1. Vuelva a ejecutar la prueba y se superarán las pruebas.

## <a name="test-the-release-version-of-the-library"></a>Prueba de la versión de la biblioteca

Ahora que se han superado todas las pruebas al ejecutar la versión de depuración de la biblioteca, ejecute las pruebas una vez más con la versión de lanzamiento de la biblioteca. Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.

Para probar la compilación de versión:

1. En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra de herramientas de Visual Studio con la compilación de versión resaltada":::

1. En el panel **Solución**, presione <kbd>Ctrl</kbd> y haga clic en el proyecto **StringLibrary** y seleccione **Compilación** en el menú contextual para volver a compilar la biblioteca.

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="Menú contextual de StringLibrary con el comando Compilar":::

1. Ejecute de nuevo las pruebas unitarias.

   Las pruebas se superan.

## <a name="debug-tests"></a>Depuración de pruebas

Si usa Visual Studio para Mac como IDE, puede emplear el mismo proceso que se muestra en [Tutorial: Depuración de una aplicación de consola de .NET con Visual Studio para Mac](debugging-with-visual-studio-mac.md) para depurar el código mediante el proyecto de prueba unitaria. En lugar de iniciar el proyecto de aplicación *ShowCase*, presione <kbd>Ctrl</kbd> y haga clic en el proyecto **StringLibraryTests** y seleccione **Iniciar depuración del proyecto** en el menú contextual.

Visual Studio inicia el proyecto de prueba con el depurador asociado. La ejecución se detendrá en cualquier punto de interrupción que haya agregado al proyecto de prueba o al código de la biblioteca subyacente.

## <a name="additional-resources"></a>Recursos adicionales

* [Pruebas unitarias en .NET](../testing/index.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha realizado una prueba unitaria de una biblioteca de clases. Puede poner la biblioteca a disposición de otros usuarios si la publica en [NuGet](https://nuget.org) como un paquete. Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:

> [!div class="nextstepaction"]
> [Crear y publicar un paquete (CLI de dotnet)](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

Si publica una biblioteca como un paquete NuGet, otros usuarios pueden instalarla y usarla. Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:

> [!div class="nextstepaction"]
> [Instalación y uso de un paquete en Visual Studio para Mac](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

No es necesario distribuir una biblioteca como un paquete. Se puede agrupar con una aplicación de consola que la use. Para aprender a publicar una aplicación de consola, vea el tutorial anterior de esta serie:

> [!div class="nextstepaction"]
> [Publicación de una aplicación de consola de .NET con Visual Studio para Mac](publishing-with-visual-studio-mac.md)
