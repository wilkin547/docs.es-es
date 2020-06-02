---
title: Recuperar y modificar datos
description: En el .NET Framework, los proveedores de datos de ADO.NET sirven como puente entre una aplicación y un origen de datos para leer y actualizar datos.
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: f916324dc829526a5e6b0078021b09786755f666
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286616"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>Recuperar y modificar datos en ADO.NET
La principal función de cualquier aplicación de base de datos es conectarse a un origen de datos y recuperar los datos que contiene. Los .NET Framework proveedores de datos de ADO.NET sirven como puente entre una aplicación y un origen de datos, lo que le permite ejecutar comandos, así como recuperar datos mediante un **DataReader** o un **DataAdapter**. Una función clave de cualquier aplicación de base de datos es la capacidad de actualizar los datos almacenados en la misma. En ADO.NET, la actualización de datos implica el uso de los objetos de comandos **DataAdapter** y <xref:System.Data.DataSet> , y, y también puede implicar el uso de transacciones. **Command**  
  
## <a name="in-this-section"></a>En esta sección  
 [Conectarse a un origen de datos](connecting-to-a-data-source.md)  
 Describe cómo se establece una conexión con un origen de datos y cómo trabajar con eventos de conexión.  
  
 [Cadenas de conexión](connection-strings.md)  
 Contiene temas en los que se describen varios aspectos del uso de cadenas de conexión, entre los que se incluyen las palabras clave de cadena de conexión, información sobre seguridad y el almacenamiento y recuperación de cadenas de conexión.  
  
 [Agrupar conexiones](connection-pooling.md)  
 Describe la agrupación de conexiones para los proveedores de datos .NET Framework.  
  
 [Comandos y parámetros](commands-and-parameters.md)  
 Contiene temas en los que se describe cómo crear comandos y generadores de comandos, configurar parámetros y cómo ejecutar comandos para recuperar y modificar datos.  
  
 [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)  
 Contiene temas en los que se describen DataReaders, DataAdapters, los parámetros, el control de eventos DataAdapter y la ejecución de operaciones por lotes.  
  
 [Transacciones y simultaneidad](transactions-and-concurrency.md)  
 Contiene temas en los que se describe cómo realizar transacciones locales y transacciones distribuidas, y cómo trabajar con la simultaneidad optimista.  
  
 [Recuperar valores autonuméricos y de identidad](retrieving-identity-or-autonumber-values.md)  
 Proporciona un ejemplo de asignación de los valores generados para una columna de **identidad** en una tabla de SQL Server o para un campo **Autonumber** de una tabla de Microsoft Access, a una columna de una fila insertada en una tabla. Describe la combinación de valores de identidad en una `DataTable`.  
  
 [Recuperar datos binarios](retrieving-binary-data.md)  
 Describe cómo recuperar datos binarios o estructuras de datos de gran tamaño mediante `CommandBehavior` .`SequentialAccess` para modificar el comportamiento predeterminado de un `DataReader` .  
  
 [Modificar datos con procedimientos almacenados](modifying-data-with-stored-procedures.md)  
 Describe cómo utilizar parámetros de entrada y parámetros de salida de procedimientos almacenados para insertar una fila en una base de datos y devolver un nuevo valor de identidad.  
  
 [Recuperar información del esquema de la base de datos](retrieving-database-schema-information.md)  
 Describe cómo obtener de un origen de dstos las bases de datos o catálogos disponibles, las tablas y vistas de una base de datos, las restricciones que existen para las tablas y otra información de esquema.  
  
 [Objetos DbProviderFactory](dbproviderfactories.md)  
 Describe el modelo de generador de proveedor y demuestra cómo usar las clases base del espacio de nombres `System.Data.Common`.  
  
 [Traza de datos en ADO.NET](data-tracing.md)  
 Describe cómo ADO.NET proporciona funcionalidad integrada de traza de datos.  
  
 [Contadores de rendimiento](performance-counters.md)  
 Describe los contadores de rendimiento disponibles para `SqlClient` y `OracleClient`.  
  
 [Programación asincrónica](asynchronous-programming.md)  
 Describe la compatibilidad de ADO.NET con la programación asincrónica.  
  
 [Compatibilidad de transmisión de datos de SqlClient](sqlclient-streaming-support.md)  
 Describe cómo escribir aplicaciones que transmiten datos de SQL Server sin que se carguen por completo en la memoria.  
  
## <a name="see-also"></a>Consulte también

- [Asignaciones de tipos de datos en ADO.NET](data-type-mappings-in-ado-net.md)
- [Objetos DataSet, DataTable y DataView](./dataset-datatable-dataview/index.md)
- [Proteger aplicaciones de ADO.NET](securing-ado-net-applications.md)
- [SQL Server y ADO.NET](./sql/index.md)
- [Información general de ADO.NET](ado-net-overview.md)
