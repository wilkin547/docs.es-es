---
description: Más información acerca de cómo modificar datos con un DbDataAdapter
title: Modificar datos con un objeto DbDataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e35c7f9e-648b-4fcc-9361-d365c3e42c9a
ms.openlocfilehash: 749c56e8db76a469d7ebf0e503508665c2fdbd94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786256"
---
# <a name="modifying-data-with-a-dbdataadapter"></a>Modificar datos con un objeto DbDataAdapter

El método <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> de un objeto <xref:System.Data.Common.DbProviderFactory> proporciona un objeto <xref:System.Data.Common.DbDataAdapter> fuertemente tipado en el proveedor de datos subyacente especificado en el momento de crear el generador. Se puede utilizar <xref:System.Data.Common.DbCommandBuilder> para crear comandos para insertar, actualizar y eliminar datos desde <xref:System.Data.DataSet> a un origen de datos.  
  
## <a name="retrieving-data-with-a-dbdataadapter"></a>Recuperación de datos con un DbDataAdapter  

 Este ejemplo muestra cómo crear un `DbDataAdapter` fuertemente tipado basado en el nombre de proveedor y la cadena de conexión. El código utiliza el método <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> de <xref:System.Data.Common.DbProviderFactory> para crear <xref:System.Data.Common.DbConnection>. A continuación, el código utiliza el método <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A> para crear un <xref:System.Data.Common.DbCommand> para seleccionar datos estableciendo sus propiedades `CommandText` y `Connection`. Finalmente, el código crear un objeto <xref:System.Data.Common.DbDataAdapter> mediante el método <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> y establece su propiedad `SelectCommand`. El método `Fill` de `DbDataAdapter` carga los datos en <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/VB/source.vb#1)]  
  
## <a name="modifying-data-with-a-dbdataadapter"></a>Modificar datos con un objeto DbDataAdapter  

 Este ejemplo muestra cómo modificar datos en `DataTable` utilizando <xref:System.Data.Common.DbDataAdapter> mediante <xref:System.Data.Common.DbCommandBuilder> para generar los comandos necesarios para actualizar datos en el origen de datos. El <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> de `DbDataAdapter` se configura para recuperar el CustomerID y el CompanyName desde la tabla Customers. El método <xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A> se utiliza para establecer la propiedad <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, el método <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A> para establecer la propiedad <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> y el método <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A> para establecer la propiedad <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A>. El código agrega una nueva fila a la tabla Customers y actualiza el origen de datos. A continuación, el código localiza la fila agregada buscando en CustomerID, que es la clave principal definida para la tabla Customers. Cambia el CompanyName y actualiza el origen de datos. Finalmente, el código elimina la fila.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/VB/source.vb#1)]  
  
## <a name="handling-parameters"></a>Control de parámetros  

 Los proveedores de datos .NET Framework administran la asignación de nombres y la especificación de parámetros y marcadores de posición de parámetros de diferente forma. Esta sintaxis se adapta a un origen de datos específico, como se describe en la tabla siguiente.  
  
|Proveedor de datos|Sintaxis de nomenclatura de parámetros|  
|-------------------|-----------------------------|  
|`SqlClient`|Usa parámetros con nombre, con el formato `@`*nombreDeParámetro*.|  
|`OracleClient`|Usa parámetros con nombre, con el formato `:`*nombreDeParámetro* (o *nombreDeParámetro*).|  
|`OleDb`|Usa marcadores de parámetro de posición, indicados por un signo de interrogación (`?`).|  
|`Odbc`|Usa marcadores de parámetro de posición, indicados por un signo de interrogación (`?`).|  
  
 El modelo de generador no es útil para la creación de objetos `DbCommand` y `DbDataAdapter` con parámetros. Es necesario bifurcar en el código para crear parámetros que se adapten al proveedor de datos.  
  
> [!IMPORTANT]
> Por razones de seguridad, no es recomendable evitar totalmente parámetros específicos del proveedor mediante el uso de concatenación de cadenas para construir instrucciones SQL directas. El uso de cadenas de concatenación en lugar de parámetros expone a la aplicación a ataques por inyección de SQL.  
  
## <a name="see-also"></a>Consulte también

- [Objetos DbProviderFactory](dbproviderfactories.md)
- [Obtener un objeto DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand y DbException](dbconnection-dbcommand-and-dbexception.md)
- [Información general de ADO.NET](ado-net-overview.md)
