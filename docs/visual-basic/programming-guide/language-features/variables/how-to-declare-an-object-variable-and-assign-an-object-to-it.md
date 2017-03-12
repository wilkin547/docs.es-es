---
title: "C&#243;mo: Declarar una variable de objeto y asignarle un objeto en Visual Basic | Microsoft Docs"
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
  - "declarar variables de objeto"
  - "variables de objeto, declarar"
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# C&#243;mo: Declarar una variable de objeto y asignarle un objeto en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara una variable de [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md) especificando `As Object` en [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md).  Asigna un objeto a este tipo de variable colocando el objeto después del signo igual \(`=`\) en una instrucción de asignación o una cláusula de inicialización.  
  
## Ejemplo  
 En el siguiente ejemplo se declara una variable `Object` y se le asigna la instancia actual.  
  
```  
  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 Puede combinar la declaración y la asignación inicializando la variable como parte de su declaración.  El ejemplo siguiente es equivalente al ejemplo anterior.  
  
```  
Dim thisObject As Object = "This is an Object"  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System>.  
  
-   Una clase, estructura o módulo en las que colocar la instrucción `Dim`.  
  
-   Un procedimiento en el que colocar la instrucción de asignación.  
  
## Vea también  
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)