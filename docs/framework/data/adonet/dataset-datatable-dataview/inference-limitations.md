---
description: 'Más información acerca de: limitaciones de inferencia'
title: Limitaciones de inferencia
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 926e456acfc5eac2598be40490b72523facfd058
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652268"
---
# <a name="inference-limitations"></a>Limitaciones de inferencia

El proceso de inferencia de un esquema de <xref:System.Data.DataSet> a partir de XML puede dar como resultado esquemas diferentes, dependiendo de los elementos XML contenidos en cada documento. Por ejemplo, considere los siguientes documentos XML.  
  
 Document1:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 Para "Documento1", el proceso de inferencia produce un **DataSet** denominado "DocumentElement" y una tabla denominada "Element1", ya que "Element1" es un elemento que se repite.  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Sin embargo, para "Document2", el proceso de inferencia produce un **DataSet** denominado "NewDataSet" y una tabla denominada "DocumentElement". "Element1" se deduce como una columna porque no tiene atributos ni elementos secundarios.  
  
 **Conjunto** de los: NewDataSet  
  
 **Tabla:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Podría parecer que estos dos documentos XML producirían el mismo esquema, pero el proceso de inferencia genera resultados muy diferentes basándose en los elementos contenidos en cada documento.  
  
 Para evitar las discrepancias que pueden producirse al generar el esquema a partir de un documento XML, se recomienda especificar explícitamente un esquema mediante el lenguaje de definición de esquemas XML (XSD) o XML-Data reducido (XDR) al cargar un **DataSet** desde XML. Para obtener más información sobre cómo especificar explícitamente un esquema de **conjunto** de datos con un esquema XML, vea [derivar una estructura relacional de conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>Vea también

- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
