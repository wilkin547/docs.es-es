---
title: "C&#243;mo: Declarar enumeraciones (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaraciones, enumeraciones"
  - "declarar enumeraciones"
  - "enumeraciones [Visual Basic], declarar"
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# C&#243;mo: Declarar enumeraciones (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una enumeración se crea con la instrucción `Enum` en la sección de declaraciones de una clase o módulo.  No puede declarar una enumeración dentro de un método.  Para especificar el nivel adecuado de acceso, utilice `Private`, `Protected`, `Friend` o `Public`.  
  
 Un tipo `Enum` tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante.  El nombre debe ser un calificador de [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] válido.  El tipo subyacente debe ser uno de los tipos de enteros `Byte`, `Short`, `Long` o `Integer`.  `Integer` es el valor predeterminado.  Las enumeraciones están siempre fuertemente tipadas y no son intercambiables con los tipos de números enteros.  
  
 Las enumeraciones no pueden tener valores de punto flotante.  Si se asigna un valor de punto flotante a una enumeración con `Option Strict On`, se producirá un error del compilador.  Si `Option Strict` es `Off`, el valor se convierte automáticamente en el tipo `Enum`.  
  
 Para obtener información sobre los nombres y sobre cómo utilizar la instrucción `Imports` de manera que la calificación de nombres resulte innecesaria, consulte [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### Para declarar una enumeración  
  
1.  Escriba una declaración que incluya un nivel de acceso al código, la palabra clave `Enum` y un nombre válido, como en los ejemplos siguientes, cada uno de los cuales declara una palabra clave `Enum` diferente.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Defina las constantes en la enumeración.  De manera predeterminada, la primera constante de una enumeración se inicializa con `0` y las siguientes se inicializan con un valor igual al de la constante anterior más uno.  Por ejemplo, la siguiente enumeración, `Days`, contiene una constante denominada `Sunday` con el valor `0`, una constante denominada `Monday` con el valor `1`, una constante denominada `Tuesday` con el valor `2`, etc.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Se pueden asignar explícitamente valores a constantes en una enumeración mediante una instrucción de asignación.  Se puede asignar cualquier valor entero, incluidos números negativos.  Por ejemplo, puede que desee que las constantes con valores menores que cero representen condiciones de error.  En la siguiente enumeración, a la constante `Invalid` se le asigna explícitamente el valor `–1`, y a la constante `Sunday` se le asigna el valor `0`.  Como es la primera constante de la enumeración, `Saturday` también se inicializa con el valor `0`.  El valor de `Monday` es `1` \(el valor de `Sunday` más uno\); el valor de `Tuesday` es `2`, y así sucesivamente.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### Para declarar una enumeración como un tipo explícito  
  
-   Especifique el tipo de enumeración mediante la cláusula `As`, tal y como se muestra en el siguiente ejemplo.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## Vea también  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Cómo: Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Cómo: Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)