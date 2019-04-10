---
title: Realizar particiones de datos (C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: b857c8c6e6b56a7263e6725a747e98ccfe4ff4fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832468"
---
# <a name="partitioning-data-c"></a>Realizar particiones de datos (C#)
Partición en LINQ es la operación de dividir una secuencia de entrada en dos secciones, sin reorganizar los elementos, y devolver después una de las secciones.  
  
 En la siguiente ilustración se muestran los resultados de tres operaciones de partición diferentes en una secuencia de caracteres. La primera operación devuelve los tres primeros elementos de la secuencia. La segunda operación omite los tres primeros elementos y devuelve los restantes. La tercera operación omite los dos primeros elementos de la secuencia y devuelve los tres siguientes.  
  
 ![Ilustración que muestra tres operaciones de creación de particiones de LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Los métodos de operador de consulta estándar que realizan particiones de las secuencias se enumeran en la sección siguiente.  
  
## <a name="operators"></a>Operadores  
  
|Nombre de operador|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Skip|Omite los elementos hasta una determinada posición de una secuencia.|No es aplicable.|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Omite los elementos según una función de predicado hasta que un elemento no satisface la condición.|No es aplicable.|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Admite los elementos hasta una determinada posición de una secuencia.|No es aplicable.|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Admite los elementos según una función de predicado hasta que un elemento no satisface la condición.|No es aplicable.|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))
