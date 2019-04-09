---
title: Semántica de comparación (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083340"
---
# <a name="comparison-semantics-entity-sql"></a>Semántica de comparación (Entity SQL)
El uso de cualquiera de los operadores de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguientes implica la comparación de las instancias de tipo:  
  
## <a name="explicit-comparison"></a>Comparación explícita  
 Operaciones de igualdad:  
  
-   =  
  
-   !=  
  
 Operaciones de ordenación:  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 Operaciones de nulabilidad:  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## <a name="explicit-distinction"></a>Distinción explícita  
 Distinción de igualdad:  
  
-   DISTINCT  
  
-   GROUP BY  
  
 Distinción de ordenación:  
  
-   ORDER BY  
  
## <a name="implicit-distinction"></a>Distinción implícita  
 Operaciones y predicados de conjuntos (igualdad):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 Predicados de elementos (igualdad):  
  
-   IN  
  
## <a name="supported-combinations"></a>Combinaciones admitidas  
 En la tabla siguiente se muestran todas las combinaciones admitidas de los operadores de comparación para cada clase de tipo:  
  
|**Tipo**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**IS NULL**<br /><br /> **IS NOT NULL**|  
|-|-|-|-|-|-|-|-|  
|Tipo de entidad|Ref<sup>1</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Todas las propiedades<sup>2</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Ref<sup>1</sup>|  
|Tipo complejo|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|  
|Fila|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Todas las propiedades<sup>4</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Todas las propiedades<sup>4</sup>|Producir<sup>3</sup>|  
|Tipo primitivo|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|Depende del proveedor|  
|Conjunto múltiple|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|  
|Ref|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Sí<sup>5</sup>|Throw|Throw|Sí<sup>5</sup>|  
|Asociación<br /><br /> type|Producir<sup>3</sup>|Throw|Throw|Throw|Producir<sup>3</sup>|Producir<sup>3</sup>|Producir<sup>3</sup>|  
  
 <sup>1</sup>las referencias de las instancias del tipo de entidad dado se comparan implícitamente, como se muestra en el ejemplo siguiente:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Una instancia de entidad no se puede comparar con una referencia explícita. Si se intenta, se inicia una excepción. Por ejemplo, la siguiente consulta iniciaría una excepción:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>propiedades de tipos complejos se simplifican antes de que se envían a la tienda, por lo que lleguen a ser comparables (siempre que todas sus propiedades sean comparables). Consulte también <sup>4.</sup>  
  
 <sup>3</sup>en tiempo de ejecución de Entity Framework detecta un caso no admitido y se inicia una excepción significativa sin activar el proveedor o almacén.  
  
 <sup>4</sup>se realiza un intento para comparar todas las propiedades. Si hay una propiedad que es de un tipo no comparable, como text, ntext o image, se podría iniciar una excepción de servidor.  
  
 <sup>5</sup>se comparan todos los elementos individuales de las referencias (Esto incluye el nombre del conjunto de entidades y todas las propiedades claves del tipo de entidad).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
