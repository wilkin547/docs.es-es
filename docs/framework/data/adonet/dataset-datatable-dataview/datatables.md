---
title: Objetos DataTable
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 2849d159fbfdb0c0739b76fd288a987d4ce3d02f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395789"
---
# <a name="datatables"></a>Objetos DataTable
Un objeto <xref:System.Data.DataSet> está formado por una colección de tablas, relaciones y restricciones. En ADO.NET, <xref:System.Data.DataTable> objetos se utilizan para representar las tablas en un **DataSet**. Un **DataTable** representa una tabla de datos relacionales en memoria; los datos son locales para el. Aplicación basada en red en el que reside, pero se pueden llenar desde un origen de datos, como Microsoft SQL Server mediante un **DataAdapter** para obtener más información, consulte [llenar un DataSet desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .  
  
 El **DataTable** clase es un miembro de la **System.Data** espacio de nombres dentro de la biblioteca de clases de .NET Framework. Puede crear y usar un **DataTable** por separado o como un miembro de un **DataSet**, y **DataTable** también pueden usarse junto con otros objetos de .NET Framework, objetos incluido el <xref:System.Data.DataView>. Obtener acceso a la colección de tablas en un **conjunto de datos** a través de la **tablas** propiedad de la **DataSet** objeto.  
  
 El esquema, o estructura, de una tabla se representa con columnas y restricciones. Definir el esquema de un **DataTable** mediante <xref:System.Data.DataColumn> objetos como <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint> objetos. Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Además del esquema, un **DataTable** debe tener también filas para albergar y ordenar los datos. La clase <xref:System.Data.DataRow> representa los datos reales que contiene una tabla. Usa el **DataRow** y sus propiedades y métodos para recuperar, evaluar y manipular los datos en una tabla. Que tenga acceso y cambiar los datos dentro de una fila, el **DataRow** objeto mantiene su estado actual y original.  
  
 Se pueden crear relaciones primarias-secundarias entre tablas utilizando una o varias columnas relacionadas de las tablas. Crear una relación entre **DataTable** objetos mediante un <xref:System.Data.DataRelation>. **DataRelation** objetos, a continuación, pueden usarse para devolver las filas relacionadas de primario o secundario de una fila determinada. Para obtener más información, consulte [agregar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Explica cómo crear un **DataTable** y agréguelo a un **DataSet**.  
  
 [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Proporciona información sobre cómo crear y usar **DataColumn** objetos y las restricciones.  
  
 [Manipulación de datos en un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Explica cómo se agregan, modifican y eliminan datos en una tabla. Explica cómo usar **DataTable** eventos para examinar los cambios a los datos en la tabla.  
  
 [Control de eventos de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Proporciona información sobre los eventos disponibles para su uso con un **DataTable**, incluidos los eventos cuando se modifican los valores de columna y se agregan o eliminan filas.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y para administrar los datos de las aplicaciones.  
  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Proporciona información acerca de ADO.NET **DataSet** incluido cómo crear relaciones entre tablas.  
  
 <xref:System.Data.Constraint>  
 Proporciona información de referencia sobre la **restricción** objeto.  
  
 <xref:System.Data.DataColumn>  
 Proporciona información de referencia sobre la **DataColumn** objeto.  
  
 <xref:System.Data.DataSet>  
 Proporciona información de referencia sobre la **DataSet** objeto.  
  
 <xref:System.Data.DataTable>  
 Proporciona información de referencia sobre la **DataTable** objeto.  
  
 [Información general de la biblioteca de clases](../../../../../docs/standard/class-library-overview.md)  
 Proporciona información general de la biblioteca de clases de .NET Framework, incluido el **sistema** espacio de nombres, así como su espacio de nombres de segundo nivel, **System.Data**.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
