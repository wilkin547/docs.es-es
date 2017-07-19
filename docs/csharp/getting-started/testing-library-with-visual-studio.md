---
title: Prueba de una biblioteca de clases con .NET Core en Visual Studio 2017 | Microsoft Docs
description: Aprenda a realizar una prueba de una biblioteca de clases escrita en C# con Visual Studio 2017
keywords: .NET Core, biblioteca de clases de .NET Standard, Visual Studio 2017, prueba unitaria
author: BillWagner
ms.author: wiwagn
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 069ad711-3eaa-45c6-94d7-b40249cc8b99
ms.translationtype: Human Translation
ms.sourcegitcommit: 829c604f9bafce03b7008cbb768371a1a08de222
ms.openlocfilehash: f07ba05a617f5e270f0e08f2006b25cecc04f05b
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---

<a id="testing-a-class-library-with-net-core-in-visual-studio-2017" class="xliff"></a>

# Prueba de una biblioteca de clases con .NET Core en Visual Studio 2017

En [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md) (Creación de una biblioteca de clases con C# y .NET Core en Visual Studio 2017), ha creado una biblioteca de clases simple que agrega un método de extensión a la clase @System.String. Ahora, creará una prueba unitaria para asegurarse de que funciona según lo esperado. Agregará su proyecto de prueba unitaria a la solución que ha creado en el tema anterior.

<a id="creating-a-unit-test-project" class="xliff"></a>

## Creación de un proyecto de prueba unitaria

Para crear el proyecto de prueba unitaria, haga lo siguiente:

1. En el **Explorador de soluciones**, abra el menú contextual del nodo de solución **ClassLibraryProjects** y seleccione **Agregar** > **Nuevo proyecto**.

   <!-- Need a VS 2017 version  [!NOTE] In addition to a Unit Test project, you can also use Visual Studio to create an xUnit test project for .NET Core. For a walkthrough that includes an xUnit test project, see [Getting started with .NET Core on Windows, using Visual Studio 2015](../../core/tutorials/using-on-windows.md). --> 

1. En el cuadro de diálogo **Agregar nuevo proyecto**, seleccione el nodo **.NET Core** seguido por la plantilla del proyecto **Proyecto de prueba unitaria (.NET Core)**. En el cuadro de texto **Nombre**, escriba "StringLibraryTest" como nombre del proyecto. Seleccione **Aceptar** para crear el proyecto de prueba unitaria.

   ![Cuadro de diálogo Agregar nuevo proyecto](./media/testing-library-with-visual-studio/testproject.png)

1. Visual Studio crea el proyecto y abre el archivo *UnitTest1.cs* en la ventana de código.

   ![Ventana de código de Visual Studio que muestra la clase UnitTest1 del proyecto de prueba unitaria predeterminado y el método TestMethod1](./media/testing-library-with-visual-studio/unittestwindow.png)

   El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:

   * Importa el espacio de nombres [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx), que contiene los tipos usados para la prueba unitaria.

   * Aplica el atributo [ \[TestClass\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) a la clase `UnitTest1`. Cada método de prueba en una clase de prueba etiquetada con el atributo \[TestMethod\] se ejecuta automáticamente cuando se ejecute la prueba unitaria.

   * Aplica el atributo [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) para definir `TestMethod1` como un método de prueba para la ejecución automática cuando se ejecuta la prueba unitaria.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia** del menú contextual.

   ![Menú contextual de las dependencias de StringLibraryTest](./media/testing-library-with-visual-studio/addreference.png)

1. En el cuadro de diálogo **Administrador de referencias**, marque la casilla junto a **StringLibrary**. Agregar una referencia al ensamblado `StringLibrary` permite al compilador buscar métodos **StringLibrary**. Seleccione el botón **Aceptar**. Se agrega una referencia a su proyecto de biblioteca de clases, `StringLibrary`.

   ![Administrador de referencias](./media/testing-library-with-visual-studio/referencemanager.png)

<a id="adding-and-running-unit-test-methods" class="xliff"></a>

## Adición y ejecución de métodos de prueba unitaria

Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) en una clase de prueba unitaria; la clase a la que se le aplica el atributo [\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx). Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.

Las pruebas más comunes llaman a los miembros de clase [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx). Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba. Algunos de sus métodos a los que se llama con más frecuencia se muestran en la tabla siguiente.

Métodos de aserción | Función
--- | ---
`Assert.AreEqual` | Comprueba que dos valores u objetos son iguales. La aserción da error si los valores o los objetos no son iguales.
`Assert.AreSame` | Comprueba que dos variables de objeto hacen referencia al mismo objeto. La aserción da error si las variables hacen referencia a objetos diferentes.
`Assert.IsFalse` | Comprueba si una condición es `false`. La aserción produce un error si la condición es `true`.
`Assert.IsNotNull` | Comprueba que un objeto no es `null`. La aserción da error si el objeto es `null`.
Atributo [\[ExpectedException\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.expectedexceptionattribute.aspx) | Indica el tipo de excepción que se espera que inicie un método de prueba. La prueba dará error si no se inicia la excepción especificada.

Al probar el método `StringLibrary.StartsWithUpper`, quiere proporcionar un número de cadenas que comiencen con un carácter en mayúsculas. Espera que el método devuelva `true` en estos casos, por lo que puede llamar al método [Assert.IsTrue(Boolean, String)](https://msdn.microsoft.com/library/ms243754.aspx). Del mismo modo, quiere proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas. Espera que el método devuelva `false` en estos casos, por lo que puede llamar al método [Assert.IsFalse(Boolean, String)](https://msdn.microsoft.com/library/ms243805.aspx).

Dado que el método de biblioteca controla cadenas, quiere asegurarse también de que controla correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty), una cadena válida que no tenga caracteres y cuyo @System.String.Length sea 0, y una cadena `null` que no se haya inicializado. Si `StartsWithUpper` se llama como un método de extensión en una instancia @System.String, no se puede pasar una cadena `null`. En cambio, también se puede llamar directamente como un método estático y pasarse como un argumento @System.String único.

Definirá tres métodos, cada uno de los cuales llama a su método [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) repetidamente para cada elemento de una matriz de cadenas. Dado que el método de prueba produce un error tan pronto como encuentra el primer error, llamará a una sobrecarga de método que le permita pasar una cadena que indique el valor de cadena usado en la llamada al método.

Para crear los métodos de prueba:

1. Reemplace el código de la ventana de código *UnitTest1.cs* por el código siguiente:

   [!CODE-csharp[Prueba 1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs#1)]

   Observe que la prueba de caracteres en mayúsculas del método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U+0391) y la letra mayúscula cirílica EM (U+041C), y la prueba de caracteres en minúsculas del método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U+03B1) y la letra cirílica minúscula Ghe (U+0433).

1. En la barra de menús, seleccione **Archivo** > **Guardar UnitTest1.cs como**. En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y seleccione **Guardar con codificación**.

   ![Cuadro de diálogo Guardar archivo como](./media/testing-library-with-visual-studio/savefileas.png)

1. En el cuadro de diálogo **Confirmar guardar como**, seleccione el botón **Sí** para guardar el archivo.

1. En el cuadro de diálogo **Opciones avanzadas para guardar**, seleccione **Unicode (UTF-8 con firma) - Página de códigos 65001** desde la lista desplegable **Codificación** y seleccione **Aceptar**.

   ![Cuadro de diálogo Opciones avanzadas para guardar](./media/testing-library-with-visual-studio/advancedsaveoptions.png)

   Si obtiene un error al guardar el código fuente en un archivo con codificación UTF-8, Visual Studio puede guardarlo como un archivo ASCII. Cuando eso suceda, el tiempo de ejecución no descodifica correctamente los caracteres UTF-8 del rango ASCII, y los resultados de la prueba no serán precisos.

1. En la barra de menús, seleccione **Prueba** > **Ejecutar** > **Todas las pruebas**. Se abre la ventana del **Explorador de pruebas** y muestra que las pruebas se ejecutan correctamente. Las tres pruebas se muestran en la sección **Pruebas superadas** y en la sección **Resumen** se informa del resultado de la serie de pruebas.

   ![Ventana del Explorador de pruebas](./media/testing-library-with-visual-studio/firsttest.png)

<a id="handling-test-failures" class="xliff"></a>

## Control de errores en las pruebas

Su serie de pruebas no tuvo errores, pero vamos a cambiarla un poco para que uno de los métodos de prueba produzca un error:

1. Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error". No necesita guardar el archivo porque Visual Studio guarda automáticamente archivos abiertos cuando se crea una solución para ejecutar pruebas.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Ejecute la prueba seleccionando **Prueba** > **Ejecutar** > **Todas las pruebas** de la barra de menús. En la ventana **Explorador de pruebas** se indica que dos pruebas se han realizado correctamente y que una ha finalizado con errores.

   ![Ventana del Explorador de pruebas](./media/testing-library-with-visual-studio/failedtest.png)

1. Seleccione la prueba que ha dado error, `TestDoesNotStartWith`, en la sección **Pruebas no superadas**. En la ventana **Explorador de pruebas** se muestra el mensaje generado por la aserción: "Error de Assert.IsFalse. Se esperaba para "Error": false; real: True". Debido al error, no se probaron todas las cadenas de la matriz después de "Error".

   ![Ventana del Explorador de pruebas que muestra el error de aserción Is False](./media/testing-library-with-visual-studio/failedtestdetail.png)

1. Quite el código que ha agregado (`"Error", `) y vuelva a ejecutar la prueba. Se superarán las pruebas.

<a id="testing-the-release-version-of-the-library" class="xliff"></a>

## Prueba de la versión de la biblioteca

Ha estado ejecutando sus pruebas con la versión de depuración de la biblioteca. Ahora que todas sus pruebas se han superado y que ha probado adecuadamente la biblioteca, debe ejecutar las pruebas un tiempo adicional con respecto a la compilación de versión de la biblioteca. Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.

Para probar la compilación de versión:

1. En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**.

   ![Barra de herramientas de Visual Studio](./media/testing-library-with-visual-studio/toolbar.png)

1. En el  **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **StringLibrary** y seleccione **Compilar** desde el menú contextual para volver a compilar la biblioteca.

   ![Menú contextual StringLibrary](./media/testing-library-with-visual-studio/buildlibrary.png)

1. Ejecute las pruebas unitarias seleccionando **Prueba** > **Ejecutar** > **Todas las pruebas** de la barra de menús. Las pruebas se superan.

Ahora que ha terminado de probar la biblioteca, el siguiente paso es ponerla a disposición de los llamadores. Puede empaquetarla con una o varias aplicaciones o puede distribuirla como un paquete NuGet. Para obtener más información, vea [Consumo de una biblioteca de clases .NET Standard](./consuming-library-with-visual-studio.md).

