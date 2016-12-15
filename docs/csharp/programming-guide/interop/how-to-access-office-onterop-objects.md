---
title: "C&#243;mo: Tener acceso a objetos de interoperabilidad de Office mediante las caracter&#237;sticas de Visual C# (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "dinámico [C#], programación en Office"
  - "argumentos opcionales y con nombre [C#], programación en Office"
  - "argumentos con nombre [C#], programación en Office"
  - "programación en Office [C#]"
  - "argumentos opcionales [C#], programación en Office"
  - "parámetros opcionales [C#], programación en Office"
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
caps.latest.revision: 33
caps.handback.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Tener acceso a objetos de interoperabilidad de Office mediante las caracter&#237;sticas de Visual C# (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual C\# 2010 presenta nuevas características que simplifican el acceso a objetos de la API de Office.  Las nuevas características incluyen argumentos con nombre y opcionales, un nuevo tipo llamado `dynamic` y la capacidad de pasar argumentos a parámetros de referencia en los métodos COM como si fueran parámetros de valor.  
  
 En este tema se utilizarán las nuevas características para escribir código que crea y muestra una hoja de cálculo de Microsoft Office Excel.  A continuación, se escribirá código para agregar un documento de Office Word que contiene un icono que está vinculado a la hoja de cálculo de Excel.  
  
 Para completar este tutorial, es necesario tener Microsoft Office Excel 2007 y Microsoft Office Word 2007 —o una versión posterior— instalados en el equipo.  
  
 Si usa un sistema operativo anterior a [!INCLUDE[windowsver](../../../csharp/programming-guide/interop/includes/windowsver_md.md)], asegúrese de que [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] esté instalado.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Para crear una aplicación de consola nueva  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto**.  Aparecerá el cuadro de diálogo **Nuevo proyecto**.  
  
3.  En el panel **Plantillas instaladas**, expanda **Visual C\#** y haga clic en **Windows**.  
  
4.  En la parte superior del cuadro de diálogo **Nuevo proyecto**, compruebe si **.NET Framework 4** \(o una versión posterior\) está seleccionado como un marco de trabajo de destino.  
  
5.  En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
6.  Escriba un nombre para el proyecto en el campo **Nombre**.  
  
7.  Haga clic en **Aceptar**.  
  
     El proyecto nuevo aparece en el **Explorador de soluciones**.  
  
### Para agregar referencias  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y seleccione **Agregar referencia**.  Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
2.  En la página de **Ensamblados**, seleccione **Microsoft.Office.Interop.Word** en la lista **Nombre de componente** y, a continuación, mantenga presionada la tecla CTRL y seleccione **Microsoft.Office.Interop.Excel**.  Si no ve los ensamblados, asegúrese de que están instalados y que se muestran \(vea [Cómo: Instalar ensamblados de interoperabilidad primarios de Office](../Topic/How%20to:%20Install%20Office%20Primary%20Interop%20Assemblies.md)\)  
  
3.  Haga clic en **Aceptar**.  
  
### Para agregar las directivas using necesarias  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el archivo **Program.cs** y, a continuación, haga clic en **Ver código**.  
  
2.  Agregue las directivas `using` siguientes a la parte superior del archivo de código.  
  
     [!code-cs[csProgGuideOfficeHowTo#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_1.cs)]  
  
### Para crear una lista de las cuentas bancarias  
  
1.  Pegue la siguiente definición de clase en **Program.cs**, bajo la clase `Program`.  
  
     [!code-cs[csProgGuideOfficeHowTo#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_2.cs)]  
  
2.  Agregue el código siguiente al método `Main` para crear una lista `bankAccounts` lista que contenga dos cuentas.  
  
     [!code-cs[csProgGuideOfficeHowTo#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_3.cs)]  
  
### Para declarar un método que exporta información de cuentas a Excel  
  
1.  Agregue el método siguiente a la clase `Program` para configurar una hoja de cálculo de Excel.  
  
     El método [Add](http://go.microsoft.com/fwlink/?LinkId=210910) tiene un parámetro opcional para especificar una plantilla determinada.  Los parámetros opcionales introducidos en [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] permiten omitir el argumento para ese parámetro si se desea utilizar el valor predeterminado del parámetro.  Dado que en el código siguiente no se envía ningún argumento, `Add` usa la plantilla predeterminada y crea un libro nuevo.  La instrucción equivalente en versiones anteriores de C\# requiere un argumento de marcador de posición: `ExcelApp.Workbooks.Add(Type.Missing)`.  
  
     [!code-cs[csProgGuideOfficeHowTo#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_4.cs)]  
  
2.  Agregue el siguiente código al final de `DisplayInExcel`.  El código inserta valores en las dos primeras columnas de la primera fila de la hoja de cálculo.  
  
     [!code-cs[csProgGuideOfficeHowTo#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_5.cs)]  
  
3.  Agregue el siguiente código al final de `DisplayInExcel`.  El bucle `foreach` coloca la información de la lista de cuentas en las dos primeras columnas de filas sucesivas de la hoja de cálculo.  
  
     [!code-cs[csProgGuideOfficeHowTo#7](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_6.cs)]  
  
4.  Agregue el código siguiente al final de `DisplayInExcel` para ajustar los anchos de columna a fin de adaptarlos al contenido.  
  
     [!code-cs[csProgGuideOfficeHowTo#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_7.cs)]  
  
     Las versiones anteriores de C\# requieren una conversión explícita para estas operaciones, ya que `ExcelApp.Columns[1]` devuelve un `Object`, y `AutoFit` es un método de [rango](http://go.microsoft.com/fwlink/?LinkId=210911) de Excel.  Las siguientes líneas muestran la conversión.  
  
     [!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]  
  
     [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] —y versiones posteriores— convierte automáticamente el valor `Object` devuelto en `dynamic` si se hace referencia al ensamblado mediante la opción del compilador [\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) o, de forma equivalente, si la propiedad **Incrustar tipos de interoperabilidad** de Excel se establece en true.  El valor predeterminado de esta propiedad es true.  
  
### Para ejecutar el proyecto  
  
1.  Agregue la línea siguiente al final de `Main`.  
  
     [!code-cs[csProgGuideOfficeHowTo#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_9.cs)]  
  
2.  Presione CTRL\+F5.  
  
     Aparece una hoja de cálculo de Excel que contiene los datos de las dos cuentas.  
  
### Para agregar un documento de Word  
  
1.  Para ilustrar las formas adicionales en que [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] y versiones posteriores mejoran la programación de Office, el código siguiente abre una aplicación de Word y crea un icono que se vincula a la hoja de cálculo de Excel.  
  
     Pegue el método `CreateIconInWordDoc`, proporcionado más adelante en este paso, en la clase `Program`.  `CreateIconInWordDoc` usa argumentos con nombre y argumentos opcionales para reducir la complejidad de las llamadas de método a [Add](http://go.microsoft.com/fwlink/?LinkId=210937) y [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099).  Estas llamadas incorporan otras dos nuevas características introducidas en [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] que simplifican las llamadas a métodos COM que tienen parámetros de referencia.  En primer lugar, puede enviar argumentos a los parámetros de referencia como si fueran parámetros de valor.  Es decir, puede enviar valores directamente, sin necesidad de crear una variable para cada parámetro de referencia.  El compilador genera variables temporales para contener los valores de argumento y las descarta cuando se regresa de la llamada.  En segundo lugar, se puede omitir la palabra clave `ref` en la lista de argumentos.  
  
     El método `Add` tiene cuatro parámetros de referencia, todos ellos opcionales.  En [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] o versiones posteriores, puede omitir los argumentos de cualquiera o de todos los parámetros si desea usar sus valores predeterminados.  En [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] y versiones anteriores, se debe proporcionar un argumento para cada parámetro; el argumento debe ser una variable, ya que los parámetros son parámetros de referencia.  
  
     El método `PasteSpecial` inserta el contenido del Portapapeles.  El método tiene siete parámetros de referencia, todos ellos opcionales.  El siguiente código especifica los argumentos para dos de ellos: `Link`, para crear un vínculo con el origen del contenido del Portapapeles, y `DisplayAsIcon`, para mostrar el vínculo como un icono.  En [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)], puede usar argumentos con nombre para esos dos y omitir los demás.  Aunque se trata de parámetros de referencia, no es necesario utilizar la palabra clave `ref` ni crear variables para enviarlas como argumentos.  Puede enviar los valores directamente.  En [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] y versiones anteriores, debe enviar un argumento de variable para cada parámetro de referencia.  
  
     [!code-cs[csProgGuideOfficeHowTo#9](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_10.cs)]  
  
     En [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] o versiones anteriores del lenguaje, es necesario el código siguiente, más complejo.  
  
     [!code-cs[csProgGuideOfficeHowTo#10](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_11.cs)]  
  
2.  Agregue la siguiente instrucción al final de `Main`.  
  
     [!code-cs[csProgGuideOfficeHowTo#11](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_12.cs)]  
  
3.  Agregue la siguiente instrucción al final de `DisplayInExcel`.  El método `Copy` agrega la hoja de cálculo en el Portapapeles.  
  
     [!code-cs[csProgGuideOfficeHowTo#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_13.cs)]  
  
4.  Presione CTRL\+F5.  
  
     Un documento de Word aparecerá con un icono.  Haga doble clic en el icono para abrir la hoja de cálculo en primer plano.  
  
### Para establecer la propiedad Incrustar tipos de interoperabilidad  
  
1.  Es posible realizar mejoras adicionales si se llama a un tipo COM que no requiere un ensamblado de interoperabilidad primario \(PIA\) en tiempo de ejecución.  Si se elimina la dependencia de PIA, la versión gana en independencia y se facilita la implementación.  Para obtener más información sobre las ventajas de la programación sin PIA, vea [Tutorial: Incrustar los tipos de los ensamblados administrados](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
     Además, programar resulta más fácil porque los tipos requeridos y devueltos por los métodos COM se pueden representar con el tipo `dynamic` en vez de `Object`.  Las variables de tipo `dynamic` no se evalúan hasta el tiempo de ejecución, lo que elimina la necesidad de la conversión explícita.  Para obtener más información, vea [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
     En [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)], el comportamiento predeterminado es insertar información de tipos en lugar de utilizar los PIA.  Debido a ese comportamiento predeterminado, algunos de los ejemplos anteriores se simplifican dado que no es necesaria la conversión explícita.  Por ejemplo, la declaración de `worksheet` en `DisplayInExcel` se escribe como `Excel._Worksheet workSheet = excelApp.ActiveSheet` en lugar de `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`.  Las llamadas a `AutoFit` en el mismo método también requerirían conversión explícita sin el valor predeterminado, porque `ExcelApp.Columns[1]` devuelve un `Object` y `AutoFit` es un método de Excel.  En el código siguiente se muestra la conversión.  
  
     [!code-cs[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]  
  
2.  Para cambiar el valor predeterminado y utilizar los PIA en lugar de insertar información de tipos, expanda el nodo **Referencias** del **Explorador de soluciones** y, a continuación, seleccione **Microsoft.Office.Interop.Excel** o **Microsoft.Office.Interop.Word**.  
  
3.  Si no ve la ventana **Propiedades**, presione **F4**.  
  
4.  Busque **Incrustar tipos de interoperabilidad** en la lista de propiedades y cambie su valor a **False**.  De igual modo, puede compilar mediante el uso de la opción del compilador [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) en lugar de [\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) en un símbolo del sistema.  
  
### Para agregar formato adicional a la tabla  
  
1.  Reemplace las dos llamadas a `AutoFit` en `DisplayInExcel` con la siguiente instrucción.  
  
     [!code-cs[csProgGuideOfficeHowTo#15](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_14.cs)]  
  
     El método [Autoformat](http://go.microsoft.com/fwlink/?LinkId=210948) tiene siete parámetros de valor, todos ellos opcionales.  Los argumentos con nombre y los argumentos opcionales permiten proporcionar argumentos para ninguno, algunos o todos ellos.  En la instrucción anterior, se proporciona un argumento para uno solo de los parámetros, `Format`.  Puesto que `Format` es el primer parámetro de la lista de parámetros, no es necesario proporcionar el nombre de parámetro.  Sin embargo, la instrucción sería más fácil de entender si se incluyese el nombre del parámetro, como se muestra en el código siguiente.  
  
     [!code-cs[csProgGuideOfficeHowTo#16](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_15.cs)]  
  
2.  Presione CTRL\+F5 para ver el resultado.  Otros formatos se enumeran en la enumeración [XlRangeAutoFormat](http://go.microsoft.com/fwlink/?LinkId=210967).  
  
3.  Compare la instrucción del paso 1 con el siguiente código, que muestra los argumentos necesarios en [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] o versiones anteriores.  
  
     [!code-cs[csProgGuideOfficeHowTo#17](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_16.cs)]  
  
## Ejemplo  
 En el código siguiente se muestra el ejemplo completo.  
  
 [!code-cs[csProgGuideOfficeHowTo#18](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_17.cs)]  
  
## Vea también  
 <xref:System.Type.Missing?displayProperty=fullName>   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [Cómo: Usar argumentos opcionales y con nombre en la programación de Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)