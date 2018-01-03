---
title: SqlClient para Entity Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 590df03857805c43b6e9a60c030cadcad3501d3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-for-the-entity-framework"></a>SqlClient para Entity Framework
En esta sección se describe el Proveedor de datos de .NET Framework para SQL Server (SqlClient), el cual permite a Entity Framework trabajar sobre Microsoft SQL Server.  
  
## <a name="provider-schema-attribute"></a>Atributo Provider de Schema  
 `Provider` es un atributo del elemento `Schema` del lenguaje de definición de esquemas de almacenamiento (SSDL).  
  
 Para utilizar SqlClient, asigne la cadena "System.Data.SqlClient" al atributo `Provider` del elemento `Schema`.  
  
## <a name="providermanifesttoken-schema-attribute"></a>Atributo ProviderManifestToken de Schema  
 `ProviderManifestToken` es un atributo necesario del elemento `Schema` en SSDL. Este token se utiliza para cargar el manifiesto del proveedor en escenarios sin conexión. Para obtener más información acerca de `ProviderManifestToken` de atributo, vea [elemento de esquema de almacenamiento (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222).  
  
 SqlClient se puede utilizar como proveedor de datos para diferentes versiones de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Estas versiones tienen capacidades distintas. Por ejemplo, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] no admite los tipos `varchar(max)` y `nvarchar(max)` que se incluyeron con [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].  
  
 SqlCliente genera y acepta los tokens del manifiesto del proveedor siguientes para las diferentes versiones de SQL Server.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  A partir de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, la [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) no son compatibles con SQL Server 2000.  
  
## <a name="provider-namespace-name"></a>Nombre del espacio de nombres de proveedor  
 Todos los proveedores deben especificar un espacio de nombres. Esta propiedad indica a Entity Framework qué prefijo usa el proveedor para estructuras concretas, como los tipos y funciones. El espacio de nombres para los manifiestos del proveedor SqlClient es `SqlServer`. Para obtener más información acerca de los espacios de nombres, vea [espacios de nombres](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).  
  
## <a name="types"></a>Tipos  
 El proveedor SqlCliente para Entity Framework proporciona información de asignación entre los tipos del modelo conceptual y los tipos de SQL Server. Para obtener más información, consulte [SqlClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
## <a name="functions"></a>Funciones  
 El proveedor de SqlClient para Entity Framework define la lista de funciones admitidas por el proveedor. Para obtener una lista de las funciones admitidas, consulte [SqlClient para Entity Framework funciones](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [SqlClient para las funciones de Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [SqlClient para tipos de Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [Problemas conocidos en SqlClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Vea también  
 [Lenguaje Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [Referencia del lenguaje](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [Problemas conocidos de proveedor de SqlClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
