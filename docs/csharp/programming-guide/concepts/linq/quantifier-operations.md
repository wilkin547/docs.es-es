---
title: Operaciones cuantificadoras (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 090bc53c3dcedc82972ab7d16fa2968011a7db65
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412258"
---
# <a name="quantifier-operations-c"></a>Operaciones cuantificadoras (C#)
Las operaciones cuantificadoras devuelven un valor <xref:System.Boolean> que indica si algunos o todos los elementos de una secuencia cumplen una condición.  
  
 En la siguiente ilustración se muestran dos operaciones cuantificadoras diferentes en dos secuencias de origen distintas. La primera operación pregunta si uno o varios de los elementos son el carácter "A", y el resultado es `true`. La segunda operación pregunta si todos los elementos son el carácter "A", y el resultado es `true`.  
  
 ![Operaciones cuantificadoras en LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 Los métodos del operador de consulta estándar que realizan operaciones cuantificadoras se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Todas|Determina si todos los elementos de una secuencia cumplen una condición.|No es aplicable.|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Cualquiera|Determina si algunos de los elementos de una secuencia cumplen una condición.|No es aplicable.|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Contiene|Determina si una secuencia contiene un elemento especificado.|No es aplicable.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))
- [Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
