---
title: Operaciones cuantificadoras (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7f69aed2e0e6791ca7f17c3420ff75a1ba220187
ms.lasthandoff: 03/13/2017

---
# <a name="quantifier-operations-visual-basic"></a>Operaciones cuantificadoras (Visual Basic)
Operaciones cuantificadoras devuelven un <xref:System.Boolean>valor que indica si algunos o todos los elementos de una secuencia satisfacen una condición.</xref:System.Boolean>  
  
 La siguiente ilustración muestra dos operaciones cuantificadoras diferentes en dos secuencias de origen diferentes. La primera operación pregunta si uno o varios de los elementos son el carácter 'A', y el resultado es `true`. La segunda operación pregunta si todos los elementos son el carácter 'A', y el resultado es `true`.  
  
 ![Operaciones cuantificadoras en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 Los métodos de operador de consulta estándar que realizan operaciones cuantificadoras se enumeran en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Todas|Determina si todos los elementos de una secuencia satisfacen una condición.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName>|  
|Cualquiera|Determina si algún elemento de una secuencia satisfacen una condición.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName>|  
|Contiene|Determina si una secuencia contiene un elemento especificado.|No es aplicable.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
 Estos ejemplos utilizan el `Aggregate` en Visual Basic como parte de la condición de filtro en una consulta LINQ.  
  
 En el ejemplo siguiente se utiliza la `Aggregate` cláusula y <xref:System.Linq.Enumerable.All%2A>método de extensión para devolver de una colección las personas cuyos animales domésticos tienen más de una edad especificada.</xref:System.Linq.Enumerable.All%2A>  
  
 [!code-vb[1 CsLINQAnyAll](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 En el ejemplo siguiente se utiliza la `Aggregate` cláusula y <xref:System.Linq.Enumerable.Any%2A>método de extensión para devolver de una colección de aquellas personas que tienen al menos un animal doméstico que es anterior a una edad especificada.</xref:System.Linq.Enumerable.Any%2A>  
  
 [!code-vb[CsLINQAnyAll&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq></xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Cómo: buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
