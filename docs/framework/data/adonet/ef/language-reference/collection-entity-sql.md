---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: d4e52bb62412e61e1a71e0fe9a8555068ca18dbd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506464"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
La palabra clave COLLECTION solo se usa en la definición de una función inline. Las funciones de colección son funciones que operan en una colección de valores y generan un resultado escalar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a>Argumentos  
 `type_definition`  
 Una expresión que devuelve una colección de tipos, filas o referencias compatibles.  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre la palabra clave COLLECTION, vea [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la palabra clave COLLECTION para declarar una colección de decimales como un argumento para una función inline de consulta.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>Vea también
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
