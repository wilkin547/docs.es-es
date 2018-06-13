---
title: Convenciones de código de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: b686747b46529b53b0802a7deb38b5b4949f4d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655366"
---
# <a name="visual-basic-coding-conventions"></a>Convenciones de código de Visual Basic
Microsoft desarrolla ejemplos y documentación que siga las directrices descritas en este tema. Si sigue las mismas convenciones de codificación, puede obtener las ventajas siguientes:  
  
-   El código tendrá una apariencia coherente, para que los lectores puedan centrarse mejor en el contenido, no en el diseño.  
  
-   Los lectores comprender el código más rápidamente porque pueden hacer suposiciones basadas en la experiencia anterior.  
  
-   Puede copiar, modificar y mantener más fácilmente el código.  
  
-   Para ayudar a asegurarse de que el código muestra "prácticas recomendadas" para Visual Basic.  
  
## <a name="naming-conventions"></a>Convenciones de nomenclatura  
  
-   Para obtener información acerca de las directrices de nomenclatura, consulte [directrices de nomenclatura](../../../standard/design-guidelines/naming-guidelines.md) tema.  
  
-   No utilice "Mi" o "Mi" como parte de un nombre de variable. Este procedimiento crea confusión con los `My` objetos.  
  
-   No es necesario cambiar los nombres de objetos en el código generado automáticamente para que se ajusten a las instrucciones.  
  
## <a name="layout-conventions"></a>Convenciones de diseño  
  
-   Inserte las tabulaciones como espacios y utilice sangrías con una sangría de cuatro espacios.  
  
-   Use **lista descriptiva (nuevo formato) de código** volver a formatear el código en el editor de código. Para obtener más información, consulte [opciones, Editor de texto, básico (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Usar solo una instrucción por línea. No use el carácter de separador de línea de Visual Basic (:).  
  
-   Evite usar el carácter de continuación de línea explícita "_" en favor de continuación de línea implícita siempre que sea el lenguaje lo permite.  
  
-   Usar solo una declaración por línea.  
  
-   Si **lista descriptiva (nuevo formato) de código** no las líneas de continuación de formato automáticamente, manualmente aplicar sangría a continuación líneas una tabulación. Sin embargo, siempre Alinear a la izquierda elementos en una lista.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Agregue al menos una línea en blanco entre las definiciones de método y propiedad.  
  
## <a name="commenting-conventions"></a>Convenciones de los comentarios  
  
-   Colocar comentarios en una línea independiente en lugar de al final de una línea de código.  
  
-   Inicie el texto del comentario con una letra mayúscula y texto del comentario final con un punto.  
  
-   Inserte un espacio entre el delimitador de comentario (') y el texto del comentario.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   No se especifica los comentarios con bloques con formato de asteriscos.  
  
## <a name="program-structure"></a>Estructura del programa  
  
-   Cuando se usa el `Main` método, utilice la construcción predeterminada para las nuevas aplicaciones de consola y usar `My` para los argumentos de línea de comandos.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>Convenciones de lenguaje  
  
### <a name="string-data-type"></a>String (Tipo de datos)  
  
-   Para concatenar cadenas, utilice una y comercial (&).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Para anexar cadenas en bucles, utilice el <xref:System.Text.StringBuilder> objeto.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Delegados flexibles en controladores de eventos  
 No calificar explícitamente los argumentos (objeto y EventArgs) a controladores de eventos. Si no utiliza argumentos de evento que se pasan a un evento (por ejemplo, el remitente como Object, e as EventArgs), utilice a delegados flexibles y omita los argumentos del evento en el código:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>Tipo de datos sin signo  
  
-   Use `Integer` en lugar de tipos sin signo, excepto cuando es necesario.  
  
### <a name="arrays"></a>Matrices  
  
-   Utilice la sintaxis abreviada al inicializar las matrices en la línea de declaración. Por ejemplo, use la siguiente sintaxis.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     No utilice la siguiente sintaxis.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Coloque el designador de matriz en el tipo, no en la variable. Por ejemplo, use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Use la sintaxis {} al declarar e inicializar matrices de tipos de datos básicos. Por ejemplo, use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>Use el con la palabra clave  
 Al realizar una serie de llamadas a un objeto, considere el uso de la `With` palabra clave:  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Utilizar las instrucciones Try... Catch e instrucciones Using cuando se usa el control de excepciones  
 No utilice `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Utilice la palabra clave IsNot  
 Use la `IsNot` palabra clave en lugar de `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>Nueva palabra clave  
  
-   Utilice la creación de instancias corta. Por ejemplo, use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     La línea anterior es equivalente a esta:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Usar a inicializadores de objeto para los nuevos objetos en lugar del constructor sin parámetros:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>Control de eventos  
  
-   Use `Handles` en lugar de `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Use `AddressOf`y no crea una instancia del delegado explícitamente:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   Al definir un evento, use la sintaxis abreviada y dejar que el compilador defina al delegado:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   No comprobar si un evento es `Nothing` (null) antes de llamar a la `RaiseEvent` método. `RaiseEvent` busca `Nothing` antes de que genera el evento.  
  
### <a name="using-shared-members"></a>Utilizar miembros compartidos  
 Llame a `Shared` miembros mediante el nombre de clase, no de una variable de instancia.  
  
### <a name="use-xml-literals"></a>Utilizar literales XML  
 Los literales XML simplifican las tareas más comunes que encuentre al trabajar con XML (por ejemplo, carga, consulta y transformación). Al desarrollar con XML, siga estas instrucciones:  
  
-   Utilizar literales XML para crear documentos XML y fragmentos en lugar de llamar directamente a las API de XML.  
  
-   Importe los espacios de nombres XML en el nivel de archivo o proyecto para aprovechar las ventajas de las optimizaciones de rendimiento para los literales XML.  
  
-   Utilice las propiedades de eje XML para tener acceso a elementos y atributos en un documento XML.  
  
-   Utilizar expresiones incrustadas para incluir valores y crear XML a partir de los valores existentes en lugar de utilizar llamadas a la API, como el `Add` método:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>Consultas LINQ  
  
-   Utilice nombres descriptivos para las variables de consulta:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Proporcionar nombres para los elementos en una consulta para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente con mayúscula utilizando la grafía Pascal de mayúsculas y minúsculas:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado. Por ejemplo, si la consulta devuelve un cliente, nombre y un identificador de pedido, cambiar su nombre en lugar de dejarlos como `Name` y `ID` en el resultado:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Usar la inferencia de tipo en la declaración de variables de consulta y las variables de rango:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Alinee las cláusulas de consulta en el `From` instrucción:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Use `Where` cláusulas antes que otras las cláusulas de consulta para que las cláusulas de consulta posteriores operan en el conjunto filtrado de datos:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Use la `Join` cláusula para definir explícitamente una operación de combinación en lugar de utilizar el `Where` cláusula para definir implícitamente una operación de combinación:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de codificación segura](../../../standard/security/secure-coding-guidelines.md)
