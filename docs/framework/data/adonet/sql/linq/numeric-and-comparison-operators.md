---
title: Operadores numéricos y de comparación
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: e2bdc55cd6c2203bc96d0766e5e53a57294d4d7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554717"
---
# <a name="numeric-and-comparison-operators"></a>Operadores numéricos y de comparación
Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime (CLR), con las siguientes excepciones:  
  
-   SQL no admite al operador de módulo en números de punto flotante.  
  
-   SQL no admite la aritmética no comprobada.  
  
-   Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.  
  
## <a name="supported-operators"></a>Operadores compatibles  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite los operadores siguientes.  
  
-   Operadores aritméticos básicos:  
  
    -   `+`  
  
    -   `-` (resta)  
  
    -   `*`  
  
    -   `/`  
  
    -   División de enteros en Visual Basic (`\`)  
  
    -   `%` (Visual Basic `Mod`)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` (negación unaria)  
  
-   Operadores de comparación básicos:  
  
    -   `=` en Visual Basic y `==` en C#  
  
    -   `<>` en Visual Basic y `!=` en C#  
  
    -   `Is/IsNot` en Visual Basic  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>Vea también
- [Tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [Operadores de C#](../../../../../../docs/csharp/language-reference/operators/index.md)
- [Operadores](../../../../../visual-basic/language-reference/operators/index.md)
