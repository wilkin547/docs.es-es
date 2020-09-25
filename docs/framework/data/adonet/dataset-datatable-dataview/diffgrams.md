---
title: Objetos DiffGram
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: aff9c2347fab51d853e19bd9dc16666c4ed549b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172806"
---
# <a name="diffgrams"></a>Objetos DiffGram

Un DiffGram es un formato XML que identifica las versiones actual y original de los elementos de datos. El <xref:System.Data.DataSet> utiliza el formato DiffGram para cargar y hacer persistente su contenido, así como para serializar su contenido con el fin de transportarlo a través de una conexión de red. Cuando un <xref:System.Data.DataSet> se escribe como un DiffGram, rellena el DiffGram con toda la información necesaria para volver a crear con precisión el contenido, aunque no el esquema de, incluidos los <xref:System.Data.DataSet> valores de columna de las versiones de fila **original** y **actual** , la información de error de fila y el orden de las filas.  
  
 Cuando se envía y recupera un <xref:System.Data.DataSet> desde un servicio Web XML, se utiliza implícitamente el formato DiffGram. Además, al cargar el contenido de un <xref:System.Data.DataSet> desde XML mediante el método **ReadXml** , o al escribir el contenido de un <xref:System.Data.DataSet> en XML mediante el método **WriteXml** , puede especificar que el contenido se lea o se escriba como un DiffGram. Para obtener más información, vea [cargar un DataSet desde XML](loading-a-dataset-from-xml.md) y escribir el contenido del conjunto de [datos como datos XML](writing-dataset-contents-as-xml-data.md).  
  
 Si bien .NET Framework utiliza principalmente el formato DiffGram como formato de serialización para el contenido de un <xref:System.Data.DataSet>, también es posible usar DiffGrams para modificar datos en tablas de una base de datos de Microsoft SQL Server.  
  
 Un DiffGram se genera escribiendo el contenido de todas las tablas en un **\<diffgram>** elemento.  
  
### <a name="to-generate-a-diffgram"></a>Para generar un Diffgram  
  
1. Genere una lista de tablas raíz (es decir, tablas sin elemento primario).  
  
2. Para cada tabla y sus descendientes en la lista, escriba la versión actual de todas las filas en la primera sección del Diffgram.  
  
3. Para cada tabla de <xref:System.Data.DataSet> , escriba la versión original de todas las filas, si hay alguna, en la **\<before>** sección del DiffGram.  
  
4. En el caso de las filas que tienen errores, escriba el contenido del error en la **\<errors>** sección del DiffGram.  
  
 El Diffgram se procesa en orden, del principio del archivo XML al final.  
  
### <a name="to-process-a-diffgram"></a>Para procesar un Diffgram  
  
1. Procese la primera sección del Diffgram, que contiene la versión actual de las filas.  
  
2. Procesa la segunda o la **\<before>** sección que contiene la versión de fila original de las filas modificadas y eliminadas.  
  
    > [!NOTE]
    > Si una fila está marcada como eliminada, la operación de eliminación puede suprimir también sus descendientes, dependiendo de la propiedad `Cascade` del actual <xref:System.Data.DataSet>.  
  
3. Procese la **\<errors>** sección. Establezca la información de error de la fila y la columna especificadas para cada elemento de esta sección.  
  
> [!NOTE]
> Si establece <xref:System.Data.XmlWriteMode> en Diffgram, el contenido del <xref:System.Data.DataSet> de destino y del <xref:System.Data.DataSet> original podría ser distinto.  
  
## <a name="diffgram-format"></a>Formato de un DiffGram  

 El formato de DiffGram está dividido en tres secciones: los datos actuales, los datos originales (o "antes de") y una sección de errores, como se muestra en el siguiente ejemplo.  
  
```xml  
<?xml version="1.0"?>  
<diffgr:diffgram
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 El formato DiffGram consta de los bloques de datos siguientes:  
  
 **\<**  ***DataInstance***  **>**  
 El nombre de este elemento, ***instanceof***, se utiliza con fines explicativos en esta documentación. Un elemento de ***instancia*** representa un <xref:System.Data.DataSet> o una fila de un <xref:System.Data.DataTable> . En lugar de una *instancia*de, el elemento contiene el nombre de <xref:System.Data.DataSet> o <xref:System.Data.DataTable> . Este bloque del formato DiffGram contiene los datos actuales, se hayan modificado o no. Un elemento, o fila, que se ha modificado se identifica con la anotación **diffgr: hasChanges** .  
  
 **\<diffgr:before>**  
 Este bloque del formato DiffGram contiene la versión original de una fila. Los elementos de este bloque coinciden con los elementos del bloque de ***instancia*** mediante la anotación **diffgr: ID** .  
  
 **\<diffgr:errors>**  
 Este bloque del formato DiffGram contiene información de error para una fila determinada en el bloque de ***instancia*** . Los elementos de este bloque coinciden con los elementos del bloque de ***instancia*** mediante la anotación **diffgr: ID** .  
  
## <a name="diffgram-annotations"></a>Anotaciones de DiffGram  

 Los DiffGrams utilizan varias anotaciones para relacionar elementos de los distintos bloques de DiffGram que representan versiones de fila o información de error diferentes en el <xref:System.Data.DataSet>.  
  
 En la tabla siguiente se describen las anotaciones de DiffGram que se definen en el espacio de nombres de DiffGram **urn: schemas-microsoft-com: XML-DiffGram-v1**.  
  
|Anotación|Descripción|  
|----------------|-----------------|  
|**id**|Se utiliza para emparejar los elementos de los **\<diffgr:before>** **\<diffgr:errors>** bloques y con los elementos del **\<** ***DataInstance*** **>** bloque. Los valores con la anotación **diffgr: ID** tienen el formato *[TableName] [identificadorfila]*. Por ejemplo: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Identifica qué elemento del **\<** ***DataInstance*** **>** bloque es el elemento primario del elemento actual. Los valores con la anotación **diffgr: parentId** tienen el formato *[NombreTabla] [identificadorfila]*. Por ejemplo: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifica una fila del **\<** ***DataInstance*** **>** bloque como modificada. La anotación **hasChanges** puede tener uno de los dos valores siguientes:<br /><br /> **insertar**<br /> Identifica una fila **agregada** .<br /><br /> **modificado**<br /> Identifica una fila **modificada** que contiene una versión de fila **original** en el **\<diffgr:before>** bloque. Tenga en cuenta que las filas **eliminadas** tendrán una versión de fila **original** en el **\<diffgr:before>** bloque, pero no habrá ningún elemento anotado en el **\<** ***DataInstance*** **>** bloque.|  
|**hasErrors**|Identifica una fila del **\<** ***DataInstance*** **>** bloque con un **RowError**. El elemento de error se coloca en el **\<diffgr:errors>** bloque.|  
|**Error**|Contiene el texto de **RowError** para un elemento determinado en el **\<diffgr:errors>** bloque.|  
  
 El <xref:System.Data.DataSet> incluye otras anotaciones al leer o escribir su contenido como un DiffGram. En la tabla siguiente se describen estas anotaciones adicionales, que se definen en el espacio de nombres **urn: schemas-microsoft-com: XML-msdata**.  
  
|Anotación|Descripción|  
|----------------|-----------------|  
|**RowOrder**|Conserva el orden de fila de los datos originales e identifica el índice de una fila de una <xref:System.Data.DataTable> determinada.|  
|**Oculto**|Identifica una columna con una propiedad **ColumnMapping** establecida en **MappingType. Hidden**. El atributo se escribe con el formato **msdata: Hidden** *[ColumnName]*= "*valor*". Por ejemplo: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Hay que tener en cuenta que las columnas ocultas solo se escriben como un atributo de DiffGram si contienen datos. En caso contrario, se pasan por alto.|  
  
## <a name="sample-diffgram"></a>DiffGram de ejemplo  

 A continuación se muestra un ejemplo del formato DiffGram. En este ejemplo se muestra el resultado de una actualización de una fila de una tabla antes de que se hayan confirmado los cambios. La fila cuyo CustomerID es "ALFKI" se ha modificado, pero no se ha actualizado. Como resultado, hay una fila **actual** con un **diffgr: ID** de "customers1" en el **\<** ***DataInstance*** **>** bloque y una fila **original** con un **diffgr: ID** de "customers1" en el **\<diffgr:before>** bloque. La fila con el CustomerID "ANATR" incluye **RowError**, por lo que se anota con `diffgr:hasErrors="true"` y hay un elemento relacionado en el **\<diffgr:errors>** bloque.  
  
```xml  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## <a name="see-also"></a>Vea también

- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Escribir el contenido de un conjunto de datos como datos XML](writing-dataset-contents-as-xml-data.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
