---
title: Convenciones de código de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 634e39e3e274b919f63ff1b4f3c7b0cd311beaf1
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201181"
---
# <a name="visual-basic-coding-conventions"></a>Convenciones de código de Visual Basic
Microsoft desarrolla los ejemplos y documentación que siguen las directrices descritas en este tema. Si sigue las mismas convenciones de codificación, obtendrá las siguientes ventajas:  
  
-   El código tendrá una apariencia coherente, para que los lectores puedan centrarse mejor en el contenido, no en el diseño.  
  
-   Los lectores comprender el código más rápidamente ya que pueden hacer suposiciones en función de la experiencia anterior.  
  
-   Puede copiar, modificar y mantener más fácilmente el código.  
  
-   Ayudan a garantizar que el código muestra "procedimientos recomendados" de Visual Basic.  
  
## <a name="naming-conventions"></a>Convenciones de nomenclatura  
  
-   Para obtener información acerca de las directrices de nomenclatura, consulte [instrucciones de nomenclatura](../../../standard/design-guidelines/naming-guidelines.md) tema.  
  
-   No utilice "Mi" o "Mi" como parte de un nombre de variable. Esta práctica crea confusión con los `My` objetos.  
  
-   No es necesario cambiar los nombres de objetos en el código generado automáticamente para que se ajusten a las instrucciones.  
  
## <a name="layout-conventions"></a>Convenciones de diseño  
  
-   Inserte tabulaciones como espacios y use la sangría inteligente con sangrías de cuatro espacios.  
  
-   Use **lista descriptiva (nuevo formato) de código** volver a formatear el código en el editor de código. Para obtener más información, consulte [opciones, Editor de texto, básico (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Utilice sólo una instrucción por línea. No use el carácter de separador de línea de Visual Basic (:).  
  
-   Evite usar el carácter de continuación de línea explícito "_" en favor de continuación de línea implícita siempre que sea el lenguaje lo permita.  
  
-   Use solo una declaración por línea.  
  
-   Si **lista descriptiva (nuevo formato) de código** no formato las líneas de continuación automáticamente, manualmente aplicar sangría a continuación líneas una tabulación. Sin embargo, siempre Alinear a la izquierda los elementos de una lista.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Agregue al menos una línea en blanco entre definiciones de método y propiedad.  
  
## <a name="commenting-conventions"></a>Convenciones de los comentarios  
  
-   Ponga los comentarios en una línea independiente en lugar de al final de una línea de código.  
  
-   Inicie el texto del comentario con una letra mayúscula y texto del comentario de final con un punto.  
  
-   Inserte un espacio entre el delimitador de comentario (') y el texto del comentario.  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
-   No especifique comentarios con bloques con formato de asteriscos.  
  
## <a name="program-structure"></a>Estructura del programa  
  
-   Cuando se usa el `Main` método, utilice la construcción predeterminada para nuevas aplicaciones de consola y usar `My` para los argumentos de línea de comandos.  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a>Convenciones de lenguaje  
  
### <a name="string-data-type"></a>String (Tipo de datos)  
  
-   Para concatenar cadenas, utilice una y comercial (&).  
  
     [!code-vb[VbVbalrGuidelines#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#4)]  
  
-   Para anexar cadenas en bucles, utilice el <xref:System.Text.StringBuilder> objeto.  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Delegados flexibles en controladores de eventos  
 No califique explícitamente los argumentos (Object y EventArgs) a controladores de eventos. Si no usa los argumentos del evento que se pasan a un evento (por ejemplo, el remitente como objeto como EventArgs), utilice a los delegados flexibles y omita los argumentos del evento en el código:  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a>Tipo de datos sin signo  
  
-   Use `Integer` en lugar de tipos sin signo, excepto cuando sean necesarios.  
  
### <a name="arrays"></a>Matrices  
  
-   Utilice la sintaxis abreviada para inicializar las matrices en la línea de declaración. Por ejemplo, use la siguiente sintaxis.  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     No utilice la siguiente sintaxis.  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
-   Sitúe el designador en el tipo, no en la variable. Por ejemplo, use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
-   Utilice la sintaxis {} al declarar e inicializar matrices de tipos de datos básicos. Por ejemplo, use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a>Use la palabra clave  
 Al realizar una serie de llamadas a un objeto, considere el uso de la `With` palabra clave:  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Usar Try... Catch y las instrucciones Using al usar el control de excepciones  
 No use `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Use la palabra clave IsNot  
 Use la `IsNot` palabra clave en lugar de `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>Nueva palabra clave  
  
-   Utilice la creación de instancias abreviada. Por ejemplo, use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     La línea anterior es equivalente a esta:  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
-   Usar a inicializadores de objeto para los nuevos objetos en lugar del constructor sin parámetros:  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a>Control de eventos  
  
-   Use `Handles` lugar `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
-   Use `AddressOf`y no crear explícitamente instancias del delegado:  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
-   Al definir un evento, utilice la sintaxis corta y permita que el compilador defina al delegado:  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
-   No comprobar si un evento es `Nothing` (null) antes de llamar a la `RaiseEvent` método. `RaiseEvent` comprueba si hay `Nothing` antes de que se genera el evento.  
  
### <a name="using-shared-members"></a>Utilizar miembros compartidos  
 Llamar a `Shared` miembros con el nombre de clase, no una variable de instancia.  
  
### <a name="use-xml-literals"></a>Utilice literales XML  
 Los literales XML simplifican las tareas más comunes que encontrar al trabajar con XML (por ejemplo, carga, consulta y transformación). Al desarrollar con XML, siga estas instrucciones:  
  
-   Utilice literales XML para crear documentos XML y fragmentos en lugar de llamar directamente a las API de XML.  
  
-   Importe los espacios de nombres XML en el nivel de archivo o proyecto para aprovechar las ventajas de las optimizaciones de rendimiento para los literales XML.  
  
-   Utilice las propiedades de eje XML para tener acceso a los elementos y atributos en un documento XML.  
  
-   Utilizar expresiones incrustadas para incluir los valores y crear XML de los valores existentes en lugar de utilizar llamadas a la API, como el `Add` método:  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a>Consultas LINQ  
  
-   Utilice nombres descriptivos para las variables de consulta:  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
-   Proporcionar nombres para los elementos de una consulta para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente mediante la grafía Pascal mayúsculas y minúsculas:  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
-   Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado. Por ejemplo, si la consulta devuelve un cliente, nombre y un identificador de pedido, cambiar su nombre en lugar de dejarlos como `Name` y `ID` en el resultado:  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
-   Usar la inferencia de tipo en la declaración de variables de consulta y las variables de rango:  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
-   Alinee las cláusulas de consulta bajo la `From` instrucción:  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
-   Use `Where` cláusulas antes que otras cláusulas de consulta para que las cláusulas de consulta posteriores operan en el conjunto filtrado de datos:  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
-   Use la `Join` cláusula para definir explícitamente una operación de combinación en lugar de usar el `Where` cláusula para definir implícitamente una operación de combinación:  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vea también
- [Instrucciones de codificación segura](../../../standard/security/secure-coding-guidelines.md)
