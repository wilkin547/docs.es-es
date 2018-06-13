---
title: Objetos DataTable
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: e148b20c7d8efdb16a897c5606535e4b0112ea29
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759717"
---
# <a name="datatables"></a>Objetos DataTable
Un objeto <xref:System.Data.DataSet> está formado por una colección de tablas, relaciones y restricciones. En ADO.NET, <xref:System.Data.DataTable> objetos se utilizan para representar las tablas en un **conjunto de datos**. A **DataTable** representa una tabla de datos relacionales en memoria; los datos están locales para el. Aplicación de red en el que reside, pero se pueden llenar desde un origen de datos como Microsoft SQL Server mediante un **DataAdapter** para obtener más información, consulte [llenar un DataSet desde un DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .  
  
 El **DataTable** clase es un miembro de la **System.Data** espacio de nombres dentro de la biblioteca de clases de .NET Framework. Puede crear y utilizar un **DataTable** por separado o como un miembro de un **conjunto de datos**, y **DataTable** objetos también pueden utilizarse junto con otros objetos de .NET Framework incluidas la <xref:System.Data.DataView>. Obtener acceso a la colección de tablas en un **conjunto de datos** a través de la **tablas** propiedad de la **conjunto de datos** objeto.  
  
 El esquema, o estructura, de una tabla se representa con columnas y restricciones. Definir el esquema de un **DataTable** con <xref:System.Data.DataColumn> objetos como <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint> objetos. Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Además del esquema, un **DataTable** debe tener también filas para albergar y ordenar los datos. La clase <xref:System.Data.DataRow> representa los datos reales que contiene una tabla. Usa el **DataRow** y sus propiedades y métodos para recuperar, evaluar y manipular los datos en una tabla. Que tenga acceso y cambiar los datos dentro de una fila, el **DataRow** objeto mantiene su estado actual y original.  
  
 Se pueden crear relaciones primarias-secundarias entre tablas utilizando una o varias columnas relacionadas de las tablas. Crear una relación entre **DataTable** objetos mediante un <xref:System.Data.DataRelation>. **DataRelation** objetos, a continuación, se pueden usar para devolver las filas secundarias o primarias relacionadas de una fila determinada. Para obtener más información, consulte [agregar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Explica cómo crear un **DataTable** y agréguelo a un **conjunto de datos**.  
  
 [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Proporciona información sobre cómo crear y usar **DataColumn** objetos y las restricciones.  
  
 [Manipulación de datos en un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Explica cómo se agregan, modifican y eliminan datos en una tabla. Explica cómo usar **DataTable** eventos para examinar los cambios a los datos de la tabla.  
  
 [Control de eventos de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Proporciona información acerca de los eventos disponibles para su uso con un **DataTable**, incluidos los eventos cuando se modifican los valores de columna y se agregan o eliminan filas.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y para administrar los datos de las aplicaciones.  
  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Proporciona información acerca de ADO.NET **conjunto de datos** incluido cómo crear relaciones entre tablas.  
  
 <xref:System.Data.Constraint>  
 Proporciona información de referencia sobre la **restricción** objeto.  
  
 <xref:System.Data.DataColumn>  
 Proporciona información de referencia sobre la **DataColumn** objeto.  
  
 <xref:System.Data.DataSet>  
 Proporciona información de referencia sobre la **conjunto de datos** objeto.  
  
 <xref:System.Data.DataTable>  
 Proporciona información de referencia sobre la **DataTable** objeto.  
  
 [Información general de la biblioteca de clases](../../../../../docs/standard/class-library-overview.md)  
 Proporciona información general de la biblioteca de clases de .NET Framework, incluido el **System** espacio de nombres, así como su espacio de nombres de segundo nivel, **System.Data**.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
