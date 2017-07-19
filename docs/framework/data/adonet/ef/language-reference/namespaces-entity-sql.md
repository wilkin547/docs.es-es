---
title: "Espacios de nombres (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Espacios de nombres (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduce espacios de nombres para evitar conflictos de nombres en los identificadores globales como los nombres de tipos, los conjuntos de entidades, las funciones, etcétera.  La compatibilidad con los espacios de nombres de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es similar a la de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona dos formas de cláusula USING: espacios de nombres completos, a los que se proporciona un alias más breve, y espacios no completos, según se ilustra en el ejemplo siguiente:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## Reglas de la resolución de nombres  
 Si un identificador no se puede resolver en los ámbitos locales, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta localizar el nombre en los ámbitos globales \(los espacios de nombres\).  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] primero intenta buscar la coincidencia del identificador \(prefijo\) con uno de los espacios de nombres completos.  Si se encuentra una coincidencia, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta resolver el resto del identificador en el espacio de nombres especificado.  Si no se encuentra ninguna coincidencia, se inicia una excepción.  
  
 Después, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta buscar el identificador en todos los espacios de nombres no completos \(especificados en el prólogo\).  Si el identificador se puede encontrar en un espacio de nombres exactamente, se devuelve esa ubicación.  Si hay una coincidencia con ese identificador en más de un espacio de nombres, se inicia una excepción.  Si no se puede identificar ningún espacio de nombres para el identificador, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] pasa el nombre al siguiente ámbito exterior \(el objeto <xref:System.Data.Common.DbCommand> o <xref:System.Data.Common.DbConnection>\), según se ilustra en el ejemplo siguiente:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## Diferencias con .NET Framework  
 En [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], puede usar espacios de nombres parciales.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no permite esto.  
  
## Uso de ADO.NET  
 Las consultas se expresan a través de objetos <xref:System.Data.Common.DbCommand> de ADO.NET.  Los objetos <xref:System.Data.Common.DbCommand> se pueden generar sobre los objetos <xref:System.Data.Common.DbConnection>.  Los espacios de nombres también se pueden especificar como parte de los objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbConnection>.  Si [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no puede resolver un identificador dentro de la propia consulta, los espacios de nombres externos se sondean \(en función de reglas similares\).  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)