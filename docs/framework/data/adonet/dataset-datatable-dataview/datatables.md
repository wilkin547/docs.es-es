---
title: Objetos DataTable
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 369855d1aff854b60c251010ec42557b70c093c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952653"
---
# <a name="datatables"></a>Objetos DataTable
Un objeto <xref:System.Data.DataSet> está formado por una colección de tablas, relaciones y restricciones. En ADO.net, <xref:System.Data.DataTable> los objetos se utilizan para representar las tablas de un **conjunto de DataSet**. Un **objeto DataTable** representa una tabla de datos relacionales en memoria; los datos son locales para. Aplicación basada en NET en la que reside, pero se puede rellenar a partir de un origen de datos, como Microsoft SQL Server usar un objeto **DataAdapter** para obtener más información, vea rellenar [un DataSet desde un DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).  
  
 La clase **DataTable** es un miembro del espacio de nombres **System. Data** dentro de la biblioteca de clases de .NET Framework. Puede crear y usar un **objeto DataTable** de forma independiente o como miembro de un **conjunto**de los objetos, y los <xref:System.Data.DataView>objetos **DataTable** también se pueden usar junto con otros objetos .NET Framework, incluido. Se tiene acceso a la colección de tablas de un **DataSet** a través de la propiedad **tables** del objeto **DataSet** .  
  
 El esquema, o estructura, de una tabla se representa con columnas y restricciones. El esquema de un **DataTable** se define mediante <xref:System.Data.DataColumn> objetos, así como <xref:System.Data.ForeignKeyConstraint> objetos <xref:System.Data.UniqueConstraint> y. Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Además de un esquema, un **objeto DataTable** también debe tener filas que contengan y ordenen los datos. La clase <xref:System.Data.DataRow> representa los datos reales que contiene una tabla. Use **DataRow** y sus propiedades y métodos para recuperar, evaluar y manipular los datos de una tabla. Al tener acceso a los datos de una fila y cambiarlos, el objeto **DataRow** mantiene su estado actual y original.  
  
 Se pueden crear relaciones primarias-secundarias entre tablas utilizando una o varias columnas relacionadas de las tablas. Cree una relación entre los objetos **DataTable** mediante <xref:System.Data.DataRelation>. Los objetos **DataRelation** se pueden usar para devolver las filas secundarias o primarias relacionadas de una fila determinada. Para obtener más información, vea [agregar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Explica cómo crear un **objeto DataTable** y agregarlo a un **conjunto de DataSet**.  
  
 [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Proporciona información sobre la creación y el uso de objetos **DataColumn** y restricciones.  
  
 [Manipulación de datos en un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Explica cómo se agregan, modifican y eliminan datos en una tabla. Explica cómo utilizar los eventos **DataTable** para examinar los cambios en los datos de la tabla.  
  
 [Control de eventos de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Proporciona información sobre los eventos disponibles para su uso con una **DataTable**, incluidos los eventos cuando se modifican los valores de columna y se agregan o eliminan filas.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y para administrar los datos de las aplicaciones.  
  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Proporciona información sobre el **conjunto** de datos ADO.net, incluido cómo crear relaciones entre las tablas.  
  
 <xref:System.Data.Constraint>  
 Proporciona información de referencia sobre el objeto de **restricción** .  
  
 <xref:System.Data.DataColumn>  
 Proporciona información de referencia sobre el objeto **DataColumn** .  
  
 <xref:System.Data.DataSet>  
 Proporciona información de referencia sobre el objeto **DataSet** .  
  
 <xref:System.Data.DataTable>  
 Proporciona información de referencia sobre el objeto **DataTable** .  
  
 [Información general de la biblioteca de clases](../../../../standard/class-library-overview.md)  
 Proporciona información general sobre la biblioteca de clases de .NET Framework, incluido el espacio de nombres **System** , así como su espacio de nombres de segundo nivel, **System. Data**.  
  
## <a name="see-also"></a>Vea también

- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
