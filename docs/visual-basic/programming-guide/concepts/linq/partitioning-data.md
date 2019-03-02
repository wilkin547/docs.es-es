---
title: Creación de particiones de datos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 06db2ac3e556e647fed576a7fa0c89b881b748c9
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202150"
---
# <a name="partitioning-data-visual-basic"></a>Creación de particiones de datos (Visual Basic)
Partición en LINQ es la operación de dividir una secuencia de entrada en dos secciones, sin reorganizar los elementos, y devolver después una de las secciones.  
  
 En la siguiente ilustración se muestran los resultados de tres operaciones de partición diferentes en una secuencia de caracteres. La primera operación devuelve los tres primeros elementos de la secuencia. La segunda operación omite los tres primeros elementos y devuelve los restantes. La tercera operación omite los dos primeros elementos de la secuencia y devuelve los tres siguientes.  
  
 ![Operaciones de partición en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 Los métodos de operador de consulta estándar que realizan particiones de las secuencias se enumeran en la sección siguiente.  
  
## <a name="operators"></a>Operadores  
  
|Nombre de operador|Descripción|Sintaxis de expresión de consulta de Visual Basic|Más información|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|Omite los elementos hasta una determinada posición de una secuencia.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Omite los elementos según una función de predicado hasta que un elemento no satisface la condición.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Admite los elementos hasta una determinada posición de una secuencia.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Admite los elementos según una función de predicado hasta que un elemento no satisface la condición.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
  
### <a name="skip"></a>Skip  
 El siguiente ejemplo de código utiliza el `Skip` cadenas en Visual Basic para omitir las cuatro primeras cadenas de una matriz de cadenas antes de devolver el resto de la matriz.  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a>SkipWhile  
 El siguiente ejemplo de código utiliza el `Skip While` cláusula en Visual Basic para omitir las cadenas en una matriz mientras la primera letra de la cadena es "a". Se devuelven las cadenas restantes de la matriz.  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a>Take  
 El siguiente ejemplo de código utiliza el `Take` cláusula en Visual Basic para devolver las primeras dos cadenas en una matriz de cadenas.  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a>TakeWhile  
 El siguiente ejemplo de código utiliza el `Take While` cláusula en Visual Basic para devolver las cadenas de una matriz, mientras que la longitud de la cadena es cinco o menos.  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Skip (cláusula)](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [Skip While (cláusula)](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take (cláusula)](../../../../visual-basic/language-reference/queries/take-clause.md)
- [Take While (cláusula)](../../../../visual-basic/language-reference/queries/take-while-clause.md)
