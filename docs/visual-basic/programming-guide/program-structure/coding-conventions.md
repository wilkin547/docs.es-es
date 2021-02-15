---
description: 'Más información sobre: Visual Basic convenciones de codificación'
title: Convenciones de código
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 424871ab0e77629ded977bd0be768ed8736d1761
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460038"
---
# <a name="visual-basic-coding-conventions"></a>Convenciones de código de Visual Basic

Microsoft desarrolla ejemplos y documentación que siguen las instrucciones de este tema. Si sigue las mismas convenciones de codificación, puede obtener las siguientes ventajas:  
  
- El código tendrá un aspecto coherente, de modo que los lectores puedan centrarse mejor en el contenido, no en el diseño.  
  
- Los lectores entienden el código con más rapidez, ya que pueden hacer suposiciones basadas en la experiencia anterior.  
  
- Puede copiar, cambiar y mantener el código más fácilmente.  
  
- Ayuda a asegurarse de que el código muestra "prácticas recomendadas" para Visual Basic.  
  
## <a name="naming-conventions"></a>Convenciones de nomenclatura  
  
- Para obtener información sobre las directrices de nomenclatura, vea [el tema directrices de nomenclatura](../../../standard/design-guidelines/naming-guidelines.md) .  
  
- No use "mi" o "mi" como parte de un nombre de variable. Esta práctica crea confusión con los `My` objetos.  
  
- No es necesario cambiar los nombres de los objetos en el código generado automáticamente para que se ajusten a las instrucciones.  
  
## <a name="layout-conventions"></a>Convenciones de diseño  
  
- Inserte tabuladores como espacios y use la sangría inteligente con sangrías de cuatro espacios.  
  
- Utilice la **lista descriptiva (cambio de formato) del código** para volver a dar formato al código en el editor de código. Para obtener más información, vea [Opciones, editor de texto, básico (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
- Use solo una instrucción por línea. No use el carácter separador de línea de Visual Basic (:).  
  
- Evite el uso del carácter de continuación de línea explícita "_" en favor de la continuación de línea implícita siempre que el lenguaje lo permita.  
  
- Use solo una declaración por línea.  
  
- Si el **listing (volver a formatear) de código** no da formato a las líneas de continuación automáticamente, Aplique sangría manualmente a las líneas de continuación en una posición de tabulación. Sin embargo, siempre alinea a la izquierda los elementos de una lista.  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- Agregue al menos una línea en blanco entre las definiciones de método y propiedad.  
  
## <a name="commenting-conventions"></a>Convenciones de los comentarios  
  
- Coloque los comentarios en una línea independiente, en lugar de al final de una línea de código.  
  
- Inicie el texto del comentario con una letra mayúscula y finalice el texto del comentario con un punto.  
  
- Inserte un espacio entre el delimitador de comentario (') y el texto del comentario.  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- No incluya comentarios con bloques con formato de asteriscos.  
  
## <a name="program-structure"></a>Estructura del programa  
  
- Cuando use el `Main` método, utilice la construcción predeterminada para las nuevas aplicaciones de consola y use `My` para los argumentos de la línea de comandos.  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a>Convenciones de lenguaje  
  
### <a name="string-data-type"></a>String (Tipo de datos)  
  
- Use [interpolación de cadenas](../language-features/strings/interpolated-strings.md) para concatenar cadenas cortas, como se muestra en el código siguiente.
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- Para anexar cadenas en bucles, utilice el <xref:System.Text.StringBuilder> objeto.  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Delegados relajados en controladores de eventos  

 No califique explícitamente los argumentos (Object y EventArgs) con los controladores de eventos. Si no está usando los argumentos de evento que se pasan a un evento (por ejemplo, Sender como Object, e como EventArgs), use delegados relajados y omita los argumentos de evento en el código:  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a>Tipo de datos sin signo  
  
- Use `Integer` en lugar de tipos sin signo, excepto donde sean necesarios.  
  
### <a name="arrays"></a>Matrices  
  
- Use la sintaxis abreviada al inicializar matrices en la línea de declaración. Por ejemplo, use la sintaxis siguiente.  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     No use la sintaxis siguiente.  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- Coloque el designador de matriz en el tipo, no en la variable. Por ejemplo, use la siguiente sintaxis:  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- Use la sintaxis {} al declarar e inicializar matrices de tipos de datos básicos. Por ejemplo, use la siguiente sintaxis:  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a>Usar la palabra clave with  

 Cuando realice una serie de llamadas a un objeto, considere la posibilidad de usar la `With` palabra clave:  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Use la instrucción try... Instrucciones Catch y Using cuando se usa el control de excepciones  

 No use `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Usar la palabra clave IsNot  

 Use la `IsNot` palabra clave en lugar de `Not...Is Nothing` .  
  
### <a name="new-keyword"></a>New (palabra clave)  
  
- Utilice la creación de instancias cortas. Por ejemplo, use la siguiente sintaxis:  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     La línea anterior es equivalente a esta:  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- Use inicializadores de objeto para los nuevos objetos en lugar del constructor sin parámetros:  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a>Control de eventos  
  
- Use `Handles` en lugar de `AddHandler` :  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- Use `AddressOf` y no cree instancias del delegado explícitamente:  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- Al definir un evento, use la sintaxis abreviada y deje que el compilador defina el delegado:  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- No Compruebe si un evento es `Nothing` (NULL) antes de llamar al `RaiseEvent` método. `RaiseEvent` comprueba `Nothing` antes de que genere el evento.  
  
### <a name="using-shared-members"></a>Usar miembros compartidos  

 Llame a `Shared` los miembros mediante el nombre de clase, no desde una variable de instancia.  
  
### <a name="use-xml-literals"></a>Usar literales XML  

 Los literales XML simplifican las tareas más comunes que se producen al trabajar con XML (por ejemplo, cargar, consultar y transformar). Al desarrollar con XML, siga estas instrucciones:  
  
- Utilice literales XML para crear documentos y fragmentos XML en lugar de llamar directamente a las API XML.  
  
- Importe los espacios de nombres XML en el nivel de archivo o proyecto para aprovechar las optimizaciones de rendimiento de los literales XML.  
  
- Use las propiedades del eje XML para tener acceso a elementos y atributos en un documento XML.  
  
- Utilizar expresiones incrustadas para incluir valores y crear XML a partir de valores existentes en lugar de utilizar llamadas API como el `Add` método:  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a>Consultas LINQ  
  
- Use nombres descriptivos para las variables de consulta:  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- Proporcione nombres para los elementos de una consulta para asegurarse de que los nombres de propiedad de tipos anónimos se escriben en mayúsculas correctamente con la grafía Pascal:  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado. Por ejemplo, si la consulta devuelve un nombre de cliente y un identificador de pedido, cambie su nombre en lugar de mantenerlos como `Name` y `ID` en el resultado:  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- Use la inferencia de tipos en la declaración de variables de consulta y variables de intervalo:  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- Alinee las cláusulas de consulta en la `From` instrucción:  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- Use `Where` cláusulas antes de otras cláusulas de consulta para que las cláusulas de consulta posteriores operen en el conjunto de datos filtrado:  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- Utilice la `Join` cláusula para definir explícitamente una operación de combinación en lugar de utilizar la `Where` cláusula para definir implícitamente una operación de combinación:  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../../standard/security/secure-coding-guidelines.md)
