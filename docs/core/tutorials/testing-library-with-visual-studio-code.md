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
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio-code"></a>Tutorial: Prueba de una biblioteca .NET Standard con .NET Core en Visual Studio Code

En este tutorial se muestra cómo automatizar las pruebas unitarias mediante la adición de un proyecto de prueba a una solución.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la solución que se crea en [Creación de una biblioteca de .NET Standard en Visual Studio Code](library-with-visual-studio-code.md).

## <a name="create-a-unit-test-project"></a>Crear un proyecto de prueba unitaria

1. Abra Visual Studio Code.

1. Abra la solución `ClassLibraryProjects` que creó en [Creación de una biblioteca de .NET Standard en Visual Studio](library-with-visual-studio.md).

1. Cree un proyecto de prueba unitaria denominado "StringLibraryTest".

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   La plantilla de proyecto crea un archivo UnitTest1.cs con el código siguiente:

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
   - Aplica el atributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> para definir `TestMethod1`.

   Cada método etiquetado con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) en una clase de prueba etiquetada con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) se ejecuta automáticamente cuando se ejecuta la prueba unitaria.

   > [!NOTE]
   > MSTest es uno de los tres marcos de pruebas entre los que puede elegir. Los otros son xUnit y nUnit.

1. Agregue el proyecto de prueba a la solución:

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

1. Cree una referencia de proyecto al proyecto de biblioteca de clases; para ello, ejecute el comando siguiente:

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

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

Dado que el método de biblioteca controla cadenas, también se recomienda asegurarse de que controla correctamente una [cadena vacía (`String.Empty`)](xref:System.String.Empty) y una cadena `null`. Una cadena vacía es aquella que no tiene ningún carácter y cuyo valor de <xref:System.String.Length> es 0. Una cadena `null` es aquella que no se ha inicializado. Se puede llamar a `StartsWithUpper` directamente como un método estático y pasar un argumento <xref:System.String> único. También puede llamar a `StartsWithUpper` como método de extensión en una variable de `string` asignada a `null`.

Definirá tres métodos, cada uno de los cuales llama a su método <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> repetidamente para cada elemento de una matriz de cadenas. Dado que el método de prueba produce un error tan pronto como encuentra el primer error, llamará a una sobrecarga de método que le permita pasar una cadena que indique el valor de cadena usado en la llamada al método.

Para crear los métodos de prueba:

1. Abra *StringLibraryTest/UnitTest1.cs* y reemplace todo el código por el siguiente.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   La prueba de caracteres en mayúsculas en el método `TestStartsWithUpper` incluye la letra mayúscula griega alfa (U + 0391) y la letra mayúscula cirílica EM (U + 041C). La prueba de caracteres en minúsculas en el método `TestDoesNotStartWithUpper` incluye la letra griega minúscula alfa (U + 03B1) y la letra cirílica minúscula Ghe (U + 0433).

1. Guarde los cambios.

1. Ejecute las pruebas:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   en la salida del terminal se indica que se han superado todas las pruebas.

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a>Administración de errores de prueba

Si está realizando el desarrollo controlado por pruebas (TDD), escribirá las pruebas, y estas generarán un error cuando las ejecute por primera vez. Después, agregará un código a la aplicación para que la prueba se realice correctamente. En este caso, ha creado la prueba después de escribir el código de la aplicación que valida, por lo que no ha podido comprobar si la prueba genera un error. Para asegurarse de que una prueba genera un error cuando espera que lo haga, agregue un valor no válido a la entrada de prueba.

1. Modifique la matriz `words` en el método `TestDoesNotStartWithUpper` para incluir la cadena "Error".

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Ejecute las pruebas:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   en la salida del terminal se indica que se produce un error en una prueba y se proporciona un mensaje de error para la prueba con errores.

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

1. Deshaga la modificación que hizo en el paso 1 y quite la cadena "Error". Vuelva a ejecutar la prueba y se superarán las pruebas.

## <a name="test-the-release-version-of-the-library"></a>Prueba de la versión de la biblioteca

Ahora que se han superado todas las pruebas al ejecutar la versión de depuración de la biblioteca, ejecute las pruebas una vez más en la versión de lanzamiento de la biblioteca. Varios factores, como las optimizaciones del compilador, a veces pueden producir un comportamiento diferente entre las compilaciones de depuración y versión.

1. Ejecute las pruebas con la configuración de compilación Versión:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   Las pruebas se superan.

## <a name="additional-resources"></a>Recursos adicionales

- [Pruebas unitarias en .NET Core y .NET Standard](../testing/index.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha realizado una prueba unitaria de una biblioteca de clases. Puede poner la biblioteca a disposición de otros usuarios si la publica en [NuGet](https://nuget.org) como un paquete. Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:

> [!div class="nextstepaction"]
> [Creación y publicación de un paquete con la CLI de dotnet](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

Si publica una biblioteca como un paquete NuGet, otros usuarios pueden instalarla y usarla. Para obtener información sobre cómo hacerlo, realice este tutorial de NuGet:

> [!div class="nextstepaction"]
> [Instalar y usar un paquete con la CLI de dotnet](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

No es necesario distribuir una biblioteca como un paquete. Se puede agrupar con una aplicación de consola que la use. Para aprender a publicar una aplicación de consola, vea el tutorial anterior de esta serie:

> [!div class="nextstepaction"]
> [Publicación de una aplicación de consola de .NET Core con Visual Studio Code](publishing-with-visual-studio-code.md)
