---
title: "La variable &#39;&lt;nombredevariable&gt;&#39; oculta una variable en un bloque de inclusi&#243;n | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30616"
  - "bc30616"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30616"
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# La variable &#39;&lt;nombredevariable&gt;&#39; oculta una variable en un bloque de inclusi&#243;n
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una variable incluida en un bloque tiene el mismo nombre que otra variable local.  
  
 **Identificador de error:** BC30616  
  
### Para corregir este error  
  
-   Cambie el nombre de la variable del bloque contenedor para que sea diferente de cualquier otra variable local.  Por ejemplo:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Una de las causas comunes que pueden producir este error es el uso de `Catch e As Exception` dentro de un controlador de eventos.  Si este es el caso, asigne el nombre `ex` en lugar de `e` a la variable del bloque `Catch`.  
  
-   Otro motivo por el cual puede producirse este error es un intento de obtener acceso a una variable local declarada dentro de un bloque `Try` en un bloque `Catch` separado.  Para corregir este error, declare la variable fuera de la estructura `Try...Catch...Finally`.  
  
## Vea también  
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Declaración de variable](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)