---
title: Calcular la suma de valores de una secuencia numérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 3a404068c2d89610aa9b01b392bca40f82e17707
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247929"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a>Calcular la suma de valores de una secuencia numérica
Utilice el operador <xref:System.Linq.Enumerable.Sum%2A> para calcular la suma de los valores numéricos de una secuencia.  
  
 Tenga en cuenta las características siguientes del operador `Sum` en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
- El operador de consulta estándar de agregado `Sum` se evalúa como cero para una secuencia vacía o una secuencia que solo contiene valores nulos. En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la semántica de SQL se mantiene invariable. Por esta razón, `Sum` se evalúa como Null en lugar de cero en el caso de secuencias vacías o secuencias que solo contienen valores nulos.  
  
- En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se aplican las restricciones de SQL para los agregados en los resultados intermedios. La suma de las cantidades de enteros de 32 bits no se calcula mediante resultados de 64 bits y se puede producir un desbordamiento para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la traducción `Sum`de. Esta posibilidad existe aun cuando la implementación del operador de consulta estándar no produzca un desbordamiento para la secuencia en memoria correspondiente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se busca el flete total de todos los pedidos de la tabla `Order`.  
  
 Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `64942.6900`.  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se busca el número total de unidades pedidas para todos los productos.  
  
 Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `780`.  
  
 Tenga en cuenta que debe convertir los tipos `short` (por ejemplo, `UnitsOnOrder`) porque `Sum` no tiene una sobrecarga para ellos.  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a>Vea también

- [Consultas de agregado](aggregate-queries.md)
- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
