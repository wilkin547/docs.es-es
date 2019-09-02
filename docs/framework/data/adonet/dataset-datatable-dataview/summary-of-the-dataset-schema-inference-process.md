---
title: Resumen del proceso de inferencia del esquema de DataSet
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 5266d08212e5259bd5b242a70d61e29ad9008006
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203242"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Resumen del proceso de inferencia del esquema de DataSet
El proceso de inferencia determina en primer lugar, a partir del documento XML, qué elementos se inferirán como tablas. A partir del XML restante, el proceso de inferencia determina las columnas para dichas tablas. En el caso de las tablas anidadas, el proceso de inferencia genera objetos <xref:System.Data.DataRelation> y <xref:System.Data.ForeignKeyConstraint> anidados.  
  
 A continuación se resumen brevemente las reglas de inferencia:  
  
- Los elementos que tienen atributos se deducen como tablas.  
  
- Los elementos que tienen elementos secundarios se deducen como tablas.  
  
- Los elementos que se repiten se deducen como una única tabla.  
  
- Si el elemento de documento, o raíz, no tiene atributos y no se deduciría ningún elemento secundario como una columna, se deduce como un <xref:System.Data.DataSet>. De lo contrario, el elemento de documento se deducirá como una tabla.  
  
- Los atributos se deducen como columnas.  
  
- Los elementos que no tienen atributos o elementos secundarios, y que no se repiten, se deducen como columnas.  
  
- En el caso de los elementos que se deducen como tablas anidadas dentro de otros elementos que también se deducen como tablas, se crea una **DataRelation** anidada entre las dos tablas. Se agrega una nueva columna de clave principal denominada **TableName_Id** a ambas tablas y se usa en **DataRelation**. Se crea una **ForeignKeyConstraint** entre las dos tablas mediante la columna **TableName_Id** .  
  
- En el caso de los elementos que se deducen como tablas y que contienen texto pero que no tienen elementos secundarios, se crea una nueva columna denominada **TableName_Text** para el texto de cada uno de los elementos. Si un elemento se deduce como una tabla y tiene texto, pero también tiene elementos secundarios, se pasa por alto el texto.  
  
## <a name="see-also"></a>Vea también

- [Inferencia de una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Carga de un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Carga de información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
