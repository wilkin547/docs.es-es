---
title: Oracle y ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 012a5b55d052f5f06da5c152da79f4676b2bff4e
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877946"
---
# <a name="oracle-and-adonet"></a>Oracle y ADO.NET
> [!NOTE]
>  Los tipos de <xref:System.Data.OracleClient> están en desuso. Los tipos seguirán estando admitidos en la versión actual de .NET Framework, pero se quitarán en una versión posterior. Microsoft recomienda usar un proveedor de Oracle de otro fabricante.  
  
 Esta sección describen las características y comportamientos que son específicos del proveedor de datos de .NET Framework para Oracle.  
  
 El proveedor de datos de .NET Framework para Oracle proporciona acceso a una base de datos de Oracle mediante Oracle Call Interface (OCI) proporcionados por el software cliente de Oracle. La funcionalidad del proveedor de datos está diseñada para ser similar de los proveedores de datos .NET Framework para SQL Server, OLE DB y ODBC.  
  
 Para usar el proveedor de datos de .NET Framework para Oracle, debe hacer referencia a una aplicación la <xref:System.Data.OracleClient> espacio de nombres como sigue:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 También debe incluir una referencia a la DLL cuando compile el código. Por ejemplo, si compila un programa C#, la línea de comandos debe incluir:  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>En esta sección  
 [Requisitos del sistema](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Describe los requisitos para usar el proveedor de datos de .NET Framework para Oracle y una serie de problemas a tener en cuenta cuando se usa.  
  
 [Objetos BFILE de Oracle](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 Describe la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos BFILE de Oracle.  
  
 [Objetos LOB de Oracle](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 Describe la clase <xref:System.Data.OracleClient.OracleLob>, que se utiliza para trabajar con tipos de datos LOB de Oracle.  
  
 [Parámetros REF CURSOR de Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 Describe la compatibilidad con el tipo de datos REF CURSOR de Oracle.  
  
 [Tipos de Oracle](../../../../docs/framework/data/adonet/oracletypes.md)  
 Describe las estructuras que puede utilizar para trabajar con tipos de datos de Oracle, como <xref:System.Data.OracleClient.OracleNumber> y <xref:System.Data.OracleClient.OracleString>.  
  
 [Secuencias de Oracle](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 Describe la compatibilidad para recuperar los valores de clave de secuencia de Oracle que genera el servidor.  
  
 [Asignaciones de tipos de datos de Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Enumera los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.  
  
 [Transacciones distribuidas de Oracle](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 Describe cómo se inscribe automáticamente el objeto <xref:System.Data.OracleClient.OracleConnection> en una transacción distribuida si se determina que hay una transacción activa.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Proteger aplicaciones de ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Describe algunas recomendaciones de codificación segura para utilizar ADO.NET.  
  
 [Objetos DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Describe cómo crear y usar `DataSets`, `DataSets` con establecimiento de tipos, `DataTables` y `DataViews`.  
  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Describe cómo trabajar con datos XML en ADO.NET.  
  
 [SQL Server y ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Describe cómo trabajar con las características y la funcionalidad específicas de SQL Server.  
  
 [Objetos DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Describe clases genéricas que permiten escribir código independiente del proveedor en ADO.NET.  
  
## <a name="see-also"></a>Vea también

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
