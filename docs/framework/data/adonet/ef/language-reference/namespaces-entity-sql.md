---
title: Espacios de nombres (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7f05067c4bdb859f3661f775c2502852b6658522
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319561"
---
# <a name="namespaces-entity-sql"></a>Espacios de nombres (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduce espacios de nombres para evitar conflictos de nombres en los identificadores globales como los nombres de tipos, los conjuntos de entidades, las funciones, etcétera. La compatibilidad con el espacio de nombres en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es similar a la compatibilidad con el espacio de nombres en el .NET Framework.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona dos formas de cláusula USING: espacios de nombres completos, a los que se proporciona un alias más breve, y espacios no completos, según se ilustra en el ejemplo siguiente:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Reglas de la resolución de nombres  
 Si un identificador no se puede resolver en los ámbitos locales, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta localizar el nombre en los ámbitos globales (los espacios de nombres). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] primero intenta buscar la coincidencia del identificador (prefijo) con uno de los espacios de nombres completos. Si hay una coincidencia, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta resolver el resto del identificador en el espacio de nombres especificado. Si no se encuentra ninguna coincidencia, se inicia una excepción.  
  
 A continuación, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta buscar el identificador en todos los espacios de nombres no completos (especificados en el prólogo). Si el identificador se puede encontrar en un espacio de nombres exactamente, se devuelve esa ubicación. Si hay una coincidencia con ese identificador en más de un espacio de nombres, se inicia una excepción. Si no se puede identificar ningún espacio de nombres para el identificador, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] pasa el nombre al siguiente ámbito saliente (el objeto <xref:System.Data.Common.DbCommand> o <xref:System.Data.Common.DbConnection>), como se muestra en el ejemplo siguiente:  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Diferencias con .NET Framework  
 En el .NET Framework, puede usar espacios de nombres parcialmente calificados. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no permite esto.  
  
## <a name="adonet-usage"></a>Uso de ADO.NET  
 Las consultas se expresan a través de objetos <xref:System.Data.Common.DbCommand> de ADO.NET. Los objetos <xref:System.Data.Common.DbCommand> se pueden generar sobre los objetos <xref:System.Data.Common.DbConnection>. Los espacios de nombres también se pueden especificar como parte de los objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbConnection>. Si [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no puede resolver un identificador dentro de la propia consulta, se sondearán los espacios de nombres externos (según las reglas similares).  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
