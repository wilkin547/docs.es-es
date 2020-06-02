---
title: Oracle y ADO.NET
description: Obtenga información sobre las características y los comportamientos del proveedor de datos de .NET Framework para Oracle, que proporciona acceso a una base de datos de Oracle mediante la interfaz de llamada de Oracle.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 8757352a7444fad802ea88ba58e0fe643c86cbb8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286694"
---
# <a name="oracle-and-adonet"></a>Oracle y ADO.NET
> [!NOTE]
> Los tipos de <xref:System.Data.OracleClient> están en desuso. Los tipos seguirán estando admitidos en la versión actual de .NET Framework, pero se quitarán en una versión posterior. Microsoft recomienda usar un proveedor de Oracle de otro fabricante.  
  
 En esta sección se describen características y comportamientos específicos del proveedor de datos de .NET Framework para Oracle.  
  
 El proveedor de datos de .NET Framework para Oracle proporciona acceso a una base de datos de Oracle mediante Oracle Call Interface (OCI), tal y como lo proporciona el software cliente de Oracle. La funcionalidad del proveedor de datos está diseñada para ser similar a la de los .NET Framework proveedores de datos para SQL Server, OLE DB y ODBC.  
  
 Para utilizar el proveedor de datos de .NET Framework para Oracle, una aplicación debe hacer referencia al espacio de nombres de la <xref:System.Data.OracleClient> siguiente manera:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 También debe incluir una referencia a la DLL cuando compile el código. Por ejemplo, si compila un programa C#, la línea de comandos debe incluir:  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>En esta sección  
 [Requisitos del sistema](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Describe los requisitos para usar el proveedor de datos de .NET Framework para Oracle y describe una serie de problemas que se deben tener en cuenta al utilizarlos.  
  
 [Objetos BFILE de Oracle](oracle-bfiles.md)  
 Describe la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos BFILE de Oracle.  
  
 [Objetos LOB de Oracle](oracle-lobs.md)  
 Describe la clase <xref:System.Data.OracleClient.OracleLob>, que se utiliza para trabajar con tipos de datos LOB de Oracle.  
  
 [Parámetros REF CURSOR de Oracle](oracle-ref-cursors.md)  
 Describe la compatibilidad con el tipo de datos REF CURSOR de Oracle.  
  
 [Tipos de Oracle](oracletypes.md)  
 Describe las estructuras que puede utilizar para trabajar con tipos de datos de Oracle, como <xref:System.Data.OracleClient.OracleNumber> y <xref:System.Data.OracleClient.OracleString>.  
  
 [Secuencias de Oracle](oracle-sequences.md)  
 Describe la compatibilidad para recuperar los valores de clave de secuencia de Oracle que genera el servidor.  
  
 [Asignaciones de tipos de datos de Oracle](oracle-data-type-mappings.md)  
 Enumera los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.  
  
 [Transacciones distribuidas de Oracle](oracle-distributed-transactions.md)  
 Describe cómo se inscribe automáticamente el objeto <xref:System.Data.OracleClient.OracleConnection> en una transacción distribuida si se determina que hay una transacción activa.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Proteger aplicaciones de ADO.NET](securing-ado-net-applications.md)  
 Describe algunas recomendaciones de codificación segura para utilizar ADO.NET.  
  
 [Objetos DataSet, DataTable y DataView](./dataset-datatable-dataview/index.md)  
 Describe cómo crear y usar `DataSets`, `DataSets` con establecimiento de tipos, `DataTables` y `DataViews`.  
  
 [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)  
 Describe cómo trabajar con datos XML en ADO.NET.  
  
 [SQL Server y ADO.NET](./sql/index.md)  
 Describe cómo trabajar con las características y la funcionalidad específicas de SQL Server.  
  
 [Objetos DbProviderFactory](dbproviderfactories.md)  
 Describe clases genéricas que permiten escribir código independiente del proveedor en ADO.NET.  
  
## <a name="see-also"></a>Consulte también

- [ADO.NET](index.md)
- [Información general de ADO.NET](ado-net-overview.md)
