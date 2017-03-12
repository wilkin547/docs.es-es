---
title: "Estructuras de control adicionales (Visual Basic) | Microsoft Docs"
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
  - "estructuras de controles"
  - "instrucciones [Visual Basic], flujo de control"
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Estructuras de control adicionales (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona estructuras de control que ayudan a eliminar de un recurso o reducen el número de veces que tiene que repetir una referencia de objeto.  
  
## Construcción Using...End Using  
 La construcción `Using...End Using` establece un bloque de instrucciones dentro del cual utiliza un recurso como una conexión de SQL.  Puede adquirir el recurso opcionalmente con la instrucción `Using`.  Cuando sale del bloque `Using`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] dispone automáticamente del recurso para que esté disponible para otro código.  El recurso debe ser local y ser descartable.  Para obtener más información, vea [Using \(Instrucción\)](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## Construcción With...End With  
 La construcción `With...End With` le permite especificar una referencia de objeto una vez y ejecutar luego una serie de instrucciones que tienen acceso a sus miembros.  Esto puede simplificar su código y mejorar el rendimiento porque [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no tiene que restablecer la referencia para cada instrucción que tiene acceso a él.  Para obtener más información, vea [With...End With \(Instrucción\)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## Vea también  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Estructuras de bucles](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Using \(Instrucción\)](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [With...End With \(Instrucción\)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)