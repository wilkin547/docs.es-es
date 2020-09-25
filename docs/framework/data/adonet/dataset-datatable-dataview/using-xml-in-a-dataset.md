---
title: Usar XML en un conjunto de datos
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: e133da727887271af3bc5330a5779df4af58a37e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201192"
---
# <a name="using-xml-in-a-dataset"></a>Usar XML en un conjunto de datos

Con ADO.NET es posible llenar un <xref:System.Data.DataSet> a partir de una secuencia o un documento XML. Se puede utilizar la secuencia o el documento XML para suministrar datos al <xref:System.Data.DataSet>, información de esquema o ambas cosas. La información suministrada desde la secuencia o el documento XML puede combinarse con datos o información de esquema existente ya presente en el <xref:System.Data.DataSet>.  
  
 ADO.NET también permite crear una representación XML de un <xref:System.Data.DataSet>, con o sin su esquema, para transportar el <xref:System.Data.DataSet> a través de HTTP con el fin de que lo utilice otra aplicación u otra plataforma compatible con XML. En una representación XML de un <xref:System.Data.DataSet>, los datos se escriben en XML y el esquema, si está incluido alineado en la representación, se escribe utilizando el lenguaje de definición de esquemas XML (XSD). XML y el esquema XML proporcionan un formato cómodo para transferir el contenido de un <xref:System.Data.DataSet> a y desde clientes remotos.  
  
## <a name="in-this-section"></a>En esta sección  

 [Objetos DiffGram](diffgrams.md)  
 Proporciona detalles acerca de DiffGram, un formato XML utilizado para leer y escribir el contenido de un <xref:System.Data.DataSet>.  
  
 [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)  
 Describe las distintas opciones que hay que tener en cuenta al cargar el contenido de un <xref:System.Data.DataSet> desde un documento XML.  
  
 [Escribir el contenido de un conjunto de datos como datos XML](writing-dataset-contents-as-xml-data.md)  
 Describe cómo generar el contenido de un <xref:System.Data.DataSet> como datos XML y las distintas opciones de formato XML que se pueden utilizar.  
  
 [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)  
 Describe los métodos <xref:System.Data.DataSet> utilizados para cargar el esquema de un <xref:System.Data.DataSet> desde XML.  
  
 [Escribir información del esquema de un conjunto de datos como XSD](writing-dataset-schema-information-as-xsd.md)  
 Describe los usos de un esquema XML y cómo generar uno a partir de un <xref:System.Data.DataSet>.  
  
 [Sincronización de DataSet y XmlDataDocument](dataset-and-xmldatadocument-synchronization.md)  
 Describe la posibilidad existente en .NET Framework de tener acceso sincrónicamente a las vistas relacional y jerárquica de un único conjunto de datos, a la vez que muestra cómo crear una relación sincrónica entre un <xref:System.Data.DataSet> y un <xref:System.Xml.XmlDataDocument>.  
  
 [Anidar objetos DataRelation](nesting-datarelations.md)  
 Explica la importancia de los objetos <xref:System.Data.DataRelation> anidados al representar el contenido de un <xref:System.Data.DataSet> como datos XML y describe cómo crearlos.  
  
 [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un <xref:System.Data.DataSet> creado a partir de un esquema XML.  
  
 [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)  
 Describe la estructura relacional, o esquema, resultante de un <xref:System.Data.DataSet> que se crea por inferencia a partir de elementos XML.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Información general de ADO.NET](../ado-net-overview.md)  
 Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y administrar los datos de aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
