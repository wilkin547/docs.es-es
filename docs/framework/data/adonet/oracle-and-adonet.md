---
title: Oracle y ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f77d5c98c96bd4b6085c30b6d1dd713bd324fbad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="oracle-and-adonet"></a>Oracle y ADO.NET
> [!NOTE]
>  Los tipos de <xref:System.Data.OracleClient> están desusados. Los tipos seguirán estando admitidos en la versión actual de .NET Framework, pero se quitarán en una versión posterior. Microsoft recomienda usar un proveedor de Oracle de otro fabricante.  
  
 En esta sección se describen características y comportamientos específicos del proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para Oracle.  
  
 El proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para Oracle proporciona acceso a bases de datos Oracle mediante la Interfaz de llamada de Oracle (OCI) que se suministra con el software Oracle Client. La funcionalidad del proveedor de datos se ha diseñado para que sea similar a la de los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], OLE DB y ODBC.  
  
 Para utilizar el proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para Oracle, la aplicación debe hacer referencia al espacio de nombres <xref:System.Data.OracleClient> de la manera siguiente:  
  
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
 Describe los requisitos para utilizar el proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para Oracle, así como una serie de aspectos que se deben tener en cuenta al utilizarlo.  
  
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
 Describe algunas recomendaciones de codificación segura para utilizar [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
 [Objetos DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Describe cómo crear y usar `DataSets`, `DataSets` con establecimiento de tipos, `DataTables` y `DataViews`.  
  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Describe cómo trabajar con datos XML en ADO.NET.  
  
 [SQL Server y ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Describe cómo trabajar con características y funcionalidad específicas de [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].  
  
 [Objetos DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Describe clases genéricas que permiten escribir código independiente del proveedor en [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
