---
title: "Integración de XML con datos relacionales y ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6ebb1a1-f2ca-49b9-92c9-0150940cf6e6
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5d03a0ca7518b06c08d98967d7c5ae864f1c04ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xml-integration-with-relational-data-and-adonet"></a>Integración de XML con datos relacionales y ADO.NET
El **XmlDataDocument** es una clase derivada de la **XmlDocument**y contiene datos XML. La ventaja de la **XmlDataDocument** es que proporciona un puente entre los datos relacionales y jerárquicos. Es un **XmlDocument** que se puede enlazar a un **conjunto de datos** y ambas clases pueden sincronizar los cambios realizados en los datos incluidos en las dos clases. Un **XmlDocument** que está enlazado a un **conjunto de datos** permite a XML integrarse con datos relacionales y no es necesario que los datos estén representados ni XML ni en un formato relacional. Se pueden hacer ambas cosas sin necesidad de restringirse a una única representación de los datos.  
  
 Las ventajas de tener los datos disponibles en dos vistas son las siguientes:  
  
-   La parte estructurada de un documento XML puede asignarse a un conjunto de datos y ser almacenada, indizada y buscada de forma eficaz.  
  
-   Las transformaciones, validación y navegación en los datos XML que están almacenados de forma relacional se pueden realizar eficazmente mediante un modelo de cursor. En ocasiones, puede hacerse más eficaz en estructuras relacionales que si el código XML se almacena en un **XmlDocument** modelo.  
  
-   El **conjunto de datos** puede almacenar una parte del código XML. Es decir, se puede usar **XPath** o **XslTransform** para almacenar una **conjunto de datos** sólo aquellos elementos y atributos de interés. Desde allí, pueden realizarse cambios en el subconjunto más pequeño y filtrado de datos, con los cambios se propaguen a los datos más grandes en el **XmlDataDocument**.  
  
 También puede ejecutar una transformación sobre los datos que se cargaron en el **conjunto de datos** de SQL Server. Otra opción consiste en enlazar WinForm de estilo de las clases administradas de .NET Framework y controles de formulario Web Forms a un **conjunto de datos** que se haya llenado de un flujo de entrada XML.  
  
 Además de admitir **XslTransform**, **XmlDataDocument** expone los datos relacionales a **XPath** consultas y validación.  Básicamente, todos los servicios XML están disponibles en los datos relacionales; las funciones relacionales, como el enlace de controles, codegen, etc., están disponibles en una proyección estructurada de XML sin comprometer la fidelidad con el lenguaje XML.  
  
 Dado que **XmlDataDocument** se hereda de un **XmlDocument**, proporciona una implementación de DOM del W3C. El hecho de que el **XmlDataDocument** está asociado y almacena un subconjunto de sus datos de un **conjunto de datos** no restringe o altera en absoluto su uso como un **XmlDocument** de ninguna manera. Código escrito para consumir un **XmlDocument** funciona sin alteraciones en un **XmlDataDocument**. El **conjunto de datos** proporciona la vista relacional de los mismos datos definiendo tablas, columnas, relaciones y restricciones, y constituye un almacén de datos de usuario independiente y en memoria.  
  
 La ilustración siguiente se muestra las distintas asociaciones que los datos XML tienen con el **conjunto de datos** y **XmlDataDocument**.  
  
 ![Conjunto de datos XML](../../../../docs/standard/data/xml/media/xmlintegrationwithrelationaldataandadodotnet.gif "xmlIntegrationWithRelationalDataAndADOdotNet")  
  
 La ilustración muestra que los datos XML pueden cargarse directamente en un **conjunto de datos**, lo que permite la manipulación directa con XML en la forma relacional. O bien, el XML se puede cargar en una clase derivada de DOM, que es el **XmlDataDocument**y posteriormente cargarlo y sincronizarlo con el **conjunto de datos**. Dado que la **conjunto de datos** y **XmlDataDocument** están sincronizados sobre un único conjunto de datos, los cambios realizados en los datos en un almacén se reflejan automáticamente en el otro almacén.  
  
 El **XmlDataDocument** hereda todas las características de edición y navegación de la **XmlDocument**. Hay veces cuando se usa el **XmlDataDocument** y sus características heredadas, sincronizadas con un **conjunto de datos**, es una opción más apropiada que cargar código XML directamente en el **delconjuntodedatos**. La siguiente tabla muestra los elementos que se va a tener en cuenta al elegir qué método usar para cargar la **conjunto de datos**.  
  
|Cuándo cargar XML directamente en un DataSet|Cuándo sincronizar un XmlDataDocument con un DataSet|  
|----------------------------------------------|-----------------------------------------------------------|  
|Las consultas de datos en el **conjunto de datos** son más fáciles usando SQL que XPath.|Se necesitan consultas XPath sobre datos de la **conjunto de datos**.|  
|Preservar el orden de los elementos en el código fuente XML no es vital.|Preservar el orden de los elementos en el código fuente XML resulta vital.|  
|No es necesario preservar el espacio en blanco entre los elementos ni el formato del código fuente XML.|Preservar el espacio y formato del código fuente XML resulta vital.|  
  
 Si cargar y escribir XML directamente dentro y fuera de un **conjunto de datos** cubre sus necesidades, vea [cargar DataSet desde XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) y [escribir un objeto DataSet como datos XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Si carga el **conjunto de datos** desde una **XmlDataDocument** cubre sus necesidades, vea [sincronizar un DataSet con un documento XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md).  
  
## <a name="see-also"></a>Vea también  
 [Usar XML en un conjunto de datos](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
