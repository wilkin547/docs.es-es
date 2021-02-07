---
description: Más información acerca de:--(comentario) (Entity SQL)
title: -- (Comentario) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 793649177d9e64bead7b8755f35bdb51f53f4dd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724978"
---
# <a name="---comment-entity-sql"></a>-- (Comentario) (Entity SQL)

Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios. Dos guiones (`--`) inician una línea de comentario.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Argumentos  

 `text_of_comment`  
 Cadena de caracteres que contiene el texto del comentario.  
  
## <a name="example"></a>Ejemplo  

 En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
