---
title: Prueba de una biblioteca de clases con .NET Core en Visual Studio 2017
description: Aprenda a realizar una prueba de una biblioteca de clases escrita en C# con Visual Studio 2017
keywords: .NET Core, biblioteca de clases de .NET Standard, Visual Studio 2017, prueba unitaria
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 069ad711-3eaa-45c6-94d7-b40249cc8b99
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ee21799706b971f0ec13285b0771b32b4367f570
ms.lasthandoff: 03/13/2017

---

# <a name="testing-a-class-library-with-net-core-in-visual-studio-2017"></a>Prueba de una biblioteca de clases con .NET Core en Visual Studio 2017 #

En [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio-2017.md) (Creación de una biblioteca de clases con C# y .NET Core en Visual Studio 2017), hemos creado una biblioteca de clases simple que agrega un método de extensión a la clase @System.String. Ahora, vamos a crear una prueba unitaria para asegurarnos de que funciona según lo esperado. Vamos a agregar nuestro proyecto de prueba unitaria a la solución que creamos en el tema anterior.

## <a name="creating-a-unit-test-project"></a>Creación de un proyecto de prueba unitaria ##

Para crear el proyecto de prueba unitaria, haga lo siguiente:

1. En el Explorador de soluciones, abra el menú contextual del nodo de solución **ClassLibraryProject** y elija **Agregar**, **Nuevo proyecto**.

   <!-- Need a VS 2017 version  [!NOTE] In addition to a Unit Test project, you can also use Visual Studio to create an XUnit test project for .NET Core. For a walkthrough that includes an XUnit test project, see [Getting started with .NET Core on Windows, using Visual Studio 2015](../../core/tutorials/using-on-windows.md). --> 

1. En el cuadro de diálogo **Agregar nuevo proyecto**, expanda el nodo **Visual C#** y el nodo **.NET Core**, a continuación, elija la plantilla de proyecto **Proyecto de prueba unitaria (.NET Core)** y asígnele el nombre `StringLibraryTest`, como se muestra en la siguiente ilustración.

   ![Imagen](./media/testproject.jpg)

1. Seleccione el botón **Aceptar** para crear el proyecto. Visual Studio crea el proyecto y abre el archivo `UnitTest1.cs` en la ventana de código, como se muestra en la siguiente ilustración.

   ![Imagen](./media/unit_test_code_window.jpg)

   El código fuente creado por la plantilla de prueba unitaria hace lo siguiente:

   - Importa el espacio de nombres [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx), que contiene los tipos usados para la prueba unitaria.

   - Aplica el atributo [ \[TestClass\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) a la clase `UnitTest1`. Cada método de prueba en una clase de prueba etiquetada con el atributo \[TestMethod\] se ejecutará automáticamente cuando se ejecute la prueba unitaria.

   - Aplica el atributo [ \[TestMethod\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) para definir `TestMethod1` como un método de prueba que se ejecuta automáticamente cuando se ejecute la prueba unitaria.

1. En el Explorador de soluciones, abra el menú contextual del nodo **Dependencias** del proyecto **StringLibraryTest** y seleccione **Agregar referencia**. Se agrega una referencia a nuestro proyecto de biblioteca de clases, `StringLibrary`. 

1. En el cuadro de diálogo **Administrador de referencias**, expanda el nodo **Proyectos** y seleccione **Solución**y, a continuación, marque la casilla junto a **StringLibrary**, como se muestra en la siguiente ilustración. Agregar una referencia al ensamblado `StringLibrary` permite al compilador resolver llamadas a métodos **StringLibrary**.

   ![Imagen](./media/add_reference.jpg)

1. Haga clic en el botón **Aceptar** para cerrar el cuadro de diálogo **Administrador de referencias**.

## <a name="adding-and-running-unit-test-methods"></a>Adición y ejecución de métodos de prueba unitaria ##

Cuando Visual Studio ejecuta una prueba unitaria, ejecuta cada método marcado con el atributo [ \[TestMethod\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) en una clase de prueba unitaria (la clase a la que se le aplica el atributo) [ \[TestClass\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx). Un método de prueba finaliza cuando se encuentra el primer error, o cuando todas las pruebas contenidas en el método se han realizado correctamente.

Las pruebas más comunes llaman a los miembros de clase [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx). Muchos métodos de aserción incluyen al menos dos parámetros, uno de los cuales es el resultado esperado de la prueba y el otro es el resultado real de la prueba. Algunos de sus métodos a los que se llama con más frecuencia son:

- `Assert.AreEqual`, que comprueba si dos valores u objetos son iguales. La aserción da error si los valores o los objetos no son iguales.

- `Assert.AreSame`, que comprueba si dos variables de objeto hacen referencia al mismo objeto. La aserción da error si las variables hacen referencia a objetos diferentes.

- `Assert.IsFalse`, que comprueba si una condición es falsa. La aserción da error si la condición es verdadera.

- `Assert.IsNotNull`, que comprueba que un objeto no es `null`. La aserción da error si el objeto es `null`.

Además, el atributo [ \[ExpectedException\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.expectedexceptionattribute.aspx) puede usarse para indicar el tipo de excepción que se espera que inicie un método de prueba. Se usa para probar las condiciones que deben dar lugar en una excepción. La prueba dará error si no se inicia la excepción especificada.

Al probar el método `StringLibrary.StartsWithUpper`, queremos proporcionar un número de cadenas que comiencen con un carácter en mayúsculas. Esperamos que el método devuelva `True` en estos casos, por lo que podemos llamar al método [Assert.IsTrue (Boolean, String)](https://msdn.microsoft.com/library/ms243754.aspx). Del mismo modo, queremos proporcionar un número de cadenas que comiencen con algo que no sea un carácter en mayúsculas. Esperamos que el método devuelva False en estos casos, por lo que podemos llamar al método [Assert.IsFalse (Boolean, String)](https://msdn.microsoft.com/library/ms243805.aspx).

Dado que nuestro método de biblioteca controla cadenas, queremos asegurarnos también de que controla correctamente una [cadena vacía](xref:System.String.Empty) (una cadena válida que no tenga caracteres y cuyo @System.String.Length sea 0) y una cadena `null` (una cadena que no se haya inicializado). Si `StartsWithUpper` se llama como un método de extensión en una instancia @System.String, no se puede pasar una cadena `null`. Sin embargo, también se puede llamar directamente como un método estático y pasar un solo argumento @System.String.

Definiremos tres métodos, cada uno de los cuales llama a su método [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) repetidamente para cada elemento de una matriz de cadenas. Dado que el método de prueba produce error tan pronto como encuentra el primer error, llamaremos a una sobrecarga de método que nos permita pasar una cadena que indique el valor de cadena usado en la llamada al método.

Para crear los métodos de prueba:

1. Reemplace el código de la ventana de código por el código siguiente:

   [!CODE-csharp[Prueba 1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs#1)]

   Observe que la prueba de caracteres en mayúsculas del método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U+0391) y la letra mayúscula cirílica EM (U+041C), y la prueba de caracteres en minúsculas del método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U+03B1) y la letra cirílica minúscula Ghe (U+0433).

1. En la barra de menú, seleccione **Archivo**, **Guardar UnitTest1.cs como...**. En el cuadro de diálogo **Guardar archivo como**, seleccione la flecha junto al botón **Guardar** y, a continuación, seleccione **Guardar con codificación...***.

1. En el cuadro de diálogo Confirmar guardar como, seleccione el botón **Sí** para guardar el archivo.

1. En la lista desplegable **Codificación** del cuadro de diálogo **Opciones avanzadas para guardar**, seleccione **Unicode (UTF-8 con signatura) - Página de códigos 65001** y luego seleccione **Aceptar**.

   Si le da error al guardar el código fuente en un archivo con codificación UTF8, Visual Studio puede guardarlo como un archivo ASCII. En ese caso, el tiempo de ejecución no decodificará con precisión caracteres fuera del rango ASCII y los resultados de la prueba no serán precisos.

1. En la barra de menú, seleccione **Prueba**, **Ejecutar**, **Todas las pruebas**. La ventana **Explorador de pruebas** se abrirá y mostrará que ambas pruebas se han ejecutado correctamente, como se muestra en la siguiente ilustración. Tenga en cuenta que las tres pruebas se muestran en la sección **Pruebas superadas** y en la sección **Resumen** se informa del resultado de la serie de pruebas.

   ![Imagen](./media/first_test.jpg)

## <a name="handling-test-failures"></a>Control de errores en las pruebas ##

Nuestra serie de pruebas no tuvo errores, así que vamos a cambiarla un poco para que uno de los métodos de prueba produzca error:

1. Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error", para que la instrucción indique lo siguiente:

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Ejecute la prueba; para ello, seleccione **Prueba**, **Ejecutar**, **Todas las pruebas**. La ventana **Explorador de pruebas** ahora indica que dos pruebas se han realizado correctamente y una ha dado error, como se muestra en la siguiente ilustración.

   ![Imagen](./media/failed_test.jpg)

1. Seleccione la prueba que ha dado error, `TestDoesNotStartWith`, en la sección **Pruebas no superadas**. El panel inferior del **Explorador de pruebas** muestra el mensaje generado por la aserción: "Assert.IsFalse failed. Expected for 'Error': false; actual: True", como muestra la siguiente ilustración del **Explorador de pruebas**. Debido al error, no se probaron todas las cadenas de la matriz después de "Error".

   ![Imagen](./media/failed_test2.jpg)

1. Quite el código que se ha agregado (`"Error", `) y vuelva a ejecutar la prueba. Ahora debería superarse.

## <a name="testing-the-release-version-of-the-library"></a>Prueba de la versión de la biblioteca ##

Hemos estado ejecutando nuestras pruebas con la versión de depuración de la biblioteca. Ahora que todas nuestras pruebas se han superado y que hemos probado adecuadamente nuestra biblioteca, debemos ejecutar las pruebas un tiempo adicional con respecto a la compilación de versión de la biblioteca. Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.

Para probar la compilación de versión:

1. En la barra de herramientas de Visual Studio, cambie la configuración de compilación de **Depurar** a **Versión**. La siguiente ilustración muestra una parte de la barra de herramientas.

   ![Imagen](./media/lib_release.jpg)

1. En el **Explorador de soluciones**, abra el menú contextual para el nodo de proyecto **StringLibrary** y seleccione **Compilar** para volver a compilar la biblioteca.

1. Vuelva a ejecutar las pruebas unitarias seleccionando **Prueba**, **Ejecutar**, **Todas las pruebas** del menú de Visual Studio. Todas las pruebas deberían superarse.

Ahora que ha terminado de probar la biblioteca, el siguiente paso es ponerla a disposición de los llamadores. Puede empaquetarla con una o varias aplicaciones o puede distribuirla como un paquete NuGet. Para más información al respecto, consulte [Consumo de una biblioteca de clases .NET Standard](./consuming-library-with-visual-studio-2017.md).

