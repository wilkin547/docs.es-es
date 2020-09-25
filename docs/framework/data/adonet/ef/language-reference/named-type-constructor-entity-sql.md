---
title: Constructor de tipos con nombre (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: c673b58ee5811e3d3b74b3744d3f5291888e2253
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197786"
---
# <a name="named-type-constructor-entity-sql"></a>Constructor de tipos con nombre (Entity SQL)

Se usa para crear instancias de los tipos nominales del modelo conceptual como los tipos de entidad o los tipos complejos.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>Argumentos  

 `identifier`  
 Valor que es un identificador simple o incluido entre comillas. Para obtener más información, vea [identificadores](identifiers-entity-sql.md)  
  
 `expression`  
 Atributos del tipo que se suponen que conservan el mismo orden que cuando aparecen en la declaración del tipo.  
  
## <a name="return-value"></a>Valor devuelto  

 Instancias de tipos complejos con nombre y de tipos de entidad.  
  
## <a name="remarks"></a>Observaciones  

 En los ejemplos siguientes se muestra cómo crear tipos nominales y complejos:  
  
 La expresión siguiente crea una instancia de un tipo `Person` :  
  
 `Person("abc", 12)`  
  
 La expresión siguiente crea una instancia de un tipo complejo:  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 La expresión siguiente crea una instancia de un tipo complejo anidado:  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado:  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 En el ejemplo siguiente se muestra cómo inicializar una propiedad de un tipo complejo en NULL:`MyModel.ZipCode(‘98118’, null)`  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente usa el constructor de tipos con nombre para crear una instancia de un tipo del modelo conceptual. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a>Consulte también

- [Tipos de constructores](constructing-types-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
