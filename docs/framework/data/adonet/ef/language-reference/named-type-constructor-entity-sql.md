---
title: Constructor de tipos con nombre (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f95f0dcb92068675b2efff0af7e97b349976bf42
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329471"
---
# <a name="named-type-constructor-entity-sql"></a>Constructor de tipos con nombre (Entity SQL)
Se usa para crear instancias de los tipos nominales del modelo conceptual como los tipos de entidad o los tipos complejos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>Argumentos  
 `identifier`  
 Valor que es un identificador simple o incluido entre comillas. Para obtener más información, vea [identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 `expression`  
 Atributos del tipo que se suponen que conservan el mismo orden que cuando aparecen en la declaración del tipo.  
  
## <a name="return-value"></a>Valor devuelto  
 Instancias de tipos complejos con nombre y de tipos de entidad.  
  
## <a name="remarks"></a>Comentarios  
 En los ejemplos siguientes se muestra cómo crear tipos nominales y complejos:  
  
 La expresión siguiente crea una instancia de un tipo `Person` :  
  
 `Person("abc", 12)`  
  
 La expresión siguiente crea una instancia de un tipo complejo:  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 La expresión siguiente crea una instancia de un tipo complejo anidado:  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado:  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 El ejemplo siguiente muestra cómo inicializar una propiedad de un tipo complejo en null:`MyModel.ZipCode(‘98118’, null)`  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente usa el constructor de tipos con nombre para crear una instancia de un tipo del modelo conceptual. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a>Vea también

- [Tipos de constructores](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
