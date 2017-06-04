---
title: "Asignar restricciones de esquema XML (XSD) a las restricciones de DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Asignar restricciones de esquema XML (XSD) a las restricciones de DataSet
El lenguaje de definición de esquemas XML \(XSD\) permite especificar restricciones para los elementos y atributos que define.  Al asignar un esquema XML al esquema relacional de un <xref:System.Data.DataSet>, las restricciones de esquema XML se asignan a las restricciones relacionales apropiadas de las tablas y columnas contenidas en el **DataSet**.  
  
 En esta sección se describe la asignación de las siguientes restricciones de esquema XML:  
  
-   La restricción de unicidad especificada mediante el elemento **unique**.  
  
-   La restricción de clave especificada mediante el elemento **key**.  
  
-   La restricción keyref especificada mediante el elemento **keyref**.  
  
 El uso de una restricción sobre un elemento o un atributo permite especificar ciertas restricciones para los valores del elemento en cualquier instancia del documento.  Por ejemplo, una restricción de clave en un elemento secundario **CustomerID** de un elemento **Customer** del esquema indica que los valores del elemento secundario **CustomerID** deben ser únicos en cualquier instancia del documento y que no se permiten valores nulos.  
  
 También se pueden especificar restricciones entre los elementos y atributos de un documento para establecer una relación dentro del documento.  Las restricciones key y keyref se utilizan en el esquema para especificar las restricciones dentro del documento, lo que da como resultado una relación entre los elementos y atributos del documento.  
  
 El proceso de asignación convierte estas restricciones del esquema en las restricciones apropiadas para las tablas creadas dentro del **DataSet**.  
  
## En esta sección  
 [Asignar restricciones unique de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones únicas en un **DataSet**.  
  
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave \(restricciones únicas donde no se permiten valores nulos\) en un **DataSet**.  
  
 [Asignar restricciones keyref de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones keyref \(de clave externa\) en un **DataSet**.  
  
## Secciones relacionadas  
 [Derivar la estructura relacional de DataSet desde la definición de esquema XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **DataSet** creado a partir de un esquema XSD.  
  
 [Generar las relaciones de DataSet desde la definición de esquemas XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML utilizados para crear relaciones entre columnas de tabla de un **DataSet**.  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)