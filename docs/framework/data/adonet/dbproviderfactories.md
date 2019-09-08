---
title: Objetos DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: e3ea9e3d083314f8df25f9edadbd1a18f1227293
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784101"
---
# <a name="dbproviderfactories"></a>Objetos DbProviderFactory
El espacio de nombres <xref:System.Data.Common> proporciona clases para la creación de instancias <xref:System.Data.Common.DbProviderFactory> que permiten trabajar con orígenes de datos específicos. Cuando crea una instancia <xref:System.Data.Common.DbProviderFactory> y le pasa información acerca del proveedor de datos, la instancia `DbProviderFactory` puede determinar el objeto fuertemente tipado correcto que debe devolver en función de la información que se ha proporcionado.  
  
 Comenzando con la versión 4 de .NET Framework , los proveedores de datos como <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> y <xref:System.Data.OracleClient> ya no aparecen en el archivo machine.config; sin embargo, sí aparecerán los proveedores personalizados.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre el modelo de fábrica](factory-model-overview.md)  
 Proporciona una introducción al patrón de diseño de generadores y a la interfaz de programación.  
  
 [Obtención de un objeto DbProviderFactory](obtaining-a-dbproviderfactory.md)  
 Muestra cómo enumerar los proveedores de datos instalados y cómo crear una clase <xref:System.Data.Common.DbConnection> a partir de `DbProviderFactory`.  
  
 [DbConnection, DbCommand y DbException](dbconnection-dbcommand-and-dbexception.md)  
 Muestra cómo crear objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbDataReader>, y cómo controlar los errores de datos con <xref:System.Data.Common.DbException>.  
  
 [Modificación de datos con un objeto DbDataAdapter](modifying-data-with-a-dbdataadapter.md)  
 Muestra cómo usar un objeto <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> para recuperar y modificar datos.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
