---
title: Operaciones cuantificadoras (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9bc48c69179b1f8876efaa465295e94a9a0e0fb6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="quantifier-operations-visual-basic"></a>Operaciones cuantificadoras (Visual Basic)
Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.  
  
 En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas. La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`. La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.  
  
 ![Operaciones cuantificadoras en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Todas|Determina si todos los elementos de una secuencia cumplen una condición.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Cualquiera|Determina si algunos de los elementos de una secuencia cumplen una condición.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Contiene|Determina si una secuencia contiene un elemento especificado.|No es aplicable.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
 Estos ejemplos utilizan la `Aggregate` cláusula en Visual Basic como parte de la condición de filtrado en una consulta LINQ.  
  
 En el ejemplo siguiente se usa el `Aggregate` cláusula y <xref:System.Linq.Enumerable.All%2A> método de extensión para devolver de una colección de las personas cuyos animales domésticos tienen más de una edad especificada.  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 En el ejemplo siguiente se utiliza la `Aggregate` cláusula y <xref:System.Linq.Enumerable.Any%2A> método de extensión para devolver de una colección de aquellas personas que tienen al menos un animal doméstico que es anterior a una edad especificada.  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq>  
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Cómo: buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
