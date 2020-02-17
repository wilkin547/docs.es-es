---
title: Creación de una solución completa de .NET Core con Visual Studio para Mac
description: Este artículo le guía en la creación de una solución .NET Core que incluye una biblioteca reutilizable y pruebas unitarias.
ms.date: 12/19/2019
ms.openlocfilehash: dea23da33912de849f0dcbe1e2f6fa3edb3a5e24
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215197"
---
# <a name="build-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a>Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac

Visual Studio para Mac proporciona un entorno de desarrollo integrado (IDE) completo para el desarrollo de aplicaciones .NET Core. Este artículo le guía en la creación de una solución .NET Core que incluye una biblioteca reutilizable y pruebas unitarias.

En este tutorial se muestra cómo crear una aplicación que acepte una palabra de búsqueda y una cadena de texto del usuario, cuente el número de veces que la palabra de búsqueda aparece en la cadena utilizando un método en una biblioteca de clases, y devuelva el resultado al usuario. La solución también incluye pruebas unitarias para la biblioteca de clases como una introducción a los conceptos de pruebas unitarias. Si prefiere continuar usando el tutorial con un ejemplo completo, descargue la [solución de ejemplo](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter). Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

> [!NOTE]
> Sus comentarios son muy importantes. Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:
>
> - En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores. Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/41/index.html).
> - Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 3.1 o posterior](https://dotnet.microsoft.com/download)
- [Visual Studio 2019 para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

Para obtener más información sobre los requisitos previos, vea [Dependencias y requisitos de .NET Core](../install/dependencies.md?pivots=os-macos). Para consultar todos los requisitos del sistema de Visual Studio 2019 para Mac, vea [Requisitos del sistema de la familia de productos de Visual Studio 2019 para Mac](/visualstudio/productinfo/vs2019-system-requirements-mac).

## <a name="building-a-library"></a>Creación de una biblioteca

1. En la ventana de inicio, seleccione **Nuevo proyecto**. En el cuadro de diálogo **Nuevo proyecto**, en el nodo **.NET Core**, seleccione la plantilla **Biblioteca de .NET Standard**. Este comando crea una biblioteca de .NET Standard que tiene como destino .NET Core, así como cualquier otra implementación de .NET que admite la versión 2.1 de [.NET Standard](../../standard/net-standard.md). Si tiene varias versiones del SDK de .NET Core instaladas, puede elegir diferentes versiones de .NET Standard para la biblioteca. Elija ".NET Standard 2.1" y seleccione **Siguiente**.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo Nuevo proyecto de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)

1. Asigne al proyecto el nombre "TextUtils" (un nombre corto para "Text Utilities") y la solución "WordCounter". Deje activada la opción **Cree un directorio de proyecto dentro del directorio de la solución**. Seleccione **Crear**.

   > [!div class="mx-imgBorder"]
   > ![Opciones del cuadro de diálogo Nuevo proyecto de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)

1. En el panel **Solución**, expanda el nodo `TextUtils` para mostrar el archivo de clase proporcionado por la plantilla *Class1.cs*. Ctrl+clic en el archivo, seleccione **Cambiar nombre** en el menú contextual y denomínelo *WordCount.cs*. Abra el archivo y reemplace el contenido por el código siguiente:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. Guarde el archivo mediante uno de estos tres métodos: use el método abreviado de teclado <kbd>&#8984;</kbd>+<kbd>s</kbd>, seleccione **Archivo** > **Guardar** en el menú o use Ctrl+clic en la pestaña del archivo y seleccione **Guardar** en el menú contextual. La siguiente imagen muestra la ventana de IDE:

   > [!div class="mx-imgBorder"]
   > ![Ventana del IDE de Visual Studio para Mac con el archivo de biblioteca de clase y el método](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)

1. Seleccione **Errores** en el margen inferior de la ventana de IDE para abrir el panel **Errores**. Seleccione el botón **Salida de la compilación**.

   > [!div class="mx-imgBorder"]
   > ![Margen inferior del IDE de Visual Studio para Mac con el botón Errores](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)

1. Seleccione **Compilar** > **Compilar todo** en el menú.

   La solución se compila. El panel de salida de la compilación muestra que la compilación es correcta.

   > [!div class="mx-imgBorder"]
   > ![Panel de salida de la compilación de Visual Studio para Mac del panel Errores con el mensaje de compilación correcta](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)

## <a name="creating-a-test-project"></a>Creación de un proyecto de prueba

Las pruebas unitarias proporcionan pruebas de software automatizadas durante el desarrollo y la publicación. El marco de pruebas que se utiliza en este tutorial es [xUnit (versión 2.4.0 o una versión posterior)](https://xunit.github.io/), que se instala automáticamente cuando el proyecto de prueba de xUnit se agrega a la solución en los pasos siguientes:

1. En la barra lateral **Solución**, use Ctrl+clic en la solución `WordCounter` y seleccione **Agregar** > **Agregar nuevo proyecto**.

1. En el cuadro de diálogo **Nuevo proyecto**, seleccione **Pruebas** en el nodo **.NET Core**. Seleccione el **proyecto de prueba xUnit** y haga clic en **Siguiente**.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo Nuevo proyecto de Visual Studio para Mac con un proyecto de prueba xUnit](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)

1. Si tiene varias versiones del SDK de .NET Core, deberá seleccionar la versión para este proyecto. Seleccione **.NET Core 3.1**. Asigne al nuevo proyecto el nombre "TestLibrary" y seleccione **Crear**.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo Nuevo proyecto de Visual Studio para Mac en el que se proporciona el nombre del proyecto](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)

1. Para que la biblioteca de prueba funcione con la clase `WordCount`, agregue una referencia al proyecto `TextUtils`. En la barra lateral **Solución**, use Ctrl+clic en **Dependencias** en **TestLibrary**. Seleccione **Editar referencias** en el menú contextual.

1. En el cuadro de diálogo **Editar referencias**, seleccione el proyecto **TextUtils** en la pestaña **Proyectos**. Seleccione **Aceptar**.

   > [!div class="mx-imgBorder"]
   > ![Cuadro de diálogo Editar referencias de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)

1. En el proyecto **TestLibrary**, cambie el nombre del archivo *UnitTest1.cs* por *TextUtilsTests.cs*.

1. Abra el archivo y reemplace el código por el código siguiente:

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");

               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   La siguiente imagen muestra el IDE con el código de prueba unitaria en su lugar. Preste atención a la instrucción `Assert.NotEqual`.

   > [!div class="mx-imgBorder"]
   > ![Prueba unitaria inicial de Visual Studio para Mac en la ventana principal del IDE](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)

   Es importante que una prueba nueva no se supere por lo menos en una ocasión, ya que, de este modo, se puede confirmar que su lógica de prueba es correcta. El método pasa el nombre "Jack" (en mayúsculas) y una cadena con "Jack" y "jack" (mayúsculas y minúsculas). Si el método `GetWordCount` funciona correctamente, devuelve un recuento de dos instancias de la palabra de búsqueda. Para que la prueba no se supere a propósito, primero implementará la prueba afirmando que el método `GetWordCount` no devuelve dos instancias de la palabra de búsqueda "Jack". Continúe con el paso siguiente para no superar la prueba a propósito.

1. Abra el panel **Pruebas unitarias** en el lado derecho de la pantalla. En el menú, seleccione **Ver** > **Pruebas**.

   > [!div class="mx-imgBorder"]
   > ![Panel Pruebas unitarias de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)

1. Haga clic en el icono **Acoplar** para mantener abierto el panel. (Resaltado en la siguiente imagen).

   > [!div class="mx-imgBorder"]
   > ![Icono de acoplamiento del panel Pruebas unitarias de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)

1. Haga clic en el botón **Ejecutar todas**.

   La prueba no se supera, que es el resultado correcto. El método de prueba afirma que dos instancias de `inputString`, "Jack", no se devuelve de la cadena "Jack jack", proporciona al método `GetWordCount`. Puesto que la distinción de mayúsculas y minúsculas se ha factorizado en el método `GetWordCount`, se devuelven dos instancias. La aserción de que 2 *no es igual a* 2 produce un error. Este es el resultado correcto y la lógica de nuestra prueba es buena.

   > [!div class="mx-imgBorder"]
   > ![Pantalla de error de prueba de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)

1. Modifique el método de prueba `IgnoreCasing` cambiando `Assert.NotEqual` por `Assert.Equal`. Guarde el archivo mediante el método abreviado de teclado <kbd>Ctrl</kbd>+<kbd>s</kbd>, **Archivo** > **Guardar** en el menú, o use Ctrl+clic en la pestaña del archivo y seleccione **Guardar** en el menú contextual.

   Se espera que el valor "Jack" de `searchWord` devuelva dos instancias con `inputString` "Jack jack" pasado a `GetWordCount`. Vuelva a ejecutar la prueba; para ello, haga clic en el botón **Ejecutar pruebas** en el panel **Pruebas unitarias** o en el botón **Volver a ejecutar pruebas** en el panel **Resultados de pruebas** en la parte inferior de la pantalla. La prueba se supera. Hay dos instancias de "Jack" en la cadena "Jack jack" (se omite la distinción de mayúsculas y minúsculas) y la aserción de prueba es `true`.

   > [!div class="mx-imgBorder"]
   > ![Pantalla de pruebas superadas de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

1. Probar los valores devueltos individuales con un elemento `Fact` es solo el comienzo de lo que se puede hacer con las pruebas unitarias. Otra técnica eficaz le permite probar varios valores a la vez mediante un elemento `Theory`. Agregue el siguiente método a la clase `TextUtils_GetWordCountShould`. Después de agregar este método tiene dos métodos en la clase:

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count,
                                       string searchWord,
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   El método `CountInstancesCorrectly` comprueba que el método `GetWordCount` cuenta correctamente. El método `InlineData` proporciona un recuento, una palabra de búsqueda y una cadena de entrada para comprobar. El método de prueba se ejecuta una vez por cada línea de datos. Una vez más, observe que está afirmando un error primero mediante `Assert.NotEqual`, aunque sabe que los recuentos de los datos son correctos y que los valores coincidirán con los recuentos devueltos por el método `GetWordCount`. Realizar el paso de no superar la prueba a propósito podría parecer una pérdida de tiempo al principio, pero comprobar la lógica de la prueba de esta manera es una comprobación importante en la lógica de las pruebas. Si se encuentra con un método de prueba que se supera cuando espera que no lo haga, habrá encontrado un error en la lógica de la prueba. Merece la pena el esfuerzo de realizar este paso cada vez que crea un método de prueba.

1. Guarde el archivo y vuelva a ejecutar las pruebas. La prueba de distinción de mayúsculas y minúsculas se supera pero las tres pruebas de recuento no. Este resultado es exactamente lo que espera que ocurra.

   > [!div class="mx-imgBorder"]
   > ![Error de prueba esperado de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)

1. Modifique el método de prueba `CountInstancesCorrectly` cambiando `Assert.NotEqual` por `Assert.Equal`. Guarde el archivo. Vuelva a ejecutar las pruebas. Todas las pruebas se superan.

   > [!div class="mx-imgBorder"]
   > ![Prueba superada esperada de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

## <a name="adding-a-console-app"></a>Adición de una aplicación de consola

1. En la barra lateral **Solución**, use Ctrl+clic en la solución `WordCounter`. Agregue un nuevo proyecto de **aplicación de consola**; para ello, seleccione la plantilla en **.NET Core** > **Aplicación**. Seleccione **Siguiente**. Nombre al proyecto **WordCounterApp**. Seleccione **Crear** para crear el proyecto en la solución.

1. En la barra lateral **Soluciones**, use Ctrl+clic en el nodo **Dependencias** del nuevo proyecto **WordCounterApp**. En el cuadro de diálogo **Editar referencias**, marque **TextUtils** y seleccione **Aceptar**.

1. Abra el archivo *Program.cs*. Reemplace el código por el siguiente código:

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. Use Ctrl+clic en el proyecto `WordCounterApp` y seleccione **Ejecutar el proyecto** en el menú contextual. Al ejecutar la aplicación, proporcione valores para la palabra de búsqueda y la cadena de entrada en los mensajes de la ventana de consola. La aplicación indica el número de veces que aparece la palabra de búsqueda en la cadena.

   > [!div class="mx-imgBorder"]
   > ![Ventana de la consola de Visual Studio para Mac en la que se muestra la aplicación en ejecución](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)

1. La última característica para explorar es la depuración con Visual Studio para Mac. Establezca un punto de interrupción en la instrucción `Console.WriteLine`: selecciónelo en el margen izquierdo de la línea 23 y verá un círculo de color rojo junto a la línea de código. Como alternativa, seleccione cualquier parte de la línea de código y seleccione **Ejecutar** > **Alternar puntos de interrupción** en el menú.

   > [!div class="mx-imgBorder"]
   > ![Punto de interrupción establecido en Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)

1. Use Ctrl+clic en el proyecto `WordCounterApp`. Seleccione **Iniciar depuración del proyecto** en el menú contextual. Cuando se ejecute la aplicación, escriba la palabra de búsqueda "cat" (gato) y la cadena "The dog chased the cat, but the cat escaped" (El perro persiguió el gato, pero el gato se escapó) que se va a buscar. Cuando se llegue a la instrucción `Console.WriteLine`, la ejecución del programa se detiene antes de que se ejecute la instrucción. En la pestaña **Variables locales**, puede ver los valores `searchWord`, `inputString`, `wordCount` y `pluralChar`.

   > [!div class="mx-imgBorder"]
   > ![Detección de la ejecución del programa depurador de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)

1. En el panel **Inmediato**, escriba "wordCount = 999;" y presione Entrar. Este comando asigna un valor absurdo de 999 a la variable `wordCount`, lo que demuestra que puede sustituir valores de variables durante la depuración.

   > [!div class="mx-imgBorder"]
   > ![Cambio de valores en la ventana Inmediato de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)

1. En la barra de herramientas, haga clic en la flecha para *continuar*. Examine la salida en la ventana de consola. Notifica el valor incorrecto de 999 que estableció cuando estaba depurando la aplicación.

   > [!div class="mx-imgBorder"]
   > ![Botón Continuar en la barra de herramientas de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)

   > [!div class="mx-imgBorder"]
   > ![Salida de la ventana de consola de Visual Studio para Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)

Puede usar el mismo proceso para depurar el código mediante el proyecto de prueba unitaria. En lugar de iniciar el proyecto de aplicación WordCount, use Ctrl+clic en el proyecto **Biblioteca de pruebas** y seleccione **Iniciar depuración del proyecto** en el menú contextual. Visual Studio para Mac inicia el proyecto de prueba con el depurador asociado. La ejecución se detendrá en cualquier punto de interrupción que haya agregado al proyecto de prueba o al código de la biblioteca subyacente.

## <a name="see-also"></a>Vea también

- [Notas de la versión de Visual Studio 2019 para Mac](/visualstudio/releasenotes/vs2019-mac-relnotes)
