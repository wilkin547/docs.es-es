---
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 9a36fcc4476c25d64fed670e857f339fb20043d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197838"
---
# <a name="comparison-semantics-entity-sql"></a>Semántica de comparación (Entity SQL)

El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:  
  
## <a name="explicit-comparison"></a>Comparación explícita  

 Operaciones de igualdad:  
  
- =  
  
- !=  
  
 Operaciones de ordenación:  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 Operaciones de nulabilidad:  
  
- IS NULL  
  
- IS NOT NULL  
  
## <a name="explicit-distinction"></a>Distinción explícita  

 Distinción de igualdad:  
  
- DISTINCT  
  
- GROUP BY  
  
 Distinción de ordenación:  
  
- ORDER BY  
  
## <a name="implicit-distinction"></a>Distinción implícita  

 Operaciones y predicados de conjuntos (igualdad):  
  
- UNION  
  
- INTERSECT  
  
- EXCEPT  
  
- SET  
  
- OVERLAPS  
  
 Predicados de elementos (igualdad):  
  
- IN  
  
## <a name="supported-combinations"></a>Combinaciones admitidas  

 En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:  
  
|**Tipo**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**IS NULL**<br /><br /> **NO ES NULL**|  
|-|-|-|-|-|-|-|-|  
|Tipo de entidad|Referencia<sup>1</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Referencia<sup>1</sup>|  
|Tipo complejo|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|  
|Row|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Todas las propiedades<sup>4</sup>|Iniciar<sup>3</sup>|  
|Tipo primitivo|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|  
|Conjunto múltiple|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|  
|Ref|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Throw|Throw|Sí<sup>5</sup>|  
|Asociación<br /><br /> type|Iniciar<sup>3</sup>|Throw|Throw|Throw|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|Iniciar<sup>3</sup>|  
  
 <sup>1</sup> Las referencias de las instancias de tipo de entidad dadas se comparan implícitamente, como se muestra en el ejemplo siguiente:  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Una instancia de entidad no se puede comparar con una referencia explícita. Si se intenta, se inicia una excepción. Por ejemplo, la siguiente consulta iniciaría una excepción:  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup> Las propiedades de los tipos complejos se alisan antes de enviarse al almacén, por lo que son comparables (siempre y cuando todas sus propiedades sean comparables). Vea también <sup>4.</sup>  
  
 <sup>3</sup> El entorno de tiempo de ejecución de Entity Framework detecta el caso no compatible y produce una excepción significativa sin tener que atraer al proveedor o almacén.  
  
 <sup>4</sup> Se ha intentado comparar todas las propiedades. Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.  
  
 <sup>5</sup> Se comparan todos los elementos individuales de las referencias (esto incluye el nombre del conjunto de entidades y todas las propiedades clave del tipo de entidad).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre Entity SQL](entity-sql-overview.md)
