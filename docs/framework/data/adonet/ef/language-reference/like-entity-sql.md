---
title: LIKE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8300e6d2-875b-481e-9ef4-e1e7c12d46fa
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 773547b097bad80e82350b473b6e59d0d84aa6dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="like-entity-sql"></a>LIKE (Entity SQL)
Determina si un elemento `String` de caracteres específico coincide con un patrón especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
match [NOT] LIKE pattern [ESCAPE escape]  
```  
  
## <a name="arguments"></a>Argumentos  
 `match`  
 Un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión que se evalúa como un `String`.  
  
 `pattern`  
 Patrón que va a coincidir con el elemento `String` especificado.  
  
 `escape`  
 Carácter de escape.  
  
 NOT  
 Especifica que el resultado de LIKE se niega.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si el elemento `string` coincide con el patrón; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]expresiones que utilizan el operador LIKE se evalúan en gran parte del mismo modo que las expresiones que utilizan la igualdad como criterios de filtrado. Sin embargo, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] las expresiones que utilizan el operador LIKE pueden incluir tanto literales como caracteres comodín.  
  
 En la tabla siguiente se describe la sintaxis del patrón `string`.  
  
|Carácter comodín|Descripción|Ejemplo|  
|------------------------|-----------------|-------------|  
|%|Cualquier elemento `string` de cero o más caracteres.|`title like '%computer%'`Busca todos los títulos con la palabra `"computer"` en cualquier lugar en el título.|  
|_ (carácter de subrayado)|Cualquier carácter individual.|`firstname like '_ean'`Busca todos los nombres de la primera de cuatro letras que finalizan con `"ean`, ", como Dean o Sean.|  
|[ ]|Cualquier carácter individual del intervalo ([a-f]) o del conjunto ([abcdef]) que se han especificado.|`lastname like '[C-P]arsen'`busca apellidos que terminan con "arsen" y empiezan con cualquier carácter individual entre C y P, como Carsen o Larsen.|  
|[^]|Cualquier carácter individual no incluido en el intervalo ([^a-f]) o del conjunto ([^abcdef]) que se han especificado.|`lastname like 'de[^l]%'`Busca todos los apellidos que empiezan con "de" y no incluyen "l" como letra siguiente.|  
  
> [!NOTE]
>  El operador LIKE y la cláusula ESCAPE de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no se pueden aplicar a los valores `System.DateTime` o `System.Guid`.  
  
 LIKE admite operaciones de búsqueda de coincidencias de patrón ASCII y Unicode. Cuando todos los parámetros son caracteres ASCII, se realiza la operación de búsqueda de coincidencias de patrón ASCII. Si uno o más argumentos son Unicode, todos los argumentos se convierten a Unicode y se realiza la operación de búsqueda de coincidencias de patrón Unicode. Cuando se utiliza Unicode con LIKE, los espacios en blanco al final son significativos; sin embargo, no lo son para los datos que no son Unicode. La sintaxis de cadena de patrón de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es el mismo que el de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  
  
 Un patrón puede contener caracteres normales y caracteres comodín. Durante la operación de búsqueda de coincidencias de patrón, los caracteres normales deben coincidir exactamente con los caracteres especificados en el elemento `string` de caracteres. Sin embargo, los caracteres comodín pueden coincidir con fragmentos arbitrarios de la cadena de caracteres. Cuando se utiliza con caracteres comodín, el operador LIKE es más flexible que los operadores de comparación de cadenas = y !=.  
  
> [!NOTE]
>  Puede utilizar extensiones específicas del proveedor si el destino es un proveedor concreto. Sin embargo, otros proveedores pueden tratar de manera diferente este tipo de estructuras. SqlServer admite patrones [primero-último] y [^primero-último] donde el primero coincide exactamente con un carácter entre el primero y el último, y el segundo coincide exactamente con un carácter que no está entre el primero y el último.  
  
### <a name="escape"></a>Escape  
 El uso de la cláusula ESCAPE permite buscar cadenas de caracteres que incluyen uno o más de los caracteres comodín especiales que se describen en la tabla de la sección anterior. Por ejemplo, suponga que varios documentos incluyen el literal "100%" en el título y desea buscar todos esos documentos. Dado que el carácter de porcentaje (%) es un carácter comodín, debe evitarlo utilizando la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cláusula de ESCAPE para ejecutar correctamente la búsqueda. A continuación se muestra un ejemplo de este filtro.  
  
```  
"title like '%100!%%' escape '!'"  
```  
  
 En esta expresión de búsqueda, el carácter comodín de porcentaje (%) situado inmediatamente después del carácter de exclamación (!) se trata como literal, en lugar de como carácter comodín. Puede utilizar cualquier carácter como carácter de escape salvo los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] caracteres comodín y el cuadrado corchete de cierre (`[ ]`) caracteres. En el ejemplo anterior, el carácter de exclamación (!) es el carácter de escape.  
  
## <a name="example"></a>Ejemplo  
 Las dos siguientes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] las consultas utilizan el tipo y operadores ESCAPE para determinar si una cadena de caracteres específica coincide con un patrón especificado. La primera consulta busca el `Name` que empieza con los caracteres `Down_`. Esta consulta utiliza la opción ESCAPE porque el carácter de subrayado (`_`) es un carácter comodín. Sin especificar la opción ESCAPE, la consulta buscaría valores de `Name` que empezasen con la palabra `Down` seguida de cualquier carácter individual diferente del carácter de subrayado. Las consultas se basan en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#LIKE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#like)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
