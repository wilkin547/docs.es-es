---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: c960ee69f8188f6dd3184b6fb31f3432f8d58fee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197955"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)

La palabra clave COLLECTION solo se usa en la definición de una función inline. Las funciones de colección son funciones que operan en una colección de valores y generan un resultado escalar.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a>Argumentos  

 `type_definition`  
 Una expresión que devuelve una colección de tipos, filas o referencias compatibles.  
  
## <a name="remarks"></a>Observaciones  

 Para obtener más información sobre la palabra clave COLLECTION, vea [Type Definitions](type-definitions-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo usar la palabra clave COLLECTION para declarar una colección de decimales como un argumento para una función inline de consulta.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
