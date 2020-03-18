---
title: 'Procedimiento Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
ms.openlocfilehash: b5d2da011ec6318c8b07f1eb4d383a4d56488239
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700840"
---
# <a name="how-to-access-office-interop-objects-c-programming-guide"></a>Procedimiento Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)

C# tiene nuevas características que simplifican el acceso a objetos de la API de Office. Las nuevas características incluyen argumentos con nombre y opcionales, un nuevo tipo llamado `dynamic` y la capacidad de pasar argumentos a parámetros de referencia en los métodos COM como si fueran parámetros de valor.

En este tema se utilizarán las nuevas características para escribir código que crea y muestra una hoja de cálculo de Microsoft Office Excel. A continuación, se escribirá código para agregar un documento de Office Word que contiene un icono que está vinculado a la hoja de cálculo de Excel.

Para completar este tutorial, es necesario tener Microsoft Office Excel 2007 y Microsoft Office Word 2007 —o una versión posterior— instalados en el equipo.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a>Para crear una aplicación de consola nueva

1. Inicie Visual Studio.

2. En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**. Aparecerá el cuadro de diálogo **Nuevo proyecto** .

3. En el panel **Plantillas instaladas**, expanda **Visual C#** y haga clic en **Windows**.

4. En la parte superior del cuadro de diálogo **Nuevo proyecto**, compruebe si **.NET Framework 4** (o una versión posterior) está seleccionado como una plataforma de destino.

5. En el panel **Plantillas**, haga clic en **Aplicación de consola**.

6. Escriba un nombre para el proyecto en el campo **Nombre**.

7. Haga clic en **Aceptar**.

     El proyecto nuevo aparece en el **Explorador de soluciones**.

## <a name="to-add-references"></a>Para agregar referencias

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto y luego haga clic en **Agregar referencia**. Aparecerá el cuadro de diálogo **Agregar referencia**.

2. En la página de **Ensamblados**, seleccione **Microsoft.Office.Interop.Word** en la lista **Nombre de componente** y, después, mantenga presionada la tecla CTRL y seleccione **Microsoft.Office.Interop.Excel**.  Si no ve los ensamblados, asegúrese de que están instalados y que se muestran. Vea [Cómo: Instalación de ensamblados de interoperabilidad primarios de Office](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies).

3. Haga clic en **Aceptar**.

## <a name="to-add-necessary-using-directives"></a>Para agregar las directivas using necesarias

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *Program.cs* y, después, haga clic en **Ver código**.

2. Agregue las directivas `using` siguientes a la parte superior del archivo de código:

     [!code-csharp[csProgGuideOfficeHowTo#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#1)]

## <a name="to-create-a-list-of-bank-accounts"></a>Para crear una lista de las cuentas bancarias

1. Pegue la definición de clase siguiente en **Program.cs**, bajo la clase `Program`.

     [!code-csharp[csProgGuideOfficeHowTo#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#2)]

2. Agregue el código siguiente al método `Main` para crear una lista `bankAccounts` lista que contenga dos cuentas.

     [!code-csharp[csProgGuideOfficeHowTo#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#3)]

## <a name="to-declare-a-method-that-exports-account-information-to-excel"></a>Para declarar un método que exporta información de cuentas a Excel

1. Agregue el método siguiente a la clase `Program` para configurar una hoja de cálculo de Excel.

     El método <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> tiene un parámetro opcional para especificar una plantilla determinada. Los parámetros opcionales introducidos en C# 4 permiten omitir el argumento para ese parámetro si se desea utilizar el valor predeterminado del parámetro. Dado que en el código siguiente no se envía ningún argumento, `Add` usa la plantilla predeterminada y crea un libro nuevo. La instrucción equivalente en versiones anteriores de C# requiere un argumento de marcador de posición: `ExcelApp.Workbooks.Add(Type.Missing)`.

     [!code-csharp[csProgGuideOfficeHowTo#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#4)]

2. Agregue el siguiente código al final de `DisplayInExcel`. El código inserta valores en las dos primeras columnas de la primera fila de la hoja de cálculo.

     [!code-csharp[csProgGuideOfficeHowTo#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#5)]

3. Agregue el siguiente código al final de `DisplayInExcel`. El bucle `foreach` coloca la información de la lista de cuentas en las dos primeras columnas de filas sucesivas de la hoja de cálculo.

     [!code-csharp[csProgGuideOfficeHowTo#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#7)]

4. Agregue el código siguiente al final de `DisplayInExcel` para ajustar los anchos de columna a fin de adaptarlos al contenido.

     [!code-csharp[csProgGuideOfficeHowTo#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#13)]

     Las versiones anteriores de C# requieren una conversión explícita para estas operaciones, ya que `ExcelApp.Columns[1]` devuelve `Object` y `AutoFit` es un método <xref:Microsoft.Office.Interop.Excel.Range> de Excel. Las siguientes líneas muestran la conversión.

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

     C# 4, y versiones posteriores, convierte automáticamente el valor `Object` devuelto en `dynamic` si se hace referencia al ensamblado mediante la opción del compilador [-link](../../language-reference/compiler-options/link-compiler-option.md) o, de forma equivalente, si la propiedad **Incrustar tipos de interoperabilidad** de Excel se establece en true. El valor predeterminado de esta propiedad es true.

## <a name="to-run-the-project"></a>Para ejecutar el proyecto

1. Agregue la línea siguiente al final de `Main`.

     [!code-csharp[csProgGuideOfficeHowTo#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#8)]

2. Presione CTRL+F5.

     Aparece una hoja de cálculo de Excel que contiene los datos de las dos cuentas.

## <a name="to-add-a-word-document"></a>Para agregar un documento de Word

1. Para ilustrar las formas adicionales en que C# 4, y versiones posteriores, mejoran la programación de Office, el código siguiente abre una aplicación de Word y crea un icono que se vincula a la hoja de cálculo de Excel.

     Pegue el método `CreateIconInWordDoc`, proporcionado más adelante en este paso, en la clase `Program`. `CreateIconInWordDoc` usa argumentos con nombre y opcionales para reducir la complejidad de las llamadas de método a <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> y <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>. Estas llamadas incorporan otras dos nuevas características introducidas en C# 4 que simplifican las llamadas a métodos COM que tienen parámetros de referencia. En primer lugar, puede enviar argumentos a los parámetros de referencia como si fueran parámetros de valor. Es decir, puede enviar valores directamente, sin necesidad de crear una variable para cada parámetro de referencia. El compilador genera variables temporales para contener los valores de argumento y las descarta cuando se regresa de la llamada. En segundo lugar, se puede omitir la palabra clave `ref` en la lista de argumentos.

     El método `Add` tiene cuatro parámetros de referencia, todos ellos opcionales. En C# 4.0 y versiones posteriores, puede omitir los argumentos de cualquiera o de todos los parámetros si quiere usar sus valores predeterminados. En C# 3.0 y versiones anteriores, se debe proporcionar un argumento para cada parámetro; el argumento debe ser una variable, ya que los parámetros son parámetros de referencia.

     El método `PasteSpecial` inserta el contenido del Portapapeles. El método tiene siete parámetros de referencia, todos ellos opcionales. El siguiente código especifica los argumentos para dos de ellos: `Link`, para crear un vínculo con el origen del contenido del Portapapeles, y `DisplayAsIcon`, para mostrar el vínculo como un icono. En C# 4.0 y versiones posteriores, puede usar argumentos con nombre para esos dos y omitir los demás. Aunque se trata de parámetros de referencia, no es necesario utilizar la palabra clave `ref` ni crear variables para enviarlas como argumentos. Puede enviar los valores directamente. En C# 3.0 y versiones anteriores, debe proporcionar un argumento de variable para cada parámetro de referencia.

     [!code-csharp[csProgGuideOfficeHowTo#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#9)]

     En C# 3.0 y versiones anteriores del lenguaje, es necesario el código siguiente, que es más complejo.

     [!code-csharp[csProgGuideOfficeHowTo#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#10)]

2. Agregue la siguiente instrucción al final de `Main`.

     [!code-csharp[csProgGuideOfficeHowTo#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#11)]

3. Agregue la siguiente instrucción al final de `DisplayInExcel`. El método `Copy` agrega la hoja de cálculo en el Portapapeles.

     [!code-csharp[csProgGuideOfficeHowTo#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#12)]

4. Presione CTRL+F5.

     Un documento de Word aparecerá con un icono. Haga doble clic en el icono para abrir la hoja de cálculo en primer plano.

## <a name="to-set-the-embed-interop-types-property"></a>Para establecer la propiedad Incrustar tipos de interoperabilidad

1. Es posible realizar mejoras adicionales si se llama a un tipo COM que no requiere un ensamblado de interoperabilidad primario (PIA) en tiempo de ejecución. Si se elimina la dependencia de PIA, la versión gana en independencia y se facilita la implementación. Para obtener más información sobre las ventajas de la programación sin PIA, consulte [Tutorial: Insertar los tipos de los ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md).

     Además, programar resulta más fácil porque los tipos requeridos y devueltos por los métodos COM se pueden representar con el tipo `dynamic` en vez de `Object`. Las variables de tipo `dynamic` no se evalúan hasta el tiempo de ejecución, lo que elimina la necesidad de la conversión explícita. Para obtener más información, vea [Uso del tipo dynamic](../types/using-type-dynamic.md).

     En C# 4, el comportamiento predeterminado es insertar información de tipos en lugar de utilizar los PIA. Debido a ese comportamiento predeterminado, algunos de los ejemplos anteriores se simplifican dado que no es necesaria la conversión explícita. Por ejemplo, la declaración de `worksheet` en `DisplayInExcel` se escribe como `Excel._Worksheet workSheet = excelApp.ActiveSheet` en lugar de `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`. Las llamadas a `AutoFit` en el mismo método también requerirían conversión explícita sin el valor predeterminado, porque `ExcelApp.Columns[1]` devuelve un `Object` y `AutoFit` es un método de Excel. En el código siguiente se muestra la conversión.

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

2. Para cambiar el valor predeterminado y usar los PIA en lugar de insertar información de tipos, expanda el nodo **Referencias** del **Explorador de soluciones** y, después, seleccione **Microsoft.Office.Interop.Excel** o **Microsoft.Office.Interop.Word**.

3. Si no ve la ventana **Propiedades**, presione **F4**.

4. Busque **Incrustar tipos de interoperabilidad** en la lista de propiedades y cambie su valor a **False**. Del mismo modo, se puede compilar mediante el uso de la opción del compilador [-reference](../../language-reference/compiler-options/reference-compiler-option.md) en lugar de [-link](../../language-reference/compiler-options/link-compiler-option.md) en un símbolo del sistema.

## <a name="to-add-additional-formatting-to-the-table"></a>Para agregar formato adicional a la tabla

1. Reemplace las dos llamadas a `AutoFit` en `DisplayInExcel` con la siguiente instrucción.

     [!code-csharp[csProgGuideOfficeHowTo#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#15)]

     El método <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> tiene siete parámetros de valor, todos ellos opcionales. Los argumentos con nombre y los argumentos opcionales permiten proporcionar argumentos para ninguno, algunos o todos ellos. En la instrucción anterior, se proporciona un argumento para uno solo de los parámetros, `Format`. Puesto que `Format` es el primer parámetro de la lista de parámetros, no es necesario proporcionar el nombre de parámetro. Sin embargo, la instrucción sería más fácil de entender si se incluyese el nombre del parámetro, como se muestra en el código siguiente.

     [!code-csharp[csProgGuideOfficeHowTo#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#16)]

2. Presione CTRL+F5 para ver el resultado. Otros formatos se indican en la enumeración <xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat>.

3. Compare la instrucción del paso 1 con el siguiente código, que muestra los argumentos necesarios en C# 3.0 y versiones anteriores.

     [!code-csharp[csProgGuideOfficeHowTo#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#17)]

## <a name="example"></a>Ejemplo

En el código siguiente se muestra el ejemplo completo.

[!code-csharp[csProgGuideOfficeHowTo#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/walkthrough.cs#18)]

## <a name="see-also"></a>Vea también

- <xref:System.Type.Missing?displayProperty=nameWithType>
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Uso de tipo dinámico](../types/using-type-dynamic.md)
- [Argumentos opcionales y con nombre](../classes-and-structs/named-and-optional-arguments.md)
- [Procedimiento para usar argumentos opcionales y con nombre en la programación de Office](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
