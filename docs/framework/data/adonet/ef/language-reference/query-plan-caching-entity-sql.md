---
description: 'Más información acerca de: almacenamiento en caché del plan de consulta (Entity SQL)'
title: Almacenamiento en caché del plan de consulta [Entity SQL]
ms.date: 03/30/2017
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
ms.openlocfilehash: eee8e3afcd6f97b7e6021389d59a8ce03507fb9f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802104"
---
# <a name="query-plan-caching-entity-sql"></a>Almacenamiento en caché del plan de consulta [Entity SQL]

Siempre que se intenta ejecutar una consulta, la canalización de la consulta examina la memoria caché del plan de consulta para comprobar si la citada consulta ya está compilada y disponible. En ese caso, vuelve a utilizar el plan almacenado en caché en lugar de compilar uno nuevo. Si no se encuentra ninguna coincidencia en la memoria caché del plan de consulta, la consulta se compila y se almacena en memoria caché. Las consultas se identifican mediante su colección de parámetros (nombres y tipos) y texto de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Todas las comparaciones de texto distinguen mayúsculas de minúsculas.  
  
## <a name="configuration"></a>Configuración  

 El almacenamiento en caché del plan de consulta se puede configurar a través del comando <xref:System.Data.EntityClient.EntityCommand>.  
  
 Para habilitar o deshabilitar el almacenamiento en caché del plan de consulta a través de la propiedad <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, establezca esta propiedad en `true` o `false`, respectivamente. Si se deshabilita el almacenamiento en caché del plan en consultas dinámicas individuales que no es probable que se usen más de una vez, mejora el rendimiento.  
  
 Puede habilitar el almacenamiento en caché del plan de consultas a través de <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.  
  
## <a name="recommended-practice"></a>Práctica recomendada  

 En general, se deben evitar las consultas dinámicas. El ejemplo de consulta dinámica siguiente es vulnerable a los ataques de inyección de SQL, porque toma directamente los datos proporcionados por el usuario sin efectuar ninguna validación.  
  
 ```csharp
 var query = "SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;  
 ```

 Si utiliza las consultas generadas dinámicamente, considere deshabilitar el almacenamiento en memoria caché del plan de consultas para evitar el consumo de memoria innecesario para las entradas de la memoria caché que no es probable que se vuelvan a usar.  
  
 El almacenamiento en caché del plan de consulta en consultas estáticas y parametrizadas puede proporcionar mejoras en el rendimiento. A continuación se muestra un ejemplo de consulta estática:  
  
```csharp
var query = "SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 Para que se encuentre una coincidencia apropiada de las consultas en la memoria caché del plan de consulta, estas deben cumplir los requisitos siguientes:  
  
- El texto de la consulta debe ser un patrón constante, preferentemente una cadena o un recurso constante.  
  
- Se debe utilizar <xref:System.Data.EntityClient.EntityParameter> o <xref:System.Data.Objects.ObjectParameter> siempre que se deba pasar un valor proporcionado por el usuario.  
  
 Se deben evitar los patrones de consulta siguientes, que consumen innecesariamente espacios en la memoria caché del plan de consulta:  
  
- Cambios en las mayúsculas o minúsculas del texto.  
  
- Cambios en los espacios en blanco.  
  
- Cambios en los valores literales.  
  
- Cambios en el texto incluido en los comentarios.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre Entity SQL](entity-sql-overview.md)
