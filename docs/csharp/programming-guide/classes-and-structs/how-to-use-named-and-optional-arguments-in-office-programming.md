---
title: "Cómo: Usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c773e7a6d902b9e61e724a69c9fdf5d61606de50
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>Cómo: Usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)
Los argumentos con nombre y los argumentos opcionales, introducidos en [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], mejoran la comodidad, la flexibilidad y la legibilidad en la programación de C#. Además, estas características facilitan enormemente el acceso a interfaces COM, como las API de automatización de Microsoft Office.  
  
 En el ejemplo siguiente, el método [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) tiene dieciséis parámetros que representan las características de una tabla, como el número de columnas y filas, el formato, los bordes, las fuentes y los colores. Los dieciséis parámetros son opcionales, ya que la mayoría de las veces no interesa especificar valores concretos para todos ellos. Pero si no hay argumentos opcionales y con nombre, es necesario proporcionar un valor o un valor de marcador de posición para cada parámetro. Con los argumentos opcionales y con nombre, puede especificar valores solamente para los parámetros necesarios para el proyecto.  
  
 Debe tener Microsoft Office Word instalado en el equipo para completar estos procedimientos.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a>Para crear una aplicación de consola nueva  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.  
  
3.  En el panel **Templates Categories** (Categorías de plantillas), expanda **Visual C#** y haga clic en **Windows**.  
  
4.  En la parte superior del panel **Plantillas**, asegúrese de que **.NET Framework 4** aparece en el cuadro **Plataforma de destino**.  
  
5.  En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
6.  Escriba un nombre para el proyecto en el campo **Nombre**.  
  
7.  Haga clic en **Aceptar**.  
  
     El proyecto nuevo aparece en el **Explorador de soluciones**.  
  
### <a name="to-add-a-reference"></a>Para agregar una referencia  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto y seleccione **Agregar referencia**. Aparecerá el cuadro de diálogo **Agregar referencia**.  
  
2.  En la página **.NET**, seleccione **Microsoft.Office.Interop.Word** en la lista **Nombre de componente**.  
  
3.  Haga clic en **Aceptar**.  
  
### <a name="to-add-necessary-using-directives"></a>Para agregar las directivas using necesarias  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo **Program.cs** y, después, haga clic en **Ver código**.  
  
2.  Agregue las directivas `using` siguientes a la parte superior del archivo de código.  
  
     [!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]  
  
### <a name="to-display-text-in-a-word-document"></a>Para mostrar texto en un documento de Word  
  
1.  En la clase `Program` en Program.cs, agregue el método siguiente para crear una aplicación de Word y un documento de Word. El método [Add](http://go.microsoft.com/fwlink/?LinkId=145381) tiene cuatro parámetros opcionales. En este ejemplo se usan los valores predeterminados. Por lo tanto, no se necesitan argumentos en la instrucción de llamada.  
  
     [!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]  
  
2.  Agregue el código siguiente al final del método para definir dónde se muestra texto en el documento y qué texto se muestra.  
  
     [!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]  
  
### <a name="to-run-the-application"></a>Para ejecutar la aplicación  
  
1.  Agregue la instrucción siguiente a Main.  
  
     [!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]  
  
2.  Presione CTRL+F5 para ejecutar el proyecto. Aparecerá un documento de Word con el texto especificado.  
  
### <a name="to-change-the-text-to-a-table"></a>Para convertir el texto en tabla  
  
1.  Use el método `ConvertToTable` para incluir el texto en una tabla. El método tiene 16 parámetros opcionales. IntelliSense coloca los parámetros opcionales entre corchetes, tal como se muestra en la ilustración siguiente.  
  
     ![Lista de parámetros para el método ConvertToTable.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")  
Parámetros de ConvertToTable  
  
     Los argumentos opcionales y con nombre permiten especificar valores solo para los parámetros que quiere cambiar. Agregue el código siguiente al final del método `DisplayInWord` para crear una tabla simple. El argumento especifica que las comas de la cadena de texto de `range` separan las celdas de la tabla.  
  
     [!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]  
  
     En versiones anteriores de C#, la llamada a `ConvertToTable` requiere un argumento de referencia para cada parámetro, tal como se muestra en el código siguiente.  
  
     [!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]  
  
2.  Presione CTRL+F5 para ejecutar el proyecto.  
  
### <a name="to-experiment-with-other-parameters"></a>Para experimentar con otros parámetros  
  
1.  Para cambiar la tabla de modo que tenga una columna y tres filas, reemplace la última línea de `DisplayInWord` por la instrucción siguiente y escriba CTRL+F5.  
  
     [!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]  
  
2.  Para especificar un formato predefinido para la tabla, reemplace la última línea de `DisplayInWord` por la instrucción siguiente y escriba CTRL+F5. El formato puede ser cualquiera de las constantes [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382).  
  
     [!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se incluye el ejemplo completo.  
  
 [!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)

