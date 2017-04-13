---
title: "DiffGrams | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DiffGrams
Un DiffGram es un formato XML que identifica las versiones actual y original de los elementos de datos.  El <xref:System.Data.DataSet> utiliza el formato DiffGram para cargar y hacer persistente su contenido, así como para serializar su contenido con el fin de transportarlo a través de una conexión de red.  Cuando un <xref:System.Data.DataSet> se escribe como un DiffGram, llena el DiffGram con toda la información necesaria para volver a crear de forma precisa el contenido, aunque no el esquema del <xref:System.Data.DataSet>, incluyendo los valores de columna de las versiones de fila **Original** y **Current**, la información de error de fila y el orden de las filas.  
  
 Cuando se envía y recupera un <xref:System.Data.DataSet> desde un servicio Web XML, se utiliza implícitamente el formato DiffGram.  Además, al cargar el contenido de un <xref:System.Data.DataSet> desde XML mediante el método **ReadXml**, o al escribir el contenido de un <xref:System.Data.DataSet> en XML mediante el método **WriteXml**, se puede especificar que el contenido se lea o se escriba como un DiffGram.  Para obtener más información, vea [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) y [Escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Si bien .NET Framework utiliza principalmente el formato DiffGram como formato de serialización para el contenido de un <xref:System.Data.DataSet>, también es posible usar DiffGrams para modificar datos en tablas de una base de datos de Microsoft SQL Server.  
  
 Los Diffgram se generan escribiendo el contenido de todas las tablas en un elemento **\<diffgram\>**.  
  
### Para generar un Diffgram  
  
1.  Genere una lista de tablas raíz \(es decir, tablas sin elemento primario\).  
  
2.  Para cada tabla y sus descendientes en la lista, escriba la versión actual de todas las filas en la primera sección del Diffgram.  
  
3.  Para cada tabla de <xref:System.Data.DataSet>, escriba la versión original de todas las filas, si hay alguna, en la sección **\<before\>** del Diffgram.  
  
4.  Para todas las filas que tengan errores, escriba el contenido del error en la sección **\<errors\>** del Diffgram.  
  
 El Diffgram se procesa en orden, del principio del archivo XML al final.  
  
### Para procesar un Diffgram  
  
1.  Procese la primera sección del Diffgram, que contiene la versión actual de las filas.  
  
2.  Procese la segunda sección o la sección **\<before\>** que contiene la versión original de las filas modificadas y eliminadas.  
  
    > [!NOTE]
    >  Si una fila está marcada como eliminada, la operación de eliminación puede suprimir también sus descendientes, dependiendo de la propiedad `Cascade` del actual <xref:System.Data.DataSet>.  
  
3.  Procese la sección **\<errors\>**.  Establezca la información de error de la fila y la columna especificadas para cada elemento de esta sección.  
  
> [!NOTE]
>  Si establece <xref:System.Data.XmlWriteMode> en Diffgram, el contenido del <xref:System.Data.DataSet> de destino y del <xref:System.Data.DataSet> original podría ser distinto.  
  
## Formato DiffGram  
 El formato de DiffGram está dividido en tres secciones: los datos actuales, los datos originales \(o "antes de"\) y una sección de errores, como se muestra en el siguiente ejemplo.  
  
```  
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
  
 **\<**  ***DataInstance***  **\>**  
 El nombre de este elemento, ***DataInstance***, se utiliza con fines explicativos en esta documentación.  Un elemento ***DataInstance*** representa un <xref:System.Data.DataSet> o una fila de una <xref:System.Data.DataTable>.  En lugar de *DataInstance*, el elemento contendría el nombre del <xref:System.Data.DataSet> o de la <xref:System.Data.DataTable>.  Este bloque del formato DiffGram contiene los datos actuales, se hayan modificado o no.  Un elemento, o fila, que se haya modificado se identifica con la anotación **diffgr:hasChanges**.  
  
 **\<diffgr:before\>**  
 Este bloque del formato DiffGram contiene la versión original de una fila.  Los elementos de este bloque se hacen coincidir con los del bloque ***DataInstance*** mediante la anotación **diffgr:id**.  
  
 **\<diffgr:errors\>**  
 Este bloque del formato DiffGram contiene información de error para una fila determinada del bloque ***DataInstance***.  Los elementos de este bloque se hacen coincidir con los del bloque ***DataInstance*** mediante la anotación **diffgr:id**.  
  
## Anotaciones de DiffGram  
 Los DiffGrams utilizan varias anotaciones para relacionar elementos de los distintos bloques de DiffGram que representan versiones de fila o información de error diferentes en el <xref:System.Data.DataSet>.  
  
 En la siguiente tabla se describen las anotaciones de DiffGram definidas en el espacio de nombres **urn:schemas\-microsoft\-com:xml\-diffgram\-v1** de DiffGram.  
  
|Anotación|Descripción|  
|---------------|-----------------|  
|**id**|Se utiliza para emparejar los elementos de los bloques **\<diffgr:before\>** y **\<diffgr:errors\>** con elementos del bloque **\<** ***DataInstance*** **\>**.  Los valores que tienen la anotación **diffgr:id** tienen el formato *\[NombreTabla\]\[IdentificadorFila\]*.  Por ejemplo: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Identifica qué elemento del bloque **\<** ***DataInstance*** **\>** es el elemento principal del elemento actual.  Los valores que tienen la anotación **diffgr:parentId** tienen el formato *\[NombreTabla\]\[IdentificadorFila\]*.  Por ejemplo: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Identifica una fila en el bloque **\<** ***DataInstance*** **\>** como modificada.  La anotación **hasChanges** puede tener uno de los dos valores siguientes:<br /><br /> **inserted**<br /> Identifica una fila agregada \(**Added**\).<br /><br /> **modified**<br /> Identifica una fila modificada **Modified** que contiene una versión de fila **Original** en el bloque **\<diffgr:before\>**.  Hay que tener en cuenta que las filas **Deleted** tendrán una versión de fila **Original** en el bloque **\<diffgr:before\>**, pero no habrá ningún elemento anotado en el bloque **\<** ***DataInstance*** **\>**.|  
|**hasErrors**|Identifica una fila del bloque **\<** ***DataInstance*** **\>** como que tiene un error**RowError**.  El elemento erróneo se sitúa en el bloque **\<diffgr:errors\>**.|  
|**Error**|Contiene el texto de **RowError** para un elemento determinado en el bloque **\<diffgr:errors\>**.|  
  
 El <xref:System.Data.DataSet> incluye otras anotaciones al leer o escribir su contenido como un DiffGram.  En la siguiente tabla se describen estas anotaciones adicionales, que se definen en el espacio de nombres **urn:schemas\-microsoft\-com:xml\-msdata**.  
  
|Anotación|Descripción|  
|---------------|-----------------|  
|**RowOrder**|Conserva el orden de fila de los datos originales e identifica el índice de una fila de una <xref:System.Data.DataTable> determinada.|  
|**Hidden**|Identifica una columna que tiene el valor **MappingType.Hidden** en la propiedad **ColumnMapping**.  El atributo se escribe con el formato **msdata:hidden** *\[NombreColumna\]*\="*valor*".  Por ejemplo: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Hay que tener en cuenta que las columnas ocultas solo se escriben como un atributo de DiffGram si contienen datos.  De lo contrario, se pasan por alto.|  
  
## DiffGram de ejemplo  
 A continuación se muestra un ejemplo del formato DiffGram.  En este ejemplo se muestra el resultado de una actualización de una fila de una tabla antes de que se hayan confirmado los cambios.  La fila cuyo CustomerID es "ALFKI" se ha modificado, pero no se ha actualizado.  Como resultado, hay una fila **Current** con un valor **diffgr:id** de "Customers1" en el bloque **\<** ***DataInstance*** **\>** y una fila **Original** con un valor **diffgr:id** de "Customers1" en el bloque **\<diffgr:before\>**.  La fila cuyo valor de CustomerID es "ANATR" incluye un **RowError**, por lo que se anota con `diffgr:hasErrors="true"` y hay un elemento relacionado en el bloque **\<diffgr:errors\>**.  
  
```  
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
  
## Vea también  
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)