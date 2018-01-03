---
title: CAST (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 97971668430dd7721b15a4ac60e422fe06f0ed1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cast-entity-sql"></a>CAST (Entity SQL)
Convierte una expresión de un tipo de datos a otro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión válida que se pueda convertir a `data_type`.  
  
 `data_type`  
 Tipo de datos de destino proporcionado por el sistema. Debe ser un tipo (escalar) primitivo. El valor de `data_type` usado depende del espacio de la consulta. Si se ejecuta una consulta con la clase <xref:System.Data.EntityClient.EntityCommand>, el tipo de datos es un tipo definido en el modelo conceptual. Para obtener más información, consulta [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md). Si se ejecuta una consulta con la clase <xref:System.Data.Objects.ObjectQuery%601>, el tipo de datos es un tipo de Common Language Runtime (CLR).  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve el mismo valor que `data_type`.  
  
## <a name="remarks"></a>Comentarios  
 La expresión de conversión tiene una semántica similar a la expresión CONVERT de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] . La expresión de conversión se utiliza para convertir un valor de un tipo en un valor de otro tipo.  
  
```  
CAST( e as T )  
```  
  
 Si e es de un tipo S, y S se puede convertir a T, la expresión anterior es una expresión de conversión válida. T debe ser un tipo (escalar) primitivo.  
  
 Se pueden proporcionar opcionalmente valores para las facetas de precisión y escala al convertir a `Edm.Decimal`. Si no se proporcionan explícitamente, los valores predeterminados para la precisión y la escala son 18 y 0, respectivamente. Concretamente, las sobrecargas siguientes son compatibles con `Decimal`:  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 El uso de una expresión de conversión se considera una conversión explícita. Las conversiones explícitas pueden truncar datos o perder precisión.  
  
> [!NOTE]
>  CAST solo se admite en tipos primitivos y tipos de miembro de enumeración.  
  
## <a name="example"></a>Ejemplo  
 La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador CAST para convertir una expresión de un tipo de datos a otro. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
