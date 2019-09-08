---
title: Comandos y parámetros
ms.date: 03/30/2017
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
ms.openlocfilehash: 1d0c3adb56e5ff44b5c5e065ac040f25584a1946
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784957"
---
# <a name="commands-and-parameters"></a>Comandos y parámetros
Una vez establecida una conexión a un origen de datos, puede ejecutar comandos y devolver resultados desde el mismo mediante un objeto <xref:System.Data.Common.DbCommand>. Para crear un comando, puede utilizar uno de los constructores de comando del proveedor de datos .NET Framework con el que esté trabajando. Los constructores pueden aceptar argumentos opcionales, como una instrucción SQL para ejecutar en el origen de datos, un objeto <xref:System.Data.Common.DbConnection> o un objeto <xref:System.Data.Common.DbTransaction>. También puede configurar dichos objetos como propiedades del comando. También puede crear un comando para una determinada conexión mediante el método <xref:System.Data.Common.DbConnection.CreateCommand%2A> de un objeto `DbConnection`. La instrucción SQL que ejecuta el comando se puede configurar mediante la propiedad <xref:System.Data.Common.DbCommand.CommandText%2A>.  
  
 Cada proveedor de datos .NET Framework incluido en .NET Framework cuenta con un objeto `Command`: El proveedor de datos .NET Framework para OLE DB incluye un objeto <xref:System.Data.OleDb.OleDbCommand>, el proveedor de datos .NET Framework para SQL Server incluye un objeto <xref:System.Data.SqlClient.SqlCommand>, el proveedor de datos .NET Framework para ODBC incluye un objeto <xref:System.Data.Odbc.OdbcCommand> y el proveedor de datos .NET Framework para Oracle incluye un objeto <xref:System.Data.OracleClient.OracleCommand>.  
  
## <a name="in-this-section"></a>En esta sección  
 [Ejecución de un comando](executing-a-command.md)  
 Describe el objeto `Command` de ADO.NET, así como la forma de utilizarlo para ejecutar consultas y comandos con respecto a un origen de datos.  
  
 [Configuración de parámetros y tipos de datos de parámetros](configuring-parameters-and-parameter-data-types.md)  
 Describe el trabajo con parámetros `Command`, incluidos dirección, tipo de datos y sintaxis de parámetros.  
  
 [Generación de comandos con objetos CommandBuilder](generating-commands-with-commandbuilders.md)  
 Describe cómo utilizar generadores de comandos para generar automáticamente comandos INSERT, UPDATE y DELETE para un `DataAdapter` que tiene un comando SELECT de tabla única.  
  
 [Obtención de un valor único de una base de datos](obtaining-a-single-value-from-a-database.md)  
 Describe cómo utilizar el método `ExecuteScalar` de un objeto `Command` para devolver un único valor desde una consulta de base de datos.  
  
 [Uso de comandos para modificar datos](using-commands-to-modify-data.md)  
 Describe cómo se utiliza un proveedor de datos para ejecutar procedimientos almacenados o instrucciones de lenguaje de definición de datos (DDL).  
  
## <a name="see-also"></a>Vea también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Objetos DataSet, DataTable y DataView](./dataset-datatable-dataview/index.md)
- [Conexión a un origen de datos](connecting-to-a-data-source.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
