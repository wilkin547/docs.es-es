---
title: Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: a2b28b0dcb2e2858c7328854650667f51e83166a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185293"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos

El lenguaje de definición de esquemas XML (XSD) permite especificar restricciones para los elementos y atributos que define. Al asignar un esquema XML a un esquema relacional en un <xref:System.Data.DataSet> , las restricciones de esquema XML se asignan a las restricciones relacionales apropiadas en las tablas y columnas del **conjunto de DataSet**.  
  
 En esta sección se describe la asignación de las siguientes restricciones de esquema XML:  
  
- La restricción de unicidad especificada mediante el elemento **único** .  
  
- Restricción de clave especificada mediante el elemento **key** .  
  
- La restricción keyref especificada mediante el elemento **keyref** .  
  
 El uso de una restricción sobre un elemento o un atributo permite especificar ciertas restricciones para los valores del elemento en cualquier instancia del documento. Por ejemplo, una restricción de clave en un elemento secundario **CustomerID** de un elemento **Customer** del esquema indica que los valores del elemento secundario **CustomerID** deben ser únicos en cualquier instancia de documento y que no se permiten valores NULL.  
  
 También se pueden especificar restricciones entre los elementos y atributos de un documento para establecer una relación dentro del documento. Las restricciones key y keyref se utilizan en el esquema para especificar las restricciones dentro del documento, lo que da como resultado una relación entre los elementos y atributos del documento.  
  
 El proceso de asignación convierte estas restricciones de esquema en restricciones adecuadas en las tablas creadas en el **conjunto de DataSet**.  
  
## <a name="in-this-section"></a>En esta sección  

 [Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones UNIQUE en un **DataSet**.  
  
 [Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave (restricciones únicas en las que no se permiten valores NULL) en un **conjunto de DataSet**.  
  
 [Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones keyref (clave externa) en un **conjunto de DataSet**.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **DataSet** que se crea a partir del esquema XSD.  
  
 [Generar relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML que se utilizan para crear relaciones entre las columnas de tabla de un **conjunto de DataSet**.  
  
## <a name="see-also"></a>Consulte también

- [Información general de ADO.NET](../ado-net-overview.md)
