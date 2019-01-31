---
title: Operaciones de agregación (C#)
ms.date: 07/20/2015
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
ms.openlocfilehash: fd526a971e3d894a1219d06ee66127fddff07025
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692225"
---
# <a name="aggregation-operations-c"></a>Operaciones de agregación (C#)
Una operación de agregación calcula un valor único a partir de una colección de valores. Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.  
  
 En la siguiente ilustración se muestran los resultados de dos operaciones de agregación diferentes en una secuencia de números. La primera operación suma los números. La segunda operación devuelve el valor máximo de la secuencia.  
  
 ![Operaciones de agregación en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")  
  
 Los métodos del operador de consulta estándar que realizan operaciones de agregación se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Agregar|Realiza una operación de agregación personalizada en los valores de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Average|Calcula el valor medio de una colección de valores.|No es aplicable.|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Recuento|Cuenta los elementos de una colección; opcionalmente, solo aquellos que satisfacen una función de predicado.|No es aplicable.|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Cuenta los elementos de una gran colección; opcionalmente, solo aquellos que satisfacen una función de predicado.|No es aplicable.|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Máx.|Determina el valor máximo de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Mín.|Determina el valor mínimo de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Sum|Calcula la suma de los valores de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))
- [Cómo: Calcular valores de columna en un archivo de texto CSV (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Cómo: Buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)
- [Cómo: Buscar el número total de bytes en un conjunto de carpetas (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)
