---
title: Funciones canónicas
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: fed6e45056e318ec0bf34951097304ef3c98f629
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760939"
---
# <a name="canonical-functions"></a>Funciones canónicas
Esta sección describe las funciones canónicas que son admitidas por todos los proveedores de datos y pueden ser utilizadas por todas las tecnologías de creación de consultas. Las funciones canónicas no pueden ser ampliadas por un proveedor.  
  
 Estas funciones canónicas se convertirán en la funcionalidad de origen de datos correspondiente para el proveedor. Esto permite que las llamadas a funciones se expresen de forma común en los orígenes de datos.  
  
 Dado que estas funciones canónicas son independientes de los orígenes de datos, los tipos de argumentos y valores devueltos de las funciones canónicas se definen en función de los tipos en el modelo conceptual. Sin embargo, puede que algunos orígenes de datos no admitan todos los tipos en el modelo conceptual.  
  
 Cuando las funciones canónicas se usan en una consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se llamará a la función apropiada en el origen de datos.  
  
 Todas las funciones canónicas tienen comportamiento de entrada NULL y condiciones de error especificadas explícitamente. Los proveedores de almacenamiento deben satisfacer ese comportamiento, pero [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] no lo exige.  
  
 En los escenarios LINQ, las consultas con el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] implican la asignación de métodos CLR a métodos en el origen de datos subyacente. Los métodos de CLR se asignan a funciones canónicas de modo que un conjunto específico de métodos se asignará correctamente, con independencia del origen de datos.  
  
## <a name="canonical-functions-namespace"></a>Espacio de nombres de funciones canónicas  
 El espacio de nombres para una función canónica es <xref:System.Data.Metadata.Edm>. El espacio de nombres <xref:System.Data.Metadata.Edm> se incluye automáticamente en todas las consultas. Sin embargo, si se importa otro espacio de nombres que contiene una función con el mismo nombre que una función canónica (en el espacio de nombres <xref:System.Data.Metadata.Edm>), se debe especificar el espacio de nombres.  
  
## <a name="in-this-section"></a>En esta sección  
 [Funciones canónicas de agregado](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 Describe las funciones canónicas de agregado de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funciones canónicas matemáticas](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 Describe las funciones canónicas matemáticas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funciones canónicas de cadena](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 Describe las funciones canónicas de cadena de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funciones canónicas de fecha y hora](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 Describe las funciones canónicas de fecha y hora de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funciones canónicas bit a bit](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 Describe las funciones canónicas bit a bit de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Funciones espaciales](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 Describe las funciones canónicas y espaciales de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Otras funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 Describe las funciones no clasificadas como funciones bit a bit, de fecha y hora, de cadena, matemáticas o de agregado.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Asignación entre las funciones canónicas del modelo conceptual y las funciones de SQL Server](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [Funciones definidas por el usuario](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
