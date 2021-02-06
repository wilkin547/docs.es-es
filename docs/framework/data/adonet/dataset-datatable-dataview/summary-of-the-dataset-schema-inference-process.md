---
description: 'Más información acerca de: Resumen del proceso de inferencia del esquema del conjunto de DataSet'
title: Resumen del proceso de inferencia del esquema de DataSet
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 637e4325558708c15d6d4eb17de9c0cf13b3b256
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651566"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Resumen del proceso de inferencia del esquema de DataSet

El proceso de inferencia determina en primer lugar, a partir del documento XML, qué elementos se inferirán como tablas. A partir del XML restante, el proceso de inferencia determina las columnas para dichas tablas. En el caso de las tablas anidadas, el proceso de inferencia genera objetos <xref:System.Data.DataRelation> y <xref:System.Data.ForeignKeyConstraint> anidados.  
  
 A continuación se encuentra un breve resumen de las reglas de inferencia:  
  
- Los elementos que tienen atributos se deducen como tablas.  
  
- Los elementos que tienen elementos secundarios se deducen como tablas.  
  
- Los elementos que se repiten se deducen como una única tabla.  
  
- Si el elemento de documento, o raíz, no tiene atributos y no se deduciría ningún elemento secundario como una columna, se deduce como un <xref:System.Data.DataSet>. De lo contrario, el elemento de documento se deducirá como una tabla.  
  
- Los atributos se deducen como columnas.  
  
- Los elementos que no tienen atributos o elementos secundarios, y que no se repiten, se deducen como columnas.  
  
- En el caso de los elementos que se deducen como tablas anidadas dentro de otros elementos que también se deducen como tablas, se crea una **DataRelation** anidada entre las dos tablas. Se agrega una nueva columna de clave principal denominada **TableName_Id** a ambas tablas y utilizada por la **DataRelation**. Se crea una **ForeignKeyConstraint** entre las dos tablas mediante el **TableName_Id** columna.  
  
- En el caso de los elementos que se deducen como tablas y que contienen texto pero que no tienen elementos secundarios, se crea una nueva columna denominada **TableName_Text** para el texto de cada uno de los elementos. Si un elemento se deduce como una tabla y tiene texto, pero también tiene elementos secundarios, se pasa por alto el texto.  
  
## <a name="see-also"></a>Vea también

- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
