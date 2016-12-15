---
title: "C&#243;mo: Usar argumentos opcionales y con nombre en la programaci&#243;n de Office (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "argumentos opcionales y con nombre [C#], programación en Office"
  - "argumentos con nombre [C#], programación en Office"
  - "argumentos opcionales [C#], programación en Office"
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
caps.handback.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Usar argumentos opcionales y con nombre en la programaci&#243;n de Office (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los argumentos con nombre y los argumentos opcionales, incluidos en [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)], mejoran la comodidad, la flexibilidad y la legibilidad de la programación de C\#. Además, estas características facilitan enormemente el acceso a las interfaces COM, como las API de automatización de Microsoft Office.  
  
 En el ejemplo siguiente, el método [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) tiene dieciséis parámetros que representan diversas características de una tabla, como el número de columnas y filas, el formato, los bordes, las fuentes y los colores.  Los dieciséis parámetros son opcionales, porque la mayoría de las veces no se desea especificar valores determinados para todos ellos.  Sin embargo, sin los argumentos opcionales y con nombre, debe proporcionarse un valor o un valor de marcador de posición para cada parámetro.  Con los argumentos opcionales y con nombre, solamente se deben especificar valores para los parámetros necesarios para el proyecto.  
  
 Para poder completar estos procedimientos, debe tener instalado Microsoft Office Word en el equipo.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Para crear una aplicación de consola  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto**.  
  
3.  En el panel **Categorías de plantillas**, expanda **Visual C\#**y, a continuación, haga clic en **Ventanas**.  
  
4.  Compruebe la parte superior del panel **Plantillas** para asegurarse de que **.NET Framework 4** aparece en el cuadro **Versión de .NET Framework de destino**.  
  
5.  En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
6.  Escriba un nombre para el proyecto en el campo **Nombre**.  
  
7.  Haga clic en **Aceptar**.  
  
     El nuevo proyecto aparecerá en el **Explorador de soluciones**.  
  
### Para agregar una referencia  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el nombre del proyecto y, a continuación, haga clic en **Agregar referencia**.  Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
2.  En la página de **.NET**, seleccione **Microsoft.Office.Interop.Word** en la lista **Nombre de componente**.  
  
3.  Haga clic en **Aceptar**.  
  
### Para agregar las directivas using necesarias  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el archivo **Program.cs** y, a continuación, haga clic en **Ver código**.  
  
2.  Agregue las siguientes directivas `using` al principio del archivo de código.  
  
     [!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]  
  
### Para mostrar texto en un documento de Word  
  
1.  En la clase `Program` de Program.cs, agregue el siguiente método para crear una aplicación y un documento de Word.  El método [Add](http://go.microsoft.com/fwlink/?LinkId=145381) tiene cuatro parámetros opcionales.  En este ejemplo se usan sus valores predeterminados.  Por lo tanto, no se requiere ningún argumento en la instrucción de llamada.  
  
     [!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]  
  
2.  Agregue el siguiente código al final del método para definir dónde se va a mostrar el texto en el documento y qué texto se va a mostrar.  
  
     [!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]  
  
### Para ejecutar la aplicación  
  
1.  Agregue la siguiente instrucción a Main.  
  
     [!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]  
  
2.  Presione CTRL\+F5 para ejecutar el proyecto.  Aparece un documento de Word que contiene el texto especificado.  
  
### Para cambiar el texto a modo de tabla  
  
1.  Use el método `ConvertToTable` para incluir el texto en una tabla.  El método tiene dieciséis parámetros opcionales.  IntelliSense coloca los parámetros opcionales entre corchetes, tal y como se muestra en la siguiente ilustración.  
  
     ![Lista de parámetros para el método ConvertToTable.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert\_TableParameters")  
Parámetros de ConvertToTable  
  
     Los parámetros opcionales y con nombre permiten especificar valores únicamente para los parámetros que se desean cambiar.  Agregue el código siguiente al final del método `DisplayInWord` para crear una tabla simple.  El argumento especifica que las comas en la cadena de texto de `range` separan las celdas de la tabla.  
  
     [!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]  
  
     En las versiones anteriores de C\#, la llamada a `ConvertToTable` requiere un argumento de referencia para cada parámetro, tal y como se muestra en el siguiente código.  
  
     [!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]  
  
2.  Presione CTRL\+F5 para ejecutar el proyecto.  
  
### Para experimentar con otros parámetros  
  
1.  Para cambiar la tabla de forma que tenga una columna y tres filas, reemplace la última línea de `DisplayInWord` con la instrucción siguiente y, a continuación, presione CTRL\+F5.  
  
     [!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]  
  
2.  Para especificar un formato predefinido para la tabla, reemplace la última línea de `DisplayInWord` con la instrucción siguiente y, a continuación, presione CTRL\+F5.  El formato puede ser cualquiera de las constantes [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382).  
  
     [!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]  
  
## Ejemplo  
 En el código siguiente se incluye el ejemplo completo.  
  
 [!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]  
  
## Vea también  
 [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)