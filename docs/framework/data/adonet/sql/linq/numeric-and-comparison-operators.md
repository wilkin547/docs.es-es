---
title: "Operadores num&#233;ricos y de comparaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Operadores num&#233;ricos y de comparaci&#243;n
Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime \(CLR\), con las siguientes excepciones:  
  
-   SQL no admite al operador de módulo en números de punto flotante.  
  
-   SQL no admite la aritmética no comprobada.  
  
-   Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.  
  
## Operadores compatibles  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite los operadores siguientes.  
  
-   Operadores aritméticos básicos:  
  
    -   `+`  
  
    -   `-` \(resta\)  
  
    -   `*`  
  
    -   `/`  
  
    -   División de enteros en Visual Basic \(`\`\)  
  
    -   `%` \(Visual Basic `Mod`\)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` \(negación unaria\)  
  
-   Operadores de comparación básicos:  
  
    -   `=` en Visual Basic y `==` en C\#  
  
    -   `<>` en Visual Basic y `!=` en C\#  
  
    -   `Is/IsNot` en Visual Basic  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## Vea también  
 [Funciones y tipos de datos](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)   
 [operadores de C\#](../Topic/C%23%20Operators.md)   
 [Operadores](../Topic/Operators%20\(Visual%20Basic\).md)