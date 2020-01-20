---
title: 'Tutorial: Programación de Office (C# y Visual Basic)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Office, programming in Visual Basic and C#
- Office programming [C#]
- Office programming [Visual Basic]
ms.assetid: 519cff31-f80b-4f0e-a56b-26358d0f8c51
ms.openlocfilehash: 6c27442cb5c0c4172f503c945849e47560c2b33d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635358"
---
# <a name="walkthrough-office-programming-c-and-visual-basic"></a>Tutorial: Programación de Office (C# y Visual Basic)

Visual Studio presenta características en C# y Visual Basic que mejoran la programación de Microsoft Office. Las características útiles de C# incluyen argumentos opcionales y con nombre, y devuelven valores de tipo `dynamic`. En la programación COM, puede omitir la palabra clave `ref` y obtener acceso a las propiedades indexadas. Las nuevas características de Visual Basic incluyen propiedades implementadas automáticamente, instrucciones de expresiones lambda e inicializadores de colección.

En ambos lenguajes se puede insertar información de tipo, lo que permite la implementación de ensamblados que interactúan con componentes COM sin necesidad de implementar ensamblados de interoperabilidad primarios (PIA) en el equipo del usuario. Para obtener más información, vea [Tutorial: Insertar los tipos de los ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md).

En este tutorial se muestran estas características en el contexto de la programación de Office, pero muchas de ellas también son útiles en la programación general. En el tutorial, usa una aplicación complemento de Excel para crear un libro de Excel. Después, crea un documento de Word que contiene un vínculo al libro. Por último, ve cómo habilitar y deshabilitar la dependencia de un PIA.

## <a name="prerequisites"></a>Requisitos previos

Debe tener Microsoft Office Excel y Microsoft Office Word instalados en su equipo para completar este tutorial.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-set-up-an-excel-add-in-application"></a>Para configurar una aplicación complemento de Excel

1. Inicie Visual Studio.

2. En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.

3. En el panel **Plantillas instaladas**, expanda **Visual Basic** o **Visual C#** , expanda **Office** y, después, haga clic en el año de la versión del producto de Office.

4. En el panel **Plantillas**, haga clic en **versión de \<Excel > Complemento**.

5. En la parte superior del panel **Plantillas**, asegúrese de que **.NET Framework 4** o una versión posterior aparece en el cuadro **Plataforma de destino**.

6. Si quiere, escriba un nombre para el proyecto en el cuadro **Nombre**.

7. Haga clic en **Aceptar**.

8. El proyecto nuevo aparece en el **Explorador de soluciones**.

### <a name="to-add-references"></a>Para agregar referencias

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto y luego haga clic en **Agregar referencia**. Aparecerá el cuadro de diálogo **Agregar referencia**.

2. En la pestaña **Ensamblados**, seleccione **Microsoft.Office.Interop.Excel**, versión `<version>.0.0.0` (para obtener una clave de los números de versión de productos de Office, vea [Versiones de Microsoft](https://en.wikipedia.org/wiki/Microsoft_Office#Versions)), en la lista **Nombre de componente** y, después, mantenga presionada la tecla CTRL y seleccione **Microsoft.Office.Interop.Word**, `version <version>.0.0.0`. Si no ve los ensamblados, asegúrese de que están instalados y que se muestran (vea [Cómo: Instalación de ensamblados de interoperabilidad primarios de Office](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies)).

3. Haga clic en **Aceptar**.

### <a name="to-add-necessary-imports-statements-or-using-directives"></a>Para agregar las instrucciones Imports necesarias o las directivas using

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo **ThisAddIn.vb** o **ThisAddIn.cs** y luego haga clic en **Ver código**.

2. Agregue las siguientes instrucciones `Imports` (Visual Basic) o directivas `using` (C#) en la parte superior del archivo de código si no están presentes.

     [!code-csharp[csOfficeWalkthrough#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#1)]

     [!code-vb[csOfficeWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#1)]

### <a name="to-create-a-list-of-bank-accounts"></a>Para crear una lista de las cuentas bancarias

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto, haga clic en **Agregar** y luego, en **Clase**. Denomine la clase Account.vb si está utilizando Visual Basic o Account.cs si está utilizando C#. Haga clic en **Agregar**.

2. Reemplace la definición de la clase `Account` por el código siguiente. Las definiciones de clase usan *propiedades implementadas automáticamente*. Para obtener más información, vea [Propiedades implementadas automáticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).

     [!code-csharp[csOfficeWalkthrough#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/account.cs#2)]

     [!code-vb[csOfficeWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/account.vb#2)]

3. Para crear una lista `bankAccounts` que contenga dos cuentas, agregue el código siguiente al método `ThisAddIn_Startup` en *ThisAddIn.vb* o *ThisAddIn.cs*. Las declaraciones de lista usan *inicializadores de colección*. Para obtener más información, vea [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

     [!code-csharp[csOfficeWalkthrough#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#3)]

     [!code-vb[csOfficeWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#3)]

### <a name="to-export-data-to-excel"></a>Para exportar datos a Excel

1. En el mismo archivo, agregue el siguiente método a la clase `ThisAddIn`. El método configura un libro de Excel, a donde exporta los datos.

     [!code-csharp[csOfficeWalkthrough#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#4)]

     [!code-vb[csOfficeWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#4)]

     En este método se utilizan dos características de C# nuevas. Ambas características ya existen en Visual Basic.

    - El método [Add](<xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A>) tiene un *parámetro opcional* para especificar una plantilla determinada. Los parámetros opcionales introducidos en C# 4 permiten omitir el argumento para ese parámetro si se desea utilizar el valor predeterminado del parámetro. Dado que en el ejemplo anterior no se envía ningún argumento, `Add` usa la plantilla predeterminada y crea un libro nuevo. La instrucción equivalente en versiones anteriores de C# requiere un argumento de marcador de posición: `excelApp.Workbooks.Add(Type.Missing)`.

         Para obtener más información, vea [Argumentos opcionales y con nombre](../classes-and-structs/named-and-optional-arguments.md).

    - Las propiedades `Range` y `Offset` del objeto [Range](<xref:Microsoft.Office.Interop.Excel.Range>) usan la característica de *propiedades indizadas*. Esta característica permite utilizar estas propiedades de los tipos COM mediante la siguiente sintaxis típica de C#. Las propiedades indizadas también permiten utilizar la propiedad `Value` del objeto `Range`, eliminando la necesidad de utilizar la propiedad `Value2`. La propiedad `Value` está indizada, pero el índice es opcional. Los argumentos opcionales y las propiedades indizadas funcionan conjuntamente en el ejemplo siguiente.

         [!code-csharp[csOfficeWalkthrough#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#5)]

         En las versiones anteriores del lenguaje, se requiere la siguiente sintaxis especial.

         [!code-csharp[csOfficeWalkthrough#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#6)]

         No es posible crear propiedades indizadas propias. La característica solo admite el uso de las propiedades indizadas existentes.

         Para más información, consulte [Procedimiento para usar propiedades indizadas en la programación de interoperabilidad COM](./how-to-use-indexed-properties-in-com-interop-rogramming.md).

2. Agregue el código siguiente al final de `DisplayInExcel` para ajustar los anchos de columna a fin de adaptarlos al contenido.

     [!code-csharp[csOfficeWalkthrough#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#7)]

     [!code-vb[csOfficeWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#7)]

     Estas adiciones muestran otra característica de C#: el tratamiento de valores `Object` devueltos por hosts COM, como Office, como si tuvieran un tipo [dynamic](../../language-reference/builtin-types/reference-types.md). Esto sucede automáticamente cuando **Incrustar tipos de interoperabilidad** se establece en su valor predeterminado `True` o, de igual modo, cuando la opción del compilador [-link](../../language-reference/compiler-options/link-compiler-option.md) hace referencia al ensamblado. El tipo `dynamic` permite el enlace en tiempo de ejecución, ya disponible en Visual Basic, y evita la conversión explícita que se requiere en C# 3.0 y versiones anteriores del lenguaje.

     Por ejemplo, `excelApp.Columns[1]` devuelve `Object` y `AutoFit` es un método [Range](<xref:Microsoft.Office.Interop.Excel.Range>) de Excel. Sin `dynamic`, debe convertir el objeto devuelto por `excelApp.Columns[1]` como una instancia de `Range` antes de llamar al método `AutoFit`.

     [!code-csharp[csOfficeWalkthrough#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#8)]

     Para obtener más información sobre cómo insertar tipos de interoperabilidad, consulte los procedimientos “Para buscar la referencia a un PIA” y “Para restaurar la dependencia de un PIA” más adelante en este tema. Para obtener más información sobre `dynamic`, vea [dynamic](../../language-reference/builtin-types/reference-types.md) o [Uso de tipo dinámico](../types/using-type-dynamic.md).

### <a name="to-invoke-displayinexcel"></a>Para invocar DisplayInExcel

1. Agregue el código siguiente al final del método `ThisAddIn_StartUp`. La llamada a `DisplayInExcel` contiene dos argumentos. El primer argumento es el nombre de la lista de cuentas que se va a procesar. El segundo argumento es una expresión lambda de varias líneas que define cómo se procesarán los datos. Los valores `ID` y `balance` de cada cuenta se muestran en las celdas adyacentes y la fila se muestra en rojo si el saldo es inferior a cero. Para obtener más información, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

     [!code-csharp[csOfficeWalkthrough#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#9)]

     [!code-vb[csOfficeWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#9)]

2. Presione F5 para ejecutar el programa. Aparece una hoja de cálculo de Excel que contiene los datos de las cuentas.

### <a name="to-add-a-word-document"></a>Para agregar un documento de Word

1. Agregue el código siguiente al final del método `ThisAddIn_StartUp` para crear un documento de Word que contenga un vínculo al libro de Excel.

     [!code-csharp[csOfficeWalkthrough#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csofficewalkthrough/cs/thisaddin.cs#10)]

     [!code-vb[csOfficeWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csofficewalkthrough/vb/thisaddin.vb#10)]

     Este código muestra algunas de las nuevas características de C#: capacidad para omitir la palabra clave `ref` en programación COM, argumentos con nombre y argumentos opcionales. Estas características ya existen en Visual Basic. El método [PasteSpecial](<xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>) tiene siete parámetros, y todos se definen como parámetros de referencia opcionales. Los argumentos opcionales y con nombre permiten designar los parámetros a los que se quiere tener acceso por nombre, y enviar argumentos únicamente a esos parámetros. En este ejemplo se envían argumentos para indicar que se debe crear un vínculo al libro en el Portapapeles (parámetro `Link`), y que el vínculo se mostrará en el documento de Word como un icono (parámetro `DisplayAsIcon`). Visual C# también le permite omitir la palabra clave `ref` para estos argumentos.

### <a name="to-run-the-application"></a>Para ejecutar la aplicación

1. Presione F5 para ejecutar la aplicación. Excel se abre y muestra una tabla que contiene la información de las dos cuentas de `bankAccounts`. Entonces aparece un documento de Word que contiene un vínculo a la tabla de Excel.

### <a name="to-clean-up-the-completed-project"></a>Para limpiar el proyecto completado

1. En Visual Studio, haga clic en **Limpiar solución** en el menú **Compilación**. De lo contrario, el complemento se ejecutará cada vez que abra Excel en el equipo.

### <a name="to-find-the-pia-reference"></a>Para buscar la referencia a un PIA

1. Ejecute de nuevo la aplicación, pero no haga clic en **Limpiar solución**.

2. Seleccione **Iniciar**. Busque **Microsoft Visual Studio \<versión>** y abra un símbolo del sistema del desarrollador.

3. Escriba `ildasm` en la ventana Símbolo del sistema para desarrolladores de Visual Studio y, luego, presione ENTRAR. Aparecerá la ventana IL DASM.

4. En el menú **Archivo** de la ventana de IL DASM, seleccione **Archivo** > **Abrir**. Haga doble clic en **Visual Studio \<versión>** y, después, haga doble clic en **Proyectos**. Abra la carpeta de su proyecto y, en la carpeta bin/Debug, busque *su_proyecto*.dll. Haga doble clic en *su_proyecto*.dll. Una nueva ventana muestra los atributos del proyecto, además de las referencias a otros módulos y ensamblados. Tenga en cuenta que los espacios de nombres `Microsoft.Office.Interop.Excel` y `Microsoft.Office.Interop.Word` se incluyen en el ensamblado. De manera predeterminada en Visual Studio, el compilador importa los tipos necesarios desde un PIA con referencia a su ensamblado.

     Para obtener más información, vea [Cómo: Consulta del contenido de un ensamblado](../../../standard/assembly/view-contents.md).

5. Haga doble clic en el icono **MANIFIESTO**. Aparecerá una ventana con una lista de ensamblados que contienen los elementos a los que hace referencia el proyecto. `Microsoft.Office.Interop.Excel` y `Microsoft.Office.Interop.Word` no están incluidos en la lista. Dado que los tipos que su proyecto necesita se han importado en el ensamblado, las referencias a un PIA no son necesarias. Esto facilita la implementación. Los PIA no tienen que estar presentes en el equipo del usuario y, puesto que una aplicación no requiere la implementación de una versión concreta de un PIA, se pueden diseñar aplicaciones que trabajen con varias versiones de Office, siempre que las API necesarias existan en todas las versiones.

     Dado que la implementación de los PIA ya no es necesaria, puede crear una aplicación en escenarios avanzados que funcione con varias versiones de Office, incluidas versiones anteriores. Sin embargo, esto solo funciona si el código no utiliza ninguna API que no esté disponible en la versión de Office con la que está trabajando. No siempre está claro si una API concreta estaba disponible en una versión anterior y por ese motivo no recomendamos trabajar con versiones anteriores de Office.

    > [!NOTE]
    > Office no publicó ensamblados PIA antes de Office 2003. Por lo tanto, la única manera de generar un ensamblado de interoperabilidad para Office 2002 o versiones anteriores es mediante la importación de la referencia COM.

6. Cierre la ventana del manifiesto y la del ensamblado.

### <a name="to-restore-the-pia-dependency"></a>Para restaurar la dependencia de un PIA

1. En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**. Expanda la carpeta **Referencias** y seleccione **Microsoft.Office.Interop.Excel**. Pulse F4 para abrir la ventana **Propiedades**.

2. En la ventana **Propiedades**, cambie la propiedad **Incrustar tipos de interoperabilidad** de **True** a **False**.

3. Repita los pasos 1 y 2 de este procedimiento para `Microsoft.Office.Interop.Word`.

4. En C#, marque como comentario las dos llamadas a `Autofit` al final del método `DisplayInExcel`.

5. Presione F5 para comprobar que el proyecto sigue ejecutándose correctamente.

6. Repita los pasos 1 a 3 del procedimiento anterior para abrir la ventana de ensamblado. Observe que `Microsoft.Office.Interop.Word` y `Microsoft.Office.Interop.Excel` ya no están en la lista de ensamblados insertados.

7. Haga doble clic en el icono **MANIFIESTO** y desplácese por la lista de ensamblados de referencia. Tanto `Microsoft.Office.Interop.Word` como `Microsoft.Office.Interop.Excel` están en la lista. Dado que la aplicación hace referencia a los PIA de Excel y Word y la propiedad **Incrustar tipos de interoperabilidad** se establece en **False**, ambos ensamblados deben existir en el equipo del usuario final.

8. En Visual Studio, haga clic en **Limpiar solución** en el menú **Compilación** para limpiar el proyecto completado.

## <a name="see-also"></a>Vea también

- [Propiedades implementadas automáticamente (Visual Basic)](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Propiedades autoimplementadas (C#)](../classes-and-structs/auto-implemented-properties.md)
- [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Inicializadores de objeto y colección](../classes-and-structs/object-and-collection-initializers.md)
- [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Paso de argumentos por posición o por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)
- [Argumentos opcionales y con nombre](../classes-and-structs/named-and-optional-arguments.md)
- [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Uso de tipo dinámico](../types/using-type-dynamic.md)
- [Expresiones lambda (Visual Basic)](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Expresiones lambda (C#)](../statements-expressions-operators/lambda-expressions.md)
- [Procedimiento para usar propiedades indizadas en la programación de interoperabilidad COM](./how-to-use-indexed-properties-in-com-interop-rogramming.md)
- [Tutorial: Inserción de información de tipos de los ensamblados de Microsoft Office en Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ee317478(v%3dvs.120))
- [Tutorial: Inserción de tipos de ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md)
- [Tutorial: Creación del primer complemento VSTO para Excel](/visualstudio/vsto/walkthrough-creating-your-first-vsto-add-in-for-excel)
- [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)
- [Interoperabilidad](./index.md)
