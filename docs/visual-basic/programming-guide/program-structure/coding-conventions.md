---
title: "Convenciones de c&#243;digo de Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "convenciones de código, Visual Basic"
  - "ejemplos [Visual Basic], convenciones de código"
  - "código de Visual Basic, convenciones"
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
caps.handback.revision: 48
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Convenciones de c&#243;digo de Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Microsoft desarrolla los ejemplos y la documentación que siguen las instrucciones de este tema.  Si sigue las mismas convenciones de codificación, puede aprovechar las ventajas siguientes:  
  
-   Su código tendrá un aspecto coherente, de modo que los lectores pueden centrar mejor su atención en el contenido y no en el diseño.  
  
-   Los lectores entienden el código con más rapidez, ya que pueden hacer suposiciones en función de su experiencia anterior.  
  
-   Puede copiar, cambiar y mantener el código con mayor facilidad.  
  
-   Ayuda a garantiza que el código muestra “procedimientos recomendados” para Visual Basic.  
  
## Convenciones de nomenclatura  
  
-   Para obtener información sobre las directrices de nomenclatura, vea el tema [Instrucciones de nomenclatura](../Topic/Naming%20Guidelines.md).  
  
-   No utilice "Mi" o "mi" como parte de un nombre de variable.  Esta práctica crea confusión con los objetos `My`.  
  
-   No tiene que cambiar los nombres de objetos en código generado automáticamente para que se ajusten a las directrices.  
  
## Convenciones de diseño  
  
-   Inserte tabulaciones como espacios y use la sangría inteligente con sangrías de cuatro espacios.  
  
-   Utilice **Lista descriptiva \(nuevo formato\) de código** para volver a aplicar formato al código en el Editor de código.  Para obtener más información, vea [Opciones, editor de texto, básico \(Visual Basic\)](/visual-studio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Utilice sólo una instrucción por línea.  No utilice el carácter separador de línea de Visual Basic \(:\).  
  
-   Evite utilizar el carácter de continuación de línea explícito "\_" a favor de la continuación de línea implícita siempre que el lenguaje lo permita.  
  
-   Utilice sólo una declaración por línea.  
  
-   Si **Lista descriptiva \(nuevo formato\) de código** no da formato a las líneas de continuación automáticamente, aplique manualmente una tabulación a las líneas de continuación para aplicar la sangría.  Sin embargo, alinee siempre los elementos de una lista a la izquierda.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Agregue al menos una línea en blanco entre el método y las definiciones de propiedad.  
  
## Convenciones de los comentarios  
  
-   Ponga los comentarios en una línea independiente, no al final de una línea de código.  
  
-   Comience el texto del comentario con una letra en mayúscula y finalice el texto del comentario con un punto.  
  
-   Inserte un espacio entre el delimitador de comentario \('\) y el texto del comentario.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   No incluya bloques de asterisco con formato alrededor de los comentarios.  
  
## Estructura del programa  
  
-   Al usar el método `Main`, utilice la construcción predeterminada para las nuevas aplicaciones de consola y utilice `My` para los argumentos de la línea de comandos.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## Convenciones de lenguaje  
  
### String \(Tipo de datos\)  
  
-   Para concatenar cadenas, use una Y comercial \(&\).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Para anexar cadenas en bucles, utilice el objeto <xref:System.Text.StringBuilder>.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### Delegados flexibles en controladores de eventos  
 No califique explícitamente los argumentos \(Object y EventArgs\) como controladores de eventos.  Si no usa los argumentos de evento que se pasan a un evento \(por ejemplo, el remitente como objeto como EventArgs\), utilice los delegados flexibles y no incluya argumentos de evento en el código:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### Tipo de datos sin signo  
  
-   Utilice `Integer` en lugar de tipos sin signo, excepto cuando sean necesarios.  
  
### Matrices  
  
-   Conviene usar la sintaxis breve al inicializar matrices en la línea de declaración.  Por ejemplo, puede usar la siguiente sintaxis.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     No use la sintaxis siguiente.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Sitúe el designador en el tipo, no en la variable.  Por ejemplo, puede usar la siguiente sintaxis:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Utilice la sintaxis {} al declarar e inicializar matrices de tipos de datos básicos.  Por ejemplo, puede usar la siguiente sintaxis:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     No use la sintaxis siguiente:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### Utilice la palabra clave With  
 Cuando realice una serie de llamadas a un objeto, considere la posibilidad de utilizar la palabra clave `With`.  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### Use las instrucciones Try...Catch y Using cuando use el Control de excepciones  
 No utilice `On Error Goto`.  
  
### Utilizar la palabra clave IsNot  
 Use la palabra clave `IsNot` en lugar de `Not...Is Nothing`.  
  
### New \(Palabra clave\)  
  
-   Usar la creación de instancias abreviadas.  Por ejemplo, puede usar la siguiente sintaxis:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     La línea anterior es equivalente a esto:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Utilice los inicializadores de objeto para los nuevos objetos en lugar del constructor sin parámetros:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### Control de eventos  
  
-   Utilice `Handles` en lugar de `AddHandler`.  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Utilice `AddressOf` y no cree instancias explícitas del delegado:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   Cuando defina un evento, utilice la sintaxis corta y permita que el compilador defina el delegado:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   No compruebe si un evento es `Nothing` \(null\) antes de llamar al método `RaiseEvent`.  `RaiseEvent` comprueba `Nothing` antes de generar el evento.  
  
### Utilizar miembros compartidos  
 Llame a los miembros `Shared` utilizando el nombre de clase y no una variable de instancia.  
  
### Utilizar literales XML  
 Los literales XML simplifican las tareas más comunes con las que se encuentra al trabajar con XML \(por ejemplo, cargar, consultar y transformar\).  Al desarrollar con XML, siga estas instrucciones:  
  
-   Utilice literales XML para crear documentos y fragmentos XML en lugar de llamar directamente a API XML.  
  
-   Importe espacios de nombres XML al archivo o nivel de proyecto para sacar partido de la optimización del rendimiento para los literales XML.  
  
-   Utilice las propiedades de eje XML para tener acceso a elementos y atributos en un documento XML.  
  
-   Utilice expresiones incrustadas para incluir valores y crear XML a partir de valores existentes en lugar de utilizar llamadas API como el método `Add`:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### Consultas LINQ  
  
-   Utilice nombres descriptivos para las variables de consulta:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Proporcione nombres para elementos en una consulta para asegurarse de que los nombres de propiedad de tipos anónimos se escriben con las mayúsculas correctas mediante la grafía Pascal:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Cambie el nombre de las propiedades cuando los nombres de propiedad en el resultado puedan ser ambiguos.  Por ejemplo, si la consulta devuelve un nombre de cliente y un Id. de pedido, cámbieles el nombre en lugar de dejarlos como `Name` e `ID` en el resultado:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Utilice la inferencia de tipos en la declaración de variables de consulta y variables de intervalo:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Alinee las cláusulas de consulta bajo la instrucción `From`:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Utilice las cláusulas `Where` antes de otras cláusulas de consulta de forma que las cláusulas de consulta posteriores operen en el conjunto de datos filtrado:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Utilice la cláusula `Join` para definir explícitamente una operación de unión en lugar de utilizar la cláusula `Where` para definir implícitamente una operación de unión:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## Vea también  
 [Secure Coding Guidelines](../Topic/Secure%20Coding%20Guidelines.md)