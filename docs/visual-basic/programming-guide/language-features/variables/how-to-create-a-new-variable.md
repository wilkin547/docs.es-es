---
title: "C&#243;mo: Crear una nueva variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Dim (instrucción)"
  - "variables [Visual Basic], crear"
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# C&#243;mo: Crear una nueva variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Crea una variable con una instrucción [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### Para crear una nueva variable  
  
1.  Declare la variable con una instrucción `Dim`.  
  
    ```  
  
    Dim newCustomer  
    ```  
  
2.  Incluya las especificaciones para las características de la variable, como [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).  Para obtener más información, vea [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     No necesita la palabra clave `Dim` si utiliza otras palabras clave en la declaración.  
  
3.  Agregue a las especificaciones el nombre de la variable que debe seguir las reglas y convenciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Para obtener más información, vea [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  Agregue al nombre la cláusula [As](../../../../visual-basic/language-reference/statements/as-clause.md) para especificar el tipo de datos de la variable.  
  
    ```  
    Public Static newCustomer As Customer   
    ```  
  
     Si no especifica el tipo de datos, usará el valor predeterminado: `Object`.  
  
5.  Agregue a la cláusula `As` un signo igual \(`=`\) y agregue al signo igual el valor inicial de la variable.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] asigna el valor especificado a la variable cada vez que ejecuta la instrucción `Dim`.  Si no especifica un valor inicial, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] asigna el valor inicial predeterminado para el tipo de datos de la variable cuando escribe por primer vez el código que contiene la instrucción `Dim`.  
  
     Si la variable es un tipo de referencia, puede crear una instancia de su clase incluyendo la palabra clave [New \(Operador\)](../../../../visual-basic/language-reference/operators/new-operator.md) en la cláusula `As`.  Si no utiliza `New`, el valor inicial de la variable es [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## Vea también  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)