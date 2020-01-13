---
title: Procedimiento para usar argumentos opcionales y con nombre en la programación de Office - Guía de programación de C#
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 36b5c8b49404606c8240d24953c3677d5612d30e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714878"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>Procedimiento para usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)

Los argumentos con nombre y los argumentos opcionales, introducidos en C# 4, mejoran la comodidad, la flexibilidad y la legibilidad en la programación de C#. Además, estas características facilitan enormemente el acceso a interfaces COM, como las API de automatización de Microsoft Office.

En el ejemplo siguiente, el método [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) tiene dieciséis parámetros que representan las características de una tabla, como el número de columnas y filas, el formato, los bordes, las fuentes y los colores. Los dieciséis parámetros son opcionales, ya que la mayoría de las veces no interesa especificar valores concretos para todos ellos. Pero si no hay argumentos opcionales y con nombre, es necesario proporcionar un valor o un valor de marcador de posición para cada parámetro. Con los argumentos opcionales y con nombre, puede especificar valores solamente para los parámetros necesarios para el proyecto.

Debe tener Microsoft Office Word instalado en el equipo para completar estos procedimientos.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a>Para crear una aplicación de consola nueva

1. Inicie Visual Studio.

2. En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.

3. En el panel **Templates Categories** (Categorías de plantillas), expanda **Visual C#** y haga clic en **Windows**.

4. En la parte superior del panel **Plantillas**, asegúrese de que **.NET Framework 4** aparece en el cuadro **Plataforma de destino**.

5. En el panel **Plantillas**, haga clic en **Aplicación de consola**.

6. Escriba un nombre para el proyecto en el campo **Nombre**.

7. Haga clic en **Aceptar**.

     El proyecto nuevo aparece en el **Explorador de soluciones**.

## <a name="to-add-a-reference"></a>Para agregar una referencia

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto y seleccione **Agregar referencia**. Aparecerá el cuadro de diálogo **Agregar referencia**.

2. En la página **.NET**, seleccione **Microsoft.Office.Interop.Word** en la lista **Nombre de componente**.

3. Haga clic en **Aceptar**.

## <a name="to-add-necessary-using-directives"></a>Para agregar las directivas using necesarias

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Program.cs* y, después, haga clic en **Ver código**.

2. Agregue las directivas `using` siguientes a la parte superior del archivo de código:

     [!code-csharp[csProgGuideNamedAndOptional#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#4)]

## <a name="to-display-text-in-a-word-document"></a>Para mostrar texto en un documento de Word

1. En la clase `Program` en *Program.cs*, agregue el método siguiente para crear una aplicación de Word y un documento de Word. El método [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) tiene cuatro parámetros opcionales. En este ejemplo se usan los valores predeterminados. Por lo tanto, no se necesitan argumentos en la instrucción de llamada.

     [!code-csharp[csProgGuideNamedAndOptional#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#6)]

2. Agregue el código siguiente al final del método para definir dónde se muestra texto en el documento y qué texto se muestra:

     [!code-csharp[csProgGuideNamedAndOptional#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#7)]

## <a name="to-run-the-application"></a>Para ejecutar la aplicación

1. Agregue la instrucción siguiente a Principal:

     [!code-csharp[csProgGuideNamedAndOptional#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#8)]

2. Presione <kbd>CTRL</kbd>+<kbd>F5</kbd> para ejecutar el proyecto. Aparecerá un documento de Word con el texto especificado.

## <a name="to-change-the-text-to-a-table"></a>Para convertir el texto en tabla
  
1. Use el método `ConvertToTable` para incluir el texto en una tabla. El método tiene 16 parámetros opcionales. IntelliSense coloca los parámetros opcionales entre corchetes, tal como se muestra en la ilustración siguiente.

     ![Lista de parámetros para el método ConvertToTable](./media/how-to-use-named-and-optional-arguments-in-office-programming/convert-table-parameters.png)

     Los argumentos opcionales y con nombre permiten especificar valores solo para los parámetros que quiere cambiar. Agregue el código siguiente al final del método `DisplayInWord` para crear una tabla simple. El argumento especifica que las comas de la cadena de texto de `range` separan las celdas de la tabla.

     [!code-csharp[csProgGuideNamedAndOptional#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#9)]

     En versiones anteriores de C#, la llamada a `ConvertToTable` requiere un argumento de referencia para cada parámetro, tal como se muestra en el código siguiente:
  
     [!code-csharp[csProgGuideNamedAndOptional#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#14)]

2. Presione <kbd>CTRL</kbd>+<kbd>F5</kbd> para ejecutar el proyecto.

## <a name="to-experiment-with-other-parameters"></a>Para experimentar con otros parámetros

1. Para cambiar la tabla de modo que tenga una columna y tres filas, reemplace la última línea de `DisplayInWord` por la instrucción siguiente y escriba <kbd>CTRL</kbd>+<kbd>F5</kbd>.  

     [!code-csharp[csProgGuideNamedAndOptional#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#10)]

2. Para especificar un formato predefinido para la tabla, reemplace la última línea de `DisplayInWord` por la instrucción siguiente y escriba <kbd>CTRL</kbd>+<kbd>F5</kbd>. El formato puede ser cualquiera de las constantes [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>).

     [!code-csharp[csProgGuideNamedAndOptional#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#11)]

## <a name="example"></a>Ejemplo

En el código siguiente se incluye el ejemplo completo:

 [!code-csharp[csProgGuideNamedAndOptional#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#12)]

## <a name="see-also"></a>Vea también

- [Argumentos opcionales y con nombre](./named-and-optional-arguments.md)
