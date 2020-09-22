---
title: Cláusula Group By
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: b60f6759ada845d8eab048bceb1e47f9546ee7d0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869944"
---
# <a name="group-by-clause-visual-basic"></a>Group By (Cláusula, Visual Basic)

Agrupa los elementos de los resultados de una consulta. También se puede usar para aplicar funciones de agregado a cada grupo. La operación de agrupación se basa en una o varias claves.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a>Partes  
  
- `listField1`, `listField2`  
  
     Opcional. Uno o más campos de la variable o las variables de consulta que identifican explícitamente los campos que se incluirán en el resultado agrupado. Si no se especifica ningún campo, se incluyen todos los campos de la variable o las variables de consulta en el resultado agrupado.  
  
- `keyExp1`  
  
     Obligatorio. Expresión que identifica la clave que se va a usar para determinar los grupos de elementos. Puede especificar más de una clave para especificar una clave compuesta.  
  
- `keyExp2`  
  
     Opcional. Uno o más claves adicionales que se combinan con `keyExp1` para crear una clave compuesta.  
  
- `aggregateList`  
  
     Obligatorio. Una o más expresiones que identifican cómo se agregan los grupos. Para identificar un nombre de miembro para los resultados agrupados, use la palabra clave `Group` , que puede estar en cualquiera de los formatos siguientes:  
  
    ```vb  
    Into Group  
    ```  
  
     o bien  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     También puede incluir funciones de agregado para aplicar al grupo.  
  
## <a name="remarks"></a>Comentarios  

 Puede usar la cláusula `Group By` para dividir los resultados de una consulta en grupos. La agrupación se basa en una clave o una clave compuesta formada por varias claves. Los elementos que están asociados con valores de clave coincidentes se incluyen en el mismo grupo.  
  
 El parámetro `aggregateList` de la cláusula `Into` y la palabra clave `Group` se usan para identificar el nombre del miembro usado para hacer referencia al grupo. También puede incluir funciones de agregado en la cláusula `Into` para calcular los valores de los elementos agrupados. Para obtener una lista de las funciones de agregado estándar, consulte [Aggregate Clause](aggregate-clause.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se agrupa una lista de clientes según su ubicación (país o región) y se proporciona un recuento de los clientes de cada grupo. Los resultados se ordenan por nombre de país o región. Los resultados agrupados se ordenan por nombre de ciudad.  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula FROM](from-clause.md)
- [Cláusula order by](order-by-clause.md)
- [Aggregate Clause](aggregate-clause.md)
- [Cláusula Group Join](group-join-clause.md)
