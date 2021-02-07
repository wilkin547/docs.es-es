---
description: 'Más información acerca de: SqlClient para el Entity Framework'
title: SqlClient para Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: eba5602c13f66d1ee4404bbc27035304e34c1cd0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673133"
---
# <a name="sqlclient-for-the-entity-framework"></a>SqlClient para Entity Framework

En esta sección se describe el Proveedor de datos de .NET Framework para SQL Server (SqlClient), el cual permite a Entity Framework trabajar sobre Microsoft SQL Server.  
  
## <a name="provider-schema-attribute"></a>Atributo Provider de Schema  

 `Provider` es un atributo del elemento `Schema` del lenguaje de definición de esquemas de almacenamiento (SSDL).  
  
 Para utilizar SqlClient, asigne la cadena "System.Data.SqlClient" al atributo `Provider` del elemento `Schema`.  
  
## <a name="providermanifesttoken-schema-attribute"></a>Atributo ProviderManifestToken de Schema  

 `ProviderManifestToken` es un atributo necesario del elemento `Schema` en SSDL. Este token se utiliza para cargar el manifiesto del proveedor en escenarios sin conexión. Para obtener más información sobre el `ProviderManifestToken` atributo, vea [Schema (elemento) (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).  
  
 SqlClient se puede usar como proveedor de datos para diferentes versiones de SQL Server. Estas versiones tienen capacidades distintas. Por ejemplo, SQL Server 2000 no admite los `varchar(max)` `nvarchar(max)` tipos y que se introdujeron con SQL Server 2005.  
  
 SqlCliente genera y acepta los tokens del manifiesto del proveedor siguientes para las diferentes versiones de SQL Server.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
> A partir de Visual Studio 2010, las [herramientas de Entity Data Model de ADO.net](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) no admiten SQL Server 2000.  
  
## <a name="provider-namespace-name"></a>Nombre del espacio de nombres de proveedor  

 Todos los proveedores deben especificar un espacio de nombres. Esta propiedad indica a Entity Framework qué prefijo usa el proveedor para estructuras concretas, como los tipos y funciones. El espacio de nombres para los manifiestos del proveedor SqlClient es `SqlServer`. Para obtener más información sobre los espacios de nombres, vea [espacios de nombres](./language-reference/namespaces-entity-sql.md).  
  
## <a name="types"></a>Tipos  

 El proveedor SqlCliente para Entity Framework proporciona información de asignación entre los tipos del modelo conceptual y los tipos de SQL Server. Para obtener más información, vea [SqlClient para Entity Framework](sqlclient-for-ef-types.md).  
  
## <a name="functions"></a>Functions  

 El proveedor de SqlClient para Entity Framework define la lista de funciones admitidas por el proveedor. Para obtener una lista de las funciones admitidas, vea [SqlClient para funciones de Entity Framework](sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [SqlClient para las funciones de Entity Framework](sqlclient-for-ef-functions.md)  
  
 [SqlClient para tipos de Entity Framework](sqlclient-for-ef-types.md)  
  
 [Problemas conocidos en SqlClient para Entity Framework](known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Vea también

- [Lenguaje Entity SQL](./language-reference/entity-sql-language.md)
- [Referencia del lenguaje](./language-reference/index.md)
- [Problemas conocidos del proveedor SqlClient para Entity Framework](sqlclient-for-the-entity-framework.md)
