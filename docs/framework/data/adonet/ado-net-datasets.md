---
title: Objetos DataSet de ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b9d566f99802ea80ae73132579bb3068b1ff3b28
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="adonet-datasets"></a>Objetos DataSet de ADO.NET
El objeto <xref:System.Data.DataSet> es esencial para la compatibilidad con escenarios de datos distribuidos desconectados con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. El **conjunto de datos** es una representación residente en memoria de datos que proporciona un modelo de programación relacional coherente independientemente del origen de datos. Se puede utilizar con muchos y distintos orígenes de datos, con datos XML o para administrar datos locales de la aplicación. El **conjunto de datos** representa un conjunto completo de datos, incluidas tablas relacionadas, restricciones y relaciones entre las tablas. La siguiente ilustración muestra la **conjunto de datos** modelo de objetos.  
  
 ![ADO.Net graphic](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Modelo de objetos DataSet  
  
 Los métodos y objetos de un **conjunto de datos** son coherentes con los del modelo de base de datos relacional.  
  
 El **conjunto de datos** también se puede mantener y recargar su contenido como XML y su esquema como esquema XML schema definition language (XSD). Para obtener más información, vea [Using XML in a DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 Un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **conjunto de datos** contiene una colección de cero o más tablas representadas por <xref:System.Data.DataTable> objetos. El <xref:System.Data.DataTableCollection> contiene todos los **DataTable** objetos en un **conjunto de datos**.  
  
 A **DataTable** se define en el <xref:System.Data> espacio de nombres y representa una única tabla de datos residentes en memoria. Contiene una colección de columnas representadas por una <xref:System.Data.DataColumnCollection>, así como restricciones representadas por una <xref:System.Data.ConstraintCollection>, que juntas definen el esquema de la tabla. A **DataTable** también contiene una colección de filas representadas por la <xref:System.Data.DataRowCollection>, que contiene los datos de la tabla. Una <xref:System.Data.DataRow> conserva, junto con su estado actual, sus versiones actual y original para identificar los cambios en los valores almacenados en la fila.  
  
## <a name="the-dataview-class"></a>Clase DataView  
 Una <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace a datos. Mediante <xref:System.Data.DataView> puede exponer los datos de una tabla con distintos criterios de ordenación y filtrar los datos por el estado de fila o basándose en una expresión de filtro. Para obtener más información, consulte [DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 A **conjunto de datos** contiene relaciones en su <xref:System.Data.DataRelationCollection> objeto. Una relación, representada por la <xref:System.Data.DataRelation> objeto, asocia las filas de una **DataTable** con filas de otra **DataTable**. Las relaciones son análogas a las rutas de acceso de unión que podrían existir entre columnas de claves principales y externas en una base de datos relacional. A **DataRelation** identifica las columnas coincidentes en dos tablas de un **conjunto de datos**.  
  
 Las relaciones habilitan la navegación de una tabla a otra en una **conjunto de datos**. Los elementos esenciales de un **DataRelation** son el nombre de la relación, el nombre de las tablas relacionadas y las columnas relacionadas de cada tabla. Es posible crear relaciones con más de una columna por tabla si se especifica una matriz de objetos <xref:System.Data.DataColumn> como columnas de claves. Al agregar una relación con la <xref:System.Data.DataRelationCollection>, puede agregar opcionalmente una **UniqueKeyConstraint** y un **ForeignKeyConstraint** para exigir restricciones de integridad cuando se realizan cambios en la columna relacionada valores.  
  
 Para obtener más información, consulte [agregar objetos DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 Puede rellenar un **conjunto de datos** de un documento o secuencia XML. Puede usar la secuencia o documento XML para suministrar la **conjunto de datos** datos, información de esquema o ambos. La información suministrada desde la secuencia o documento XML puede combinarse con datos existentes o información de esquema ya está presente en el **conjunto de datos**. Para obtener más información, vea [Using XML in a DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 El **conjunto de datos**, **DataTable**, y **DataColumn** todos tienen un **ExtendedProperties** propiedad. **ExtendedProperties** es un **PropertyCollection** donde puede colocar información personalizada, como la instrucción SELECT que se utilizó para generar el conjunto de resultados o la hora se generan los datos. El **ExtendedProperties** colección se mantiene con la información de esquema para el **conjunto de datos**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] proporciona capacidades LINQ (Language Integrated Query) para datos desconectados almacenados en DataSet. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]utiliza norma [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] sintaxis y proporciona comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense cuando se usa el [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE.  
  
 Para más información, vea [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Objetos DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
