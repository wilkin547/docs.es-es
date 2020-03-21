---
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150459"
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
  
|**Tipo**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **Distintas**|**Unión**<br /><br /> **Intersect**<br /><br /> **Excepto**<br /><br /> **Establecer**<br /><br /> **OVERLAPS**|**En**|**< <**<br /><br /> **> >**|**PEDIDO POR**|**ES NULO**<br /><br /> **NO ES NULO**|  
|-|-|-|-|-|-|-|-|  
|Tipo de entidad|Ref<sup>1</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Ref<sup>1</sup>|  
|Tipo complejo|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|  
|Row|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Todas las propiedades<sup>4</sup>|Lanzar<sup>3</sup>|  
|Tipo primitivo|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|  
|Conjunto múltiple|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|  
|Ref|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Throw|Throw|Sí<sup>5</sup>|  
|Asociación<br /><br /> type|Lanzar<sup>3</sup>|Throw|Throw|Throw|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|Lanzar<sup>3</sup>|  
  
 <sup>1</sup> Las referencias de las instancias de tipo de entidad especificadas se comparan implícitamente, como se muestra en el ejemplo siguiente:  
  
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
  
 <sup>2</sup> Las propiedades de tipos complejos se aplanan antes de enviarse a la tienda, por lo que se vuelven comparables (siempre y cuando todas sus propiedades sean comparables). Consulte también <sup>4.</sup>  
  
 <sup>3</sup> El tiempo de ejecución de Entity Framework detecta el caso no admitido y produce una excepción significativa sin involucrar al proveedor o almacén.  
  
 <sup>4</sup> Se intenta comparar todas las propiedades. Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.  
  
 <sup>5</sup> Se comparan todos los elementos individuales de las referencias (esto incluye el nombre del conjunto de entidades y todas las propiedades de clave del tipo de entidad).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre Entity SQL](entity-sql-overview.md)
