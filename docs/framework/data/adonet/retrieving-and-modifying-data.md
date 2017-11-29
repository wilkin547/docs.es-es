---
title: Recuperar y modificar datos en ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 35de20b1cb35fdcd87a653f1ac202c01d345c317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Recuperar y modificar datos en ADO.NET
La principal función de cualquier aplicación de base de datos es conectarse a un origen de datos y recuperar los datos que contiene. Los proveedores de datos de .NET Framework de ADO.NET sirven como puente entre una aplicación y un origen de datos, lo que le permite ejecutar comandos y recuperar datos mediante un **DataReader** o un **DataAdapter** . Una función clave de cualquier aplicación de base de datos es la capacidad de actualizar los datos almacenados en la misma. En ADO.NET, actualización de datos implica el uso de la **DataAdapter** y <xref:System.Data.DataSet>, y **comando** objetos; y también pueden implicar mediante transacciones.  
  
## <a name="in-this-section"></a>En esta sección  
 [Conexión a un origen de datos](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 Describe cómo se establece una conexión con un origen de datos y cómo trabajar con eventos de conexión.  
  
 [Cadenas de conexión](../../../../docs/framework/data/adonet/connection-strings.md)  
 Contiene temas en los que se describen varios aspectos del uso de cadenas de conexión, entre los que se incluyen las palabras clave de cadena de conexión, información sobre seguridad y el almacenamiento y recuperación de cadenas de conexión.  
  
 [Agrupación de conexiones](../../../../docs/framework/data/adonet/connection-pooling.md)  
 Describe la agrupación de conexiones para los proveedores de datos .NET Framework.  
  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 Contiene temas en los que se describe cómo crear comandos y generadores de comandos, configurar parámetros y cómo ejecutar comandos para recuperar y modificar datos.  
  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 Contiene temas en los que se describen DataReaders, DataAdapters, los parámetros, el control de eventos DataAdapter y la ejecución de operaciones por lotes.  
  
 [Las transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 Contiene temas en los que se describe cómo realizar transacciones locales y transacciones distribuidas, y cómo trabajar con la simultaneidad optimista.  
  
 [Recuperar valores Autonuméricos e identidad](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 Proporciona un ejemplo de asignación de los valores generados para una **identidad** columna en un [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] tabla o para una **Autonumérico** campo en una tabla de Microsoft Access, para una columna de una fila insertada en una tabla. Describe la combinación de valores de identidad en una `DataTable`.  
  
 [Recuperar datos binarios](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 Describe cómo recuperar datos binarios o estructuras de datos de gran tamaño mediante `CommandBehavior`.`SequentialAccess` Para modificar el comportamiento predeterminado de un `DataReader`.  
  
 [Modificar datos con procedimientos almacenados](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 Describe cómo utilizar parámetros de entrada y parámetros de salida de procedimientos almacenados para insertar una fila en una base de datos y devolver un nuevo valor de identidad.  
  
 [Recuperar información del esquema de base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 Describe cómo obtener de un origen de dstos las bases de datos o catálogos disponibles, las tablas y vistas de una base de datos, las restricciones que existen para las tablas y otra información de esquema.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Describe el modelo de generador de proveedor y demuestra cómo usar las clases base del espacio de nombres `System.Data.Common`.  
  
 [Seguimiento de datos en ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md)  
 Describe cómo ADO.NET proporciona funcionalidad integrada de traza de datos.  
  
 [Contadores de rendimiento](../../../../docs/framework/data/adonet/performance-counters.md)  
 Describe los contadores de rendimiento disponibles para `SqlClient` y `OracleClient`.  
  
 [Programación asincrónica](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 Describe la compatibilidad de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] con programación asincrónica.  
  
 [Compatibilidad con Streaming de SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 Explica cómo escribir aplicaciones que transmiten por secuencias datos de [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] sin cargarlos totalmente en memoria.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de tipos de datos en ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [Objetos DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proteger aplicaciones de ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server y ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
