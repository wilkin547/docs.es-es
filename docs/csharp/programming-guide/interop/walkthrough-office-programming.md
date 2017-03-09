---
title: "Tutorial: Programaci&#243;n de Office (C# y Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "programación en Office [C#]"
  - "programación en Office [Visual Basic]"
  - "Office, programar en Visual Basic y C#"
ms.assetid: 519cff31-f80b-4f0e-a56b-26358d0f8c51
caps.latest.revision: 46
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 46
---
# Tutorial: Programaci&#243;n de Office (C# y Visual Basic)
[!INCLUDE[vs_dev10_long](../../../csharp/programming-guide/interop/includes/vs-dev10-long-md.md)] presenta características nuevas en C\# y Visual Basic que mejoran la programación de Microsoft Office.  Cada lenguaje ha agregado características que ya existen en el otro idioma.  
  
 Entre las nuevas características de C\# se incluyen argumentos opcionales y con nombre, valores devueltos de tipo `dynamic` y, en la programación COM, la capacidad para omitir la palabra clave `ref` y tener acceso a las propiedades indizadas.  Entre las nuevas características de Visual Basic se incluyen propiedades implementadas automáticamente, instrucciones de expresiones lambda e inicializadores de colección.  
  
 En ambos lenguajes se puede insertar información de tipo, lo que permite la implementación de ensamblados que interactúan con componentes COM sin necesidad de implementar ensamblados de interoperabilidad primarios \(PIA\) en el equipo del usuario.  Para obtener más información, vea [Tutorial: Incrustar los tipos de los ensamblados administrados](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Este tutorial muestra las nuevas características en el contexto de la programación de Office, pero muchas de ellas también son útiles en programación general.  En el tutorial, se utilizará primero una aplicación complemento de Excel para crear un libro de Excel.  Después se creará un documento de Word que contiene un vínculo al libro.  Por último, se verá cómo se puede activar y desactivar la dependencia de un PIA.  
  
## Requisitos previos  
 Debe tener Microsoft Office Excel 2013 \(o la versión 2007 o posterior\) y Microsoft Office Word 2013 \(o la versión 2007 o posterior\) instalados en el equipo para poder completar este tutorial.  
  
 Si usa un sistema operativo anterior a [!INCLUDE[windowsver](../../../csharp/programming-guide/interop/includes/windowsver-md.md)], asegúrese de que [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)] esté instalado.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para configurar una aplicación complemento de Excel  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto**.  
  
3.  En el panel **Plantillas instaladas**, expanda **Visual Basic** o **Visual C\#**, expanda **Office** y luego haga clic en **2013** \(o **2010** o **2007**\).  
  
4.  En el panel **Plantillas**, haga clic en **Complemento de Excel 2013** \(o **Complemento de Excel 2010** o **Complemento de Excel 2007**\).  
  
5.  En la parte superior del panel **Plantillas**, asegúrese de que **.NET Framework 4** o una versión posterior aparece en el cuadro **Marco de trabajo de destino**.  
  
6.  Si lo desea, escriba un nombre para el proyecto en el cuadro **Nombre**.  
  
7.  Haga clic en **Aceptar**.  
  
8.  El proyecto nuevo aparece en el **Explorador de soluciones**.  
  
### Para agregar referencias  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y seleccione **Agregar referencia**.  Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
2.  En la pestaña **Ensamblados**, seleccione **Microsoft.Office.Interop.Excel**, versión 15.0.0.0 \(o versión 14.0.0.0 para Excel 2010 o versión 12.0.0.0 para Excel 2007\) en la lista **Nombre de componente**, mantenga presionada la tecla CTRL y seleccione **Microsoft.Office.Interop.Word**, versión 15.0.0.0 \(o versión 14.0.0.0 para Word 2010 o 12.0.0.0 para Word 2007\).  Si no ve los ensamblados, asegúrese de que están instalados y que se muestran \(vea [Cómo: Instalar ensamblados de interoperabilidad primarios de Office](../Topic/How%20to:%20Install%20Office%20Primary%20Interop%20Assemblies.md)\).  
  
3.  Haga clic en **Aceptar**.  
  
### Para agregar las instrucciones Imports necesarias o las directivas using  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el archivo **ThisAddIn.vb** o **ThisAddIn.cs** y, a continuación, haga clic en **Ver código**.  
  
2.  Agregue las siguientes instrucciones `Imports` \(Visual Basic\) o directivas `using` \(C\#\) en la parte superior del archivo de código si no están presentes.  
  
     [!code-cs[csOfficeWalkthrough#1](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#1)]
     [!code-vb[csOfficeWalkthrough#1](../../../csharp/programming-guide/interop/codesnippet/visualbasic/officewalkthroughsnippets - vb/thisaddin.vb#1)]  
  
### Para crear una lista de las cuentas bancarias  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto, haga clic en **Agregar** y, a continuación, haga clic en **Clase**.  Denomine la clase Account.vb si está utilizando Visual Basic o Account.cs si está utilizando C\#.  Haga clic en **Agregar**.  
  
2.  Reemplace la definición de la clase `Account` por el código siguiente.  Las definiciones de clase usan *propiedades autoimplementadas*, lo que supone una novedad para Visual Basic en Visual Studio 2010.  Para obtener más información, vea [Propiedades autoimplementadas](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
     [!code-cs[csOfficeWalkthrough#2](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/account.cs#2)]
     [!code-vb[csOfficeWalkthrough#2](../../../csharp/programming-guide/interop/codesnippet/visualbasic/officewalkthroughsnippets - vb/account.vb#2)]  
  
3.  Para crear una lista `bankAccounts` que contenga dos cuentas, agregue el código siguiente al método `ThisAddIn_Startup` en ThisAddIn.vb o ThisAddIn.cs.  Las declaraciones de lista usan *inicializadores de colección*, lo que supone una novedad para Visual Basic en Visual Studio 2010.  Para obtener más información, vea [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).  
  
     [!code-cs[csOfficeWalkthrough#3](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#3)]
     [!code-vb[csOfficeWalkthrough#3](../../../csharp/programming-guide/interop/codesnippet/visualbasic/officewalkthroughsnippets - vb/thisaddin.vb#3)]  
  
### Para exportar datos a Excel  
  
1.  En el mismo archivo, agregue el siguiente método a la clase `ThisAddIn`.  El método configura un libro de Excel, a donde exporta los datos.  
  
     [!code-cs[csOfficeWalkthrough#4](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#4)]
     [!code-vb[csOfficeWalkthrough#4](../../../csharp/programming-guide/interop/codesnippet/visualbasic/officewalkthroughsnippets - vb/thisaddin.vb#4)]  
  
     En este método se utilizan dos características de C\# nuevas.  Ambas características ya existen en Visual Basic.  
  
    -   El método [Add](http://go.microsoft.com/fwlink/?LinkId=210910) tiene un *parámetro opcional* para especificar una plantilla determinada.  Los parámetros opcionales introducidos en [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] permiten omitir el argumento para ese parámetro si se desea utilizar el valor predeterminado del parámetro.  Dado que en el ejemplo anterior no se envía ningún argumento, `Add` usa la plantilla predeterminada y crea un libro nuevo.  La instrucción equivalente en versiones anteriores de C\# requiere un argumento de marcador de posición: `excelApp.Workbooks.Add(Type.Missing)`.  
  
         Para obtener más información, vea [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
    -   Las propiedades `Range` y `Offset` del objeto [Range](http://go.microsoft.com/fwlink/?LinkId=210911) usan la característica de *propiedades indizadas*.  Esta característica permite utilizar estas propiedades de los tipos COM mediante la siguiente sintaxis típica de C\#.  Las propiedades indizadas también permiten utilizar la propiedad `Value` del objeto `Range`, eliminando la necesidad de utilizar la propiedad `Value2`.  La propiedad `Value` está indizada, pero el índice es opcional.  Los argumentos opcionales y las propiedades indizadas funcionan conjuntamente en el ejemplo siguiente.  
  
         [!code-cs[csOfficeWalkthrough#5](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#5)]  
  
         En las versiones anteriores del lenguaje, se requiere la siguiente sintaxis especial.  
  
         [!code-cs[csOfficeWalkthrough#6](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#6)]  
  
         No es posible crear propiedades indizadas propias.  La característica solo admite el uso de las propiedades indizadas existentes.  
  
         Para obtener más información, vea [Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md).  
  
2.  Agregue el código siguiente al final de `DisplayInExcel` para ajustar los anchos de columna a fin de adaptarlos al contenido.  
  
     [!code-cs[csOfficeWalkthrough#7](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#7)]
     [!code-vb[csOfficeWalkthrough#7](../../../csharp/programming-guide/interop/codesnippet/visualbasic/officewalkthroughsnippets - vb/thisaddin.vb#7)]  
  
     Estas adiciones muestran otra característica nueva de C\# 2010: el tratamiento de valores `Object` devueltos por hosts COM \(como Office\) como si tuvieran un tipo [dinámico](../../../csharp/language-reference/keywords/dynamic.md).  Esto sucede automáticamente cuando **Incrustar tipos de interoperabilidad** se establece en su valor predeterminado `True` o, de igual modo, cuando la opción del compilador [\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) hace referencia al ensamblado.  El tipo `dynamic` permite el enlace en tiempo de ejecución, ya disponible en Visual Basic, y evita la conversión explícita que se requiere en Visual C\# 2008 y versiones anteriores del lenguaje.  
  
     Por ejemplo, `excelApp.Columns[1]` devuelve un `Object` y `AutoFit` es un método [Range](de%20http://go.microsoft.com/fwlink/?LinkId=210911) de Excel.  Sin `dynamic`, debe convertir el objeto devuelto por `excelApp.Columns[1]` como una instancia de `Range` antes de llamar al método `AutoFit`.  
  
     [!code-cs[csOfficeWalkthrough#8](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#8)]  
  
     Para obtener más información sobre cómo insertar tipos de interoperabilidad, consulte los procedimientos “Para buscar la referencia a un PIA” y “Para restaurar la dependencia de un PIA” más adelante en este tema.  Para obtener más información sobre `dynamic`, vea [dynamic](../../../csharp/language-reference/keywords/dynamic.md) o [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
### Para invocar DisplayInExcel  
  
1.  Agregue el código siguiente al final del método `ThisAddIn_StartUp`.  La llamada a `DisplayInExcel` contiene dos argumentos.  El primer argumento es el nombre de la lista de cuentas que se va a procesar.  El segundo argumento es una expresión lambda de varias líneas que define cómo se procesarán los datos.  Los valores `ID` y `balance` de cada cuenta se muestran en las celdas adyacentes y la fila se muestra en rojo si el saldo es inferior a cero.  Las expresiones lambda de varias líneas son una característica nueva en Visual Basic 2010.  Para obtener más información, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
     [!code-cs[csOfficeWalkthrough#9](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#9)]
     [!code-vb[csOfficeWalkthrough#9](../../../csharp/programming-guide/interop/codesnippet/visualbasic/officewalkthroughsnippets - vb/thisaddin.vb#9)]  
  
2.  Presione F5 para ejecutar el programa.  Aparece una hoja de cálculo de Excel que contiene los datos de las cuentas.  
  
### Para agregar un documento de Word  
  
1.  Agregue el código siguiente al final del método `ThisAddIn_StartUp` para crear un documento de Word que contenga un vínculo al libro de Excel.  
  
     [!code-cs[csOfficeWalkthrough#10](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#10)]
     [!code-vb[csOfficeWalkthrough#10](../../../csharp/programming-guide/interop/codesnippet/visualbasic/officewalkthroughsnippets - vb/thisaddin.vb#10)]  
  
     Este código muestra algunas de las nuevas características de C\#: capacidad para omitir la palabra clave `ref` en programación COM, argumentos con nombre y argumentos opcionales.  Estas características ya existen en Visual Basic.  El método [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099) tiene siete parámetros, y todos se definen como parámetros de referencia opcional.  Antes de Visual C\# 2010, había que definir variables de objeto para utilizar como argumentos de los siete parámetros, incluso cuando no se tenía ningún valor significativo para enviarles.  Los argumentos opcionales y con nombre permiten designar los parámetros a los que se desea tener acceso por nombre, y enviar argumentos únicamente a esos parámetros.  En este ejemplo se envían argumentos para indicar que se debe crear un vínculo al libro en el Portapapeles \(parámetro `Link`\), y que el vínculo se mostrará en el documento de Word como un icono \(parámetro `DisplayAsIcon`\).  Visual C\# 2010 también permite omitir la palabra clave `ref` para estos argumentos.  Compare el siguiente segmento de código de Visual C\# 2008 con la única línea necesaria en Visual C\# 2010:  
  
     [!code-cs[csOfficeWalkthrough#11](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#11)]  
  
### Para ejecutar la aplicación  
  
1.  Presione F5 para ejecutar la aplicación.  Excel se abre y muestra una tabla que contiene la información de las dos cuentas de `bankAccounts`.  Entonces aparece un documento de Word que contiene un vínculo a la tabla de Excel.  
  
### Para limpiar el proyecto completado  
  
1.  En Visual Studio, haga clic en **Limpiar solución** en el menú **Compilación**.  De lo contrario, el complemento se ejecutará cada vez que abra Excel en el equipo.  
  
### Para buscar la referencia a un PIA  
  
1.  Ejecute de nuevo la aplicación, pero no haga clic en **Limpiar solución**.  
  
2.  En el menú **Inicio**, haga clic en **Todos los programas**.  A continuación, haga clic en **Microsoft Visual Studio 2013**, después en **Visual Studio Tools** y luego en **Símbolo del sistema de Visual Studio \(2013\)**.  
  
3.  Escriba `ildasm` en la ventana del símbolo del sistema de Visual Studio \(2013\) y después presione ENTRAR.  Aparecerá la ventana IL DASM.  
  
4.  En el menú **Archivo** de la ventana de IL DASM, haga clic en **Abrir**.  Haga doble clic en **Visual Studio 2013** y luego haga doble clic en **Proyectos**.  Abra la carpeta de su proyecto y, en la carpeta bin\/Debug, busque *su\_proyecto*.dll.  Haga doble clic en *su\_proyecto*.dll.  Una nueva ventana muestra los atributos del proyecto, además de las referencias a otros módulos y ensamblados.  Tenga en cuenta que los espacios de nombres `Microsoft.Office.Interop.Excel` y `Microsoft.Office.Interop.Word` se incluyen en el ensamblado.  De forma predeterminada en Visual Studio 2013, el compilador importa los tipos necesarios desde un PIA con referencia a su ensamblado.  
  
     Para obtener más información, vea [Cómo: Ver el contenido de un ensamblado](../Topic/How%20to:%20View%20Assembly%20Contents.md).  
  
5.  Haga doble clic en el icono **MANIFIESTO**.  Aparecerá una ventana con una lista de ensamblados que contienen los elementos a los que hace referencia el proyecto.  `Microsoft.Office.Interop.Excel` y `Microsoft.Office.Interop.Word` no están incluidos en la lista.  Dado que los tipos que su proyecto necesita se han importado en el ensamblado, las referencias a un PIA no son necesarias.  Esto facilita la implementación.  Los PIA no tienen que estar presentes en el equipo del usuario y, puesto que una aplicación no requiere la implementación de una versión concreta de un PIA, se pueden diseñar aplicaciones que trabajen con varias versiones de Office, siempre que las API necesarias existan en todas las versiones.  
  
     Dado que la implementación de los PIA ya no es necesaria, puede crear una aplicación en escenarios avanzados que funcione con varias versiones de Office, incluidas versiones anteriores.  Sin embargo, esto solo funciona si el código no utiliza ninguna API que no esté disponible en la versión de Office con la que está trabajando.  No siempre está claro si una API concreta estaba disponible en una versión anterior y por ese motivo no recomendamos trabajar con versiones anteriores de Office.  
  
    > [!NOTE]
    >  Office no publicó ensamblados PIA antes de Office 2003.  Por lo tanto, la única manera de generar un ensamblado de interoperabilidad para Office 2002 o versiones anteriores es mediante la importación de la referencia COM.  
  
6.  Cierre la ventana del manifiesto y la del ensamblado.  
  
### Para restaurar la dependencia de un PIA  
  
1.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  Expanda la carpeta **Referencias** y seleccione **Microsoft.Office.Interop.Excel**.  Presione F4 para que se muestre la ventana **Propiedades**.  
  
2.  En la ventana **Propiedades**, cambie la propiedad **Incrustar tipos de interoperabilidad** de **True** a **False**.  
  
3.  Repita los pasos 1 y 2 de este procedimiento para `Microsoft.Office.Interop.Word`.  
  
4.  En C\#, marque como comentario las dos llamadas a `Autofit` al final del método `DisplayInExcel`.  
  
5.  Presione F5 para comprobar que el proyecto sigue ejecutándose correctamente.  
  
6.  Repita los pasos 1 a 3 del procedimiento anterior para abrir la ventana de ensamblado.  Observe que `Microsoft.Office.Interop.Word` y `Microsoft.Office.Interop.Excel` ya no están en la lista de ensamblados insertados.  
  
7.  Haga doble clic en el icono **MANIFIESTO** y desplácese por la lista de ensamblados de referencia.  Tanto `Microsoft.Office.Interop.Word` como `Microsoft.Office.Interop.Excel` están en la lista.  Dado que la aplicación hace referencia a los PIA de Excel y Word y la propiedad **Incrustar tipos de interoperabilidad** se establece en **False**, ambos ensamblados deben existir en el equipo del usuario final.  
  
8.  En Visual Studio, haga clic en **Limpiar solución** en el menú **Compilación** para limpiar el proyecto completado.  
  
## Vea también  
 [Propiedades autoimplementadas](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)   
 [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Pasar argumentos por posición o por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)   
 [Tutorial: Incrustar información de tipos de los ensamblados de Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tutorial: Incrustar los tipos de los ensamblados administrados](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tutorial: Crear el primer complemento de VSTO para Excel](../Topic/Walkthrough:%20Creating%20Your%20First%20VSTO%20Add-in%20for%20Excel.md)   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Interoperabilidad](../../../csharp/programming-guide/interop/interoperability.md)