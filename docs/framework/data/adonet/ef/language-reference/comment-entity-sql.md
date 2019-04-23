---
title: -- (Comentario) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339520"
---
# <a name="---comment-entity-sql"></a>-- (Comentario) (Entity SQL)
Las consultas de[!INCLUDE[esql](../../../../../../includes/esql-md.md)] pueden contener comentarios. Dos guiones (`--`) inician una línea de comentario.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Argumentos  
 `text_of_comment`  
 Cadena de caracteres que contiene el texto del comentario.  
  
## <a name="example"></a>Ejemplo  
 En la siguiente consulta de Entity SQL se muestra cómo usar los comentarios. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
