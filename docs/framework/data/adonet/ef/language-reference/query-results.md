---
title: Resultados de la consulta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
ms.openlocfilehash: 70aa2ad6385ec4791b05b202dc5dc6d4fe9e57b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797844"
---
# <a name="query-results"></a>Resultados de la consulta
Después de que una consulta de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] se convierta en árboles de comandos y se ejecute, los resultados de la consulta se devuelven normalmente como uno de los tipos siguientes:  
  
- Una colección con cero o más objetos entidad con tipo o una proyección de tipos complejos en el modelo conceptual.  
  
- Tipos CLR admitidos por el modelo conceptual.  
  
- Colecciones insertadas.  
  
- Tipos anónimos.  
  
 Cuando la consulta se ha ejecutado en el origen de datos, los resultados se materializan en tipos de CLR y se devuelven al cliente. [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] realiza la materialización de todos los objetos. Los errores derivados de la imposibilidad de realizar asignaciones entre [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] y CLR hará que se produzcan excepciones durante la materialización de los objetos.  
  
 Si la ejecución de la consulta devuelve tipos primitivos del modelo conceptual, los resultados están compuestos de tipos de CLR que son independientes y están desconectados de [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Sin embargo, si la consulta devuelve una colección de objetos entidad con tipo, representada por <xref:System.Data.Objects.ObjectQuery%601>, dichos tipos son sometidos a seguimiento por el contexto del objeto. Todos los comportamientos de objeto (por ejemplo, las colecciones de elementos primarios y secundarios, seguimiento de cambios, polimorfismo etc.) son como se define en el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Esta funcionalidad se puede utilizar en su capacidad, como se define en [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Para obtener más información, consulte [trabajar con objetos](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Los tipos struct devueltos en las consultas (como tipos anónimos y tipos complejos que aceptan valores NULL) pueden ser de valor `null`. Una propiedad de <xref:System.Data.Objects.DataClasses.EntityCollection%601> de una entidad devuelta también puede ser de valor `null`. Esto puede deberse a la proyección de la propiedad de colección de una entidad que es de valor `null`, como la llamada a <xref:System.Linq.Queryable.FirstOrDefault%2A> en una <xref:System.Data.Objects.ObjectQuery%601> que no tiene elementos.  
  
 En determinadas situaciones, puede que parezca que una consulta genera un resultado materializado durante su ejecución, pero la consulta se ejecutará en el servidor y el objeto entidad nunca se materializará en CLR. Esto puede producir problemas si se está dependiendo de los efectos secundarios de la materialización de los objetos.  
  
 El ejemplo siguiente contiene una clase personalizada, `MyContact`, con una propiedad `LastName`. Cuando se establece la propiedad `LastName`, se incrementa una variable `count`. Si ejecuta las dos consultas siguientes, la primera consulta incrementará `count` mientras que la segunda consulta no lo hará. Esto de debe a que en la segunda consulta la propiedad `LastName` se proyecta desde los resultados y nunca se crea la clase `MyContact`, porque no se requiere ejecutar la consulta en el almacén.  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
