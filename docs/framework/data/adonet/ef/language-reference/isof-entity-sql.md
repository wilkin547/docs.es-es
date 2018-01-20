---
title: ISOF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 78bfcef336ad265b98069ed540f9156cf9cb65bd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="isof-entity-sql"></a>ISOF (Entity SQL)
Determina si el tipo de una expresión es del tipo especificado o uno de sus subtipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión de consulta válida de la que se va a determinar el tipo.  
  
 NOT  
 Niega el resultado EDM.Boolean de IS OF.  
  
 ONLY  
 Especifica que IS OF devuelve `true` solo si `expression` es de tipo `type` y no de uno cualquiera de sus subtipos.  
  
 `type`  
 Tipo con el que se va a probar `expression`. El tipo debe estar calificado por el espacio de nombres.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si `expression` es de tipo T y T es un tipo base o un tipo derivado de `type`; NULL si `expression` es nulo en tiempo de ejecución; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Las expresiones `expression IS NOT OF (type)` y `expression IS NOT OF (ONLY type)` son sintácticamente equivalentes a `NOT (expression IS OF (type))` y `NOT (expression IS OF (ONLY type))`, respectivamente.  
  
 En la tabla siguiente se muestra el comportamiento del operador `IS OF` en algunos patrones de esquina típicos. Todas las excepciones se producen en el cliente antes de que se llame al proveedor:  
  
|Modelo|Comportamiento|  
|-------------|--------------|  
|null IS OF (EntityType)|Produce|  
|null IS OF (ComplexType)|Produce|  
|null IS OF (RowType)|Produce|  
|TREAT (null AS EntityType) IS OF (EntityType)|Devuelve DBNull|  
|TREAT (null AS ComplexType) IS OF (ComplexType)|Produce|  
|TREAT (null AS RowType) IS OF (RowType)|Produce|  
|EntityType IS OF (EntityType)|Devuelve true o false|  
|ComplexType IS OF (ComplexType)|Produce|  
|RowType IS OF (RowType)|Produce|  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta utiliza el operador IS OF para determinar el tipo de una expresión de consulta y, a continuación, utiliza el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse. La consulta se basa en el [modelo School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
