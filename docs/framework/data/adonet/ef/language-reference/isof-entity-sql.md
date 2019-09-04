---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 3b746a82f72fc7f42f9d91ddd0a7d6f4f86ac0bb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250573"
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
 Las expresiones `expression IS NOT OF (type)` y `expression IS NOT OF (ONLY type)` son sintácticamente equivalentes `NOT (expression IS OF (ONLY type))`a `NOT (expression IS OF (type))` y, respectivamente.  
  
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
 La consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] de siguiente usa el operador is of para determinar el tipo de una expresión de consulta y, a continuación, usa el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse. La consulta se basa en el [modelo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
