---
title: Objetos DiffGram
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 573da0b608b3f74b9cf789a27a10183f3320f908
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513664"
---
# <a name="diffgrams"></a>Objetos DiffGram
Un DiffGram es un formato XML que identifica las versiones actual y original de los elementos de datos. El <xref:System.Data.DataSet> utiliza el formato DiffGram para cargar y hacer persistente su contenido, así como para serializar su contenido con el fin de transportarlo a través de una conexión de red. Cuando un <xref:System.Data.DataSet> se escribe como un DiffGram, llena el DiffGram con toda la información necesaria para con precisión volver a crear el contenido, aunque no el esquema de la <xref:System.Data.DataSet>, incluyendo los valores de columna de ambos el **Original** y **actual** versiones de fila, información de error de fila y el orden de fila.  
  
 Cuando se envía y recupera un <xref:System.Data.DataSet> desde un servicio Web XML, se utiliza implícitamente el formato DiffGram. Además, al cargar el contenido de un <xref:System.Data.DataSet> desde XML mediante el **ReadXml** método, o al escribir el contenido de un <xref:System.Data.DataSet> en XML mediante el **WriteXml** método, puede especificar que el contenido se lee o escribe como un DiffGram. Para obtener más información, consulte [cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) y [escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Si bien .NET Framework utiliza principalmente el formato DiffGram como formato de serialización para el contenido de un <xref:System.Data.DataSet>, también es posible usar DiffGrams para modificar datos en tablas de una base de datos de Microsoft SQL Server.  
  
 Un Diffgram se genera escribiendo el contenido de todas las tablas de un  **\<diffgram >** elemento.  
  
### <a name="to-generate-a-diffgram"></a>Para generar un Diffgram  
  
1.  Genere una lista de tablas raíz (es decir, tablas sin elemento primario).  
  
2.  Para cada tabla y sus descendientes en la lista, escriba la versión actual de todas las filas en la primera sección del Diffgram.  
  
3.  Para cada tabla en la <xref:System.Data.DataSet>, escriba la versión original de todas las filas, si hay alguna, en el  **\<antes >** sección del Diffgram.  
  
4.  Para las filas con errores, escriba el contenido del error en la  **\<errores >** sección del Diffgram.  
  
 El Diffgram se procesa en orden, del principio del archivo XML al final.  
  
### <a name="to-process-a-diffgram"></a>Para procesar un Diffgram  
  
1.  Procese la primera sección del Diffgram, que contiene la versión actual de las filas.  
  
2.  Procese la segunda o  **\<antes >** sección que contiene la versión original de modificar y las filas eliminadas.  
  
    > [!NOTE]
    >  Si una fila está marcada como eliminada, la operación de eliminación puede suprimir también sus descendientes, dependiendo de la propiedad `Cascade` del actual <xref:System.Data.DataSet>.  
  
3.  Proceso del  **\<errores >** sección. Establezca la información de error de la fila y la columna especificadas para cada elemento de esta sección.  
  
> [!NOTE]
>  Si establece <xref:System.Data.XmlWriteMode> en Diffgram, el contenido del <xref:System.Data.DataSet> de destino y del <xref:System.Data.DataSet> original podría ser distinto.  
  
## <a name="diffgram-format"></a>Formato DiffGram  
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
 El nombre de este elemento, ***DataInstance***, se utiliza con fines explicativos en esta documentación. Un ***DataInstance*** elemento representa un <xref:System.Data.DataSet> o una fila de un <xref:System.Data.DataTable>. En lugar de *DataInstance*, el elemento contendría el nombre de la <xref:System.Data.DataSet> o <xref:System.Data.DataTable>. Este bloque del formato DiffGram contiene los datos actuales, se hayan modificado o no. Un elemento o fila, que se ha modificado se identifica con el **diffgr: HasChanges** anotación.  
  
 **\<diffgr:before>**  
 Este bloque del formato DiffGram contiene la versión original de una fila. En este bloque se hacen coincidir con los elementos de la ***DataInstance*** bloquear mediante la **diffgr: ID** anotación.  
  
 **\<diffgr:errors>**  
 Este bloque del formato DiffGram contiene información de error para una fila determinada en el ***DataInstance*** bloque. En este bloque se hacen coincidir con los elementos de la ***DataInstance*** bloquear mediante la **diffgr: ID** anotación.  
  
## <a name="diffgram-annotations"></a>Anotaciones de DiffGram  
 Los DiffGrams utilizan varias anotaciones para relacionar elementos de los distintos bloques de DiffGram que representan versiones de fila o información de error diferentes en el <xref:System.Data.DataSet>.  
  
 La tabla siguiente describen las anotaciones de DiffGram definidas en el espacio de nombres de DiffGram **urn: schemas-microsoft-com-diffgram-v1**.  
  
|Anotación|Descripción|  
|----------------|-----------------|  
|**identificador**|Se utiliza para emparejar los elementos de la  **\<diffgr: antes de >** y  **\<diffgr: errors >** bloques a los elementos de la **\<** ***DataInstance*** **>** bloque. Los valores con el **diffgr: ID** anotación tienen el formato *[NombreTabla] [IdentificadorFila]*. Por ejemplo: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Identifica qué elemento de la **\<** ***DataInstance*** **>** bloque es el elemento primario del elemento actual. Los valores con el **diffgr: parentId** anotación tienen el formato *[NombreTabla] [IdentificadorFila]*. Por ejemplo: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifica una fila en la **\<** ***DataInstance*** **>** bloquear como modificada. El **hasChanges** anotación puede tener uno de los dos valores siguientes:<br /><br /> **inserted**<br /> Identifica un **Added** fila.<br /><br /> **modified**<br /> Identifica un **Modified** fila que contiene un **Original** versión de fila en la  **\<diffgr: antes de >** bloque. Tenga en cuenta que **Deleted** las filas tendrán un **Original** versión de fila en la  **\<diffgr: antes de >** bloque, pero habrá ningún elemento anotado en el **\<** ***DataInstance*** **>** bloque.|  
|**hasErrors**|Identifica una fila en la **\<** ***DataInstance*** **>** bloque con un **RowError**. El elemento erróneo se sitúa en el  **\<diffgr: errors >** bloque.|  
|**Error**|Contiene el texto de la **RowError** para un elemento determinado en el  **\<diffgr: errors >** bloque.|  
  
 El <xref:System.Data.DataSet> incluye otras anotaciones al leer o escribir su contenido como un DiffGram. La tabla siguiente describen estas anotaciones adicionales, que se definen en el espacio de nombres **urn: schemas-microsoft-com-msdata**.  
  
|Anotación|Descripción|  
|----------------|-----------------|  
|**RowOrder**|Conserva el orden de fila de los datos originales e identifica el índice de una fila de una <xref:System.Data.DataTable> determinada.|  
|**Hidden**|Identifica una columna como si tuviera un **ColumnMapping** propiedad establecida en **MappingType.Hidden**. El atributo se escribe en el formato **msdata: hidden** *[ColumnName]*= "*valor*". Por ejemplo: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Hay que tener en cuenta que las columnas ocultas solo se escriben como un atributo de DiffGram si contienen datos. De lo contrario, se pasan por alto.|  
  
## <a name="sample-diffgram"></a>DiffGram de ejemplo  
 A continuación se muestra un ejemplo del formato DiffGram. En este ejemplo se muestra el resultado de una actualización de una fila de una tabla antes de que se hayan confirmado los cambios. La fila cuyo CustomerID es "ALFKI" se ha modificado, pero no se ha actualizado. Como resultado, hay un **actual** de fila con un **diffgr: ID** de "Customers1" en el **\<** ***DataInstance*** **>** bloque y un **Original** de fila con un **diffgr: ID** de "Customers1" en el  **\<diffgr: antes de >** bloque. La fila cuyo CustomerID es "ANATR" incluye un **RowError**, por lo que se anota con `diffgr:hasErrors="true"` y hay un elemento relacionado en el  **\<diffgr: errors >** bloque.  
  
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
- [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Carga de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Escritura de contenido de un conjunto de datos como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
