---
title: Crear particiones de datos (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a746ce3e24812d1df6b6e221cca0364bf2cc7f1c
ms.lasthandoff: 03/13/2017

---
# <a name="partitioning-data-visual-basic"></a>Crear particiones de datos (Visual Basic)
Creación de particiones en LINQ hace referencia a la operación de dividir una secuencia de entrada en dos secciones, sin reorganizar los elementos y, a continuación, devolver una de las secciones.  
  
 La ilustración siguiente muestra los resultados de tres operaciones de partición diferentes en una secuencia de caracteres. La primera operación devuelve los tres primeros elementos de la secuencia. La segunda operación omite los tres primeros elementos y devuelve los elementos restantes. La tercera operación omite los dos primeros elementos de la secuencia y devuelve los tres elementos.  
  
 ![Las operaciones de creación de particiones de LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 Los métodos de operador de consulta estándar que partición de las secuencias se enumeran en la sección siguiente.  
  
## <a name="operators"></a>Operadores  
  
|Nombre de operador|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|Omite los elementos hasta una posición especificada en una secuencia.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName>|  
|SkipWhile|Omite los elementos según una función de predicado hasta que un elemento no cumple la condición.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName>|  
|Take|Admite los elementos hasta una posición especificada en una secuencia.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName>|  
|TakeWhile|Admite los elementos según una función de predicado hasta que un elemento no cumple la condición.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
  
### <a name="skip"></a>Skip  
 El siguiente ejemplo de código utiliza el `Skip` cláusula en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para omitir las cuatro primeras cadenas de una matriz de cadenas antes de devolver las cadenas restantes de la matriz.  
  
 [!code-vb[1 CsLINQPartitioning](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 El siguiente ejemplo de código utiliza el `Skip While` cláusula en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] omitir las cadenas de una matriz mientras la primera letra de la cadena es "a". Se devuelven las cadenas restantes de la matriz.  
  
 [!code-vb[CsLINQPartitioning&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 El siguiente ejemplo de código utiliza el `Take` cláusula en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para devolver las dos primeras cadenas de una matriz de cadenas.  
  
 [!code-vb[CsLINQPartitioning&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 El siguiente ejemplo de código utiliza el `Take While` cláusula en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para devolver las cadenas de una matriz mientras la longitud de la cadena es cinco o menos.  
  
 [!code-vb[CsLINQPartitioning Nº&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq></xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Skip (cláusula)](../../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Skip While (cláusula)](../../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take (cláusula)](../../../../visual-basic/language-reference/queries/take-clause.md)   
 [Take While (cláusula)](../../../../visual-basic/language-reference/queries/take-while-clause.md)
