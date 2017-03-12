---
title: "C&#243;mo: Controlar el &#225;mbito de una variable (Visual Basic) | Microsoft Docs"
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
  - "elementos declarados, ámbito"
  - "elementos declarados, visibilidad"
  - "ámbito, elementos declarados"
  - "ámbito, variables"
  - "ámbito, Visual Basic"
  - "variables [Visual Basic], ámbito"
  - "variables [Visual Basic], visibilidad"
  - "visibilidad, elementos declarados"
  - "visibilidad, variables"
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# C&#243;mo: Controlar el &#225;mbito de una variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Normalmente, una variable está en *ámbito*, o visible para referencia, en toda la región donde se declara.  En algunos casos, el *nivel de acceso* de la variable puede influir en su ámbito.  
  
 Para obtener más información, vea [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## Ámbito en el nivel de bloque o procedimiento  
  
#### Para hacer que una variable sea visible sólo dentro de un bloque  
  
-   Coloque [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) para la variable entre las instrucciones de declaración de inicio y fin de ese bloque, por ejemplo entre las instrucciones `For` y `Next` de un bucle `For`.  
  
     Sólo puede hacer referencia a la variable desde dentro del bloque.  
  
#### Para hacer que una variable sea visible sólo dentro de un procedimiento  
  
-   Coloque la instrucción `Dim` para la variable dentro del procedimiento pero fuera de cualquier bloque \(como un bloque `With`...`End With`\).  
  
     Sólo puede hacer referencia a la variable desde dentro del procedimiento, incluyendo dentro de cualquier bloque contenido en el procedimiento.  
  
## Ámbito en el nivel de módulo o espacio de nombres  
 Por comodidad, el término *nivel de módulo* se aplica por igual a módulos, clases y estructuras.  El nivel de acceso de una variable de nivel de módulo determina su ámbito.  El espacio de nombres que contiene el módulo, la clase o la estructura también influye en el ámbito.  
  
#### Para hacer que una variable sea visible en todo un módulo, clase o estructura  
  
1.  Coloque la instrucción `Dim` para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2.  Incluya la palabra clave [Private](../../../../visual-basic/language-reference/modifiers/private.md) en la instrucción `Dim`.  
  
3.  Puede hacer referencia a la variable desde cualquier parte dentro del módulo, clase o estructura, pero no desde fuera de él.  
  
#### Para hacer que una variable sea visible en todo un espacio de nombres  
  
1.  Coloque la instrucción `Dim` para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2.  Incluya la palabra clave [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [Public](../../../../visual-basic/language-reference/modifiers/public.md) en la instrucción `Dim`.  
  
3.  Puede hacer referencia a la variable desde cualquier parte dentro del espacio de nombres que contiene el módulo, clase o estructura.  
  
## Ejemplo  
 En el ejemplo siguiente se declara una variable en el nivel de módulo y se limita su visibilidad al código dentro del módulo.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 En el ejemplo anterior, todos los procedimientos definidos en el módulo `demonstrateScope` pueden hacer referencia a la variable `String` `strMsg`.  Cuando se llama al procedimiento `usePrivateVariable`, se muestra el contenido de la variable `strMsg` en un cuadro de diálogo.  
  
 La siguiente modificación del ejemplo anterior permite que el código haga referencia a la variable de cadena `strMsg` en cualquier parte del espacio de nombres de su declaración.  
  
```  
Public strMsg As String  
```  
  
## Programación eficaz  
 Cuanto más estrecho sea el ámbito de una variable, menos probabilidades tendrá de hacer referencia accidentalmente a ella en lugar de a otra variable con el mismo nombre.  También puede minimizar los problemas de concordancia de referencias.  
  
## Seguridad de .NET Framework  
 Cuanto más estrecho sea el ámbito de una variable, menos posibilidades habrá de que un código malintencionado puede hacer un uso indebido de ella.  
  
## Vea también  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Período de duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md)