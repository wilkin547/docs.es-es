---
title: "DataTables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTables
Un objeto <xref:System.Data.DataSet> está formado por una colección de tablas, relaciones y restricciones.  En ADO .NET, los objetos <xref:System.Data.DataTable> se utilizan para representar las tablas de un **DataSet**.  Un objeto **DataTable** representa una tabla de datos relacionales de la memoria; los datos son locales de la aplicación basada en .NET en la que residen, pero se pueden llenar desde un origen de datos como Microsoft SQL Server mediante un **DataAdapter** Para obtener más información, vea [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).  
  
 La clase **DataTable** es miembro del espacio de nombres **System.Data** dentro de la biblioteca de clases de .NET Framework.  Se puede crear y utilizar **DataTable** de manera independiente o como miembro de un **DataSet** y los objetos **DataTable** se pueden utilizar también en combinación con otros objetos de .NET Framework, incluido <xref:System.Data.DataView>.  Al conjunto de tablas de un **DataSet** se puede tener acceso mediante la propiedad **Tables** del objeto **DataSet**.  
  
 El esquema, o estructura, de una tabla se representa con columnas y restricciones.  El esquema de una **DataTable** se define mediante objetos <xref:System.Data.DataColumn>, <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>.  Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.  
  
 Además del esquema, un objeto **DataTable** debe tener también filas en las que albergar y ordenar los datos.  La clase <xref:System.Data.DataRow> representa los datos reales que contiene una tabla.  La clase **DataRow**, sus propiedades y métodos se utilizan para recuperar, evaluar y manipular los datos de una tabla.  Cuando se tiene acceso a los datos de una fila y se cambian, el objeto **DataRow** mantiene tanto su estado actual como el original.  
  
 Se pueden crear relaciones primarias\-secundarias entre tablas utilizando una o varias columnas relacionadas de las tablas.  Se pueden crear relaciones entre objetos **DataTable** mediante un objeto <xref:System.Data.DataRelation>.  Los objetos **DataRelation** se pueden utilizar después para devolver las filas relacionadas, secundaria o primaria, de una fila concreta.  Para obtener más información, consulta [Agregar DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## En esta sección  
 [Crear DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Explica cómo se crea un objeto **DataTable** y se agrega a un objeto **DataSet**.  
  
 [Definición de esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Proporciona información acerca de la creación y uso de los objetos y restricciones de **DataColumn**.  
  
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Explica cómo se agregan, modifican y eliminan datos en una tabla.  Explica cómo se usan eventos **DataTable** para examinar los cambios de los datos de la tabla.  
  
 [Control de eventos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Proporciona información sobre los eventos disponibles que se pueden utilizar con **DataTable**, incluidos los eventos en los que se modifican los valores de columnas y se agregan o eliminan filas.  
  
## Secciones relacionadas  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y para administrar los datos de las aplicaciones.  
  
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Proporciona información sobre el objeto **DataSet** de ADO .NET, incluida la creación de relaciones entre tablas.  
  
 [Clase Constraint](frlrfSystemDataConstraintClassTopic)  
 Proporciona información de referencia sobre el objeto **Constraint**.  
  
 [Clase DataColumn](frlrfSystemDataDataColumnClassTopic)  
 Proporciona información de referencia sobre el objeto **DataColumn**.  
  
 [Clase DataSet](frlrfSystemDataDataSetClassTopic)  
 Proporciona información de referencia sobre el objeto **DataSet**.  
  
 [Clase DataTable](frlrfSystemDataDataTableClassTopic)  
 Proporciona información de referencia sobre el objeto **DataTable**.  
  
 [Información general de la biblioteca de clases](../../../../../docs/standard/class-library-overview.md)  
 Proporciona una introducción a la biblioteca de clases de .NET Framework, incluido el espacio de nombres **System** y su espacio de nombres de nivel secundario, **System.Data**.  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)