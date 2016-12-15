---
title: "Caracteres especiales en c&#243;digo (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.)"
  - "vb.("
  - "vb.colon"
  - "vb.!"
  - "vb.."
  - "vb.:"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "! (operador)"
  - ". (operador)"
  - "carácter separador :"
  - "operador de suma"
  - "dos puntos (:)"
  - "operadores de concatenación, caracteres especiales en el código"
  - "operadores de concatenación, operador de suma"
  - "operador de acceso al diccionario"
  - "operador de punto (.)"
  - "operador signo de exclamación (!)"
  - "signos de exclamación"
  - "operador de acceso a miembros"
  - "operadores [Visual Basic], tener acceso al diccionario"
  - "operadores [Visual Basic], tener acceso a miembros"
  - "paréntesis, utilizar en el código"
  - "carácter de punto en el código"
  - "separadores"
  - "separadores, utilizar en el código"
  - "caracteres especiales, en el código"
  - "código de Visual Basic, caracteres especiales"
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Caracteres especiales en c&#243;digo (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

A veces es necesario usar caracteres especiales en el código, es decir, caracteres que no son alfabéticos o numéricos.  Los caracteres de puntuación y especiales del juego de caracteres de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tienen varias finalidades, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado.  No especifican que se deba realizar una operación.  
  
## Paréntesis  
 Utilice paréntesis al definir un procedimiento, como `Sub` o `Function`.  Debe incluir entre paréntesis todas las listas de argumentos de los procedimientos.  También se utilizan paréntesis para agrupar las variables o argumentos en grupos lógicos, en particular para reemplazar el orden predeterminado de prioridad de operadores en una expresión compleja.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 Tras la ejecución del código anterior, el valor de `d` es 8,225 y el valor de `e` es 3.  El cálculo de `d` utiliza la prioridad predeterminada de `/` sobre `+` y es equivalente a `d = b + (c / a)`.  Los paréntesis del cálculo para `e` reemplazan la prioridad predeterminada.  
  
## Separadores  
 Los separadores hacen lo que su nombre sugiere; separan secciones de código.  En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], el carácter separador corresponde a los dos puntos \(`:`\).  Utilice los separadores se desea incluir varias instrucciones en una única línea en lugar de escribirlas en líneas independientes.  Esto ahorra espacio y mejora la legibilidad del código.  En el ejemplo siguiente se muestran tres instrucciones separadas por dos puntos.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Para obtener más información, vea [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 El carácter de dos puntos \(`:`\) también se utiliza para identificar una etiqueta de instrucción.  Para obtener más información, vea [Cómo: Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## Concatenación  
 Utilice el operador `&` para *concatenar* o vincular cadenas entre sí.  No lo confunda con el operador `+`, que suma valores numéricos.  Si utiliza el operador `+` para concatenar cuando está operando con valores numéricos, puede obtener resultados no deseados.  En el siguiente ejemplo se muestra cómo.  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 Siguiendo la ejecución del código anterior, el valor de `resultA` es 21,01 y el valor de `resultB` es "10,0111".  
  
## Operadores de acceso a miembros  
 Para tener acceso a un miembro de un tipo, utilice el operador punto \(`.`\) o signo de exclamación \(`!`\) entre el nombre del tipo y el nombre del miembro.  
  
### Punto \(.\) Operador  
 Utilice el operador `.` en una clase, estructura, interfaz o enumeración como operador de acceso a miembros.  El miembro puede ser un campo, una propiedad, un evento o un método.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### Signo de exclamación \(\!\) Operador  
 Utilice el operador `!`, sólo en una clase o interfaz, como operador de acceso al diccionario.  La clase o interfaz debe tener una propiedad predeterminada que acepte un solo argumento `String`.  El identificador que sigue inmediatamente al operador `!` se convierte en el valor del argumento pasado a la propiedad predeterminada como cadena.  En el siguiente ejemplo se muestra cómo.  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Las tres líneas de resultado de `MsgBox` muestran el valor `32856`.  La primera línea utiliza un acceso tradicional a la propiedad `index`, la segunda aprovecha el hecho de que `index` es la propiedad predeterminada de la clase `hasDefault` y la tercera usa el acceso de diccionario a la clase.  
  
 Observe que el segundo operando del operador `!` debe ser un identificador de Visual Basic válido que no esté entre comillas \(`" "`\).  Dicho de otra forma, no se puede utilizar un literal de cadena o una variable de cadena.  El cambio siguiente a la última línea de la llamada `MsgBox` genera un error porque `"X"` es un literal de cadena incluido entre comillas.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Las referencias a colecciones predeterminadas deben ser explícitas.  En particular, no es posible utilizar el operador `!` en una variable de enlace en tiempo de ejecución.  
  
 El carácter `!` también se utiliza como carácter de tipo `Single`.  
  
## Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)