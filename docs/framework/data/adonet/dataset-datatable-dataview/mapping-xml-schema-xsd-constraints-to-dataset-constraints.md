---
title: Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: c9cd97535a0165b82f0823c1f17f621491d4255c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44186960"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos
El lenguaje de definición de esquemas XML (XSD) permite especificar restricciones para los elementos y atributos que define. Al asignar un esquema XML al esquema relacional de un <xref:System.Data.DataSet>, restricciones de esquema XML se asignan a las restricciones relacionales apropiadas en las tablas y columnas dentro de la **DataSet**.  
  
 En esta sección se describe la asignación de las siguientes restricciones de esquema XML:  
  
-   La restricción de unicidad especificada mediante el **único** elemento.  
  
-   La restricción de clave especificada mediante el **clave** elemento.  
  
-   La restricción keyref especificada mediante el **keyref** elemento.  
  
 El uso de una restricción sobre un elemento o un atributo permite especificar ciertas restricciones para los valores del elemento en cualquier instancia del documento. Por ejemplo, una restricción de clave en un **CustomerID** elemento secundario de un **cliente** elemento en el esquema indica que los valores de la **CustomerID** debe ser el elemento secundario único en cualquier instancia del documento, y que no se permiten valores null.  
  
 También se pueden especificar restricciones entre los elementos y atributos de un documento para establecer una relación dentro del documento. Las restricciones key y keyref se utilizan en el esquema para especificar las restricciones dentro del documento, lo que da como resultado una relación entre los elementos y atributos del documento.  
  
 El proceso de asignación convierte estas restricciones del esquema en las restricciones apropiadas para las tablas creadas dentro de la **DataSet**.  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignación de restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones unique en una **DataSet**.  
  
 [Asignación de restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave (restricciones únicas donde no se permiten valores null) en un **DataSet**.  
  
 [Asignación de restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones (clave externa) en keyref un **DataSet**.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **DataSet** creado a partir de un esquema XSD.  
  
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML utilizados para crear relaciones entre columnas de tabla en un **DataSet**.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
