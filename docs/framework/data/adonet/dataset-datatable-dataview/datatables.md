---
title: Objetos DataTable
description: Obtenga información sobre una DataTable de ADO.NET, que representa una tabla de datos relacionales en memoria, local para. Aplicación basada en .net donde reside.
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: d501096b4abe94653acdc5249c120abff94534d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202310"
---
# <a name="datatables"></a>Objetos DataTable

Un objeto <xref:System.Data.DataSet> está formado por una colección de tablas, relaciones y restricciones. En ADO.NET, <xref:System.Data.DataTable> los objetos se utilizan para representar las tablas de un **conjunto de DataSet**. Un **objeto DataTable** representa una tabla de datos relacionales en memoria; los datos son locales para. Aplicación basada en NET en la que reside, pero se puede rellenar a partir de un origen de datos, como Microsoft SQL Server usar un objeto **DataAdapter** para obtener más información, vea [rellenar un DataSet desde un DataAdapter](../populating-a-dataset-from-a-dataadapter.md).  
  
 La clase **DataTable** es un miembro del espacio de nombres **System. Data** dentro de la biblioteca de clases de .NET Framework. Puede crear y usar un **objeto DataTable** de forma independiente o como miembro de un **conjunto**de los objetos, y los objetos **DataTable** también se pueden usar junto con otros objetos .NET Framework, incluido <xref:System.Data.DataView> . Se tiene acceso a la colección de tablas de un **DataSet** a través de la propiedad **tables** del objeto **DataSet** .  
  
 El esquema, o estructura, de una tabla se representa con columnas y restricciones. El esquema de un **DataTable** se define mediante <xref:System.Data.DataColumn> objetos, así como <xref:System.Data.ForeignKeyConstraint> <xref:System.Data.UniqueConstraint> objetos y. Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Además de un esquema, un **objeto DataTable** también debe tener filas que contengan y ordenen los datos. La clase <xref:System.Data.DataRow> representa los datos reales que contiene una tabla. Use **DataRow** y sus propiedades y métodos para recuperar, evaluar y manipular los datos de una tabla. Al tener acceso a los datos de una fila y cambiarlos, el objeto **DataRow** mantiene su estado actual y original.  
  
 Se pueden crear relaciones primarias-secundarias entre tablas utilizando una o varias columnas relacionadas de las tablas. Cree una relación entre los objetos **DataTable** mediante <xref:System.Data.DataRelation> . Los objetos **DataRelation** se pueden usar para devolver las filas secundarias o primarias relacionadas de una fila determinada. Para obtener más información, vea [agregar objetos DataRelation](adding-datarelations.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [Crear un objeto DataTable](creating-a-datatable.md)  
 Explica cómo crear un **objeto DataTable** y agregarlo a un **conjunto de DataSet**.  
  
 [Definición del esquema de DataTable](datatable-schema-definition.md)  
 Proporciona información sobre la creación y el uso de objetos **DataColumn** y restricciones.  
  
 [Manipular datos en un objeto DataTable](manipulating-data-in-a-datatable.md)  
 Explica cómo se agregan, modifican y eliminan datos en una tabla. Explica cómo utilizar los eventos **DataTable** para examinar los cambios en los datos de la tabla.  
  
 [Controlar eventos de DataTable](handling-datatable-events.md)  
 Proporciona información sobre los eventos disponibles para su uso con una **DataTable**, incluidos los eventos cuando se modifican los valores de columna y se agregan o eliminan filas.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [ADO.NET](../index.md)  
 Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y para administrar los datos de las aplicaciones.  
  
 [Objetos DataSet, DataTable y DataView](index.md)  
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
  
## <a name="see-also"></a>Consulte también

- [Información general de ADO.NET](../ado-net-overview.md)
