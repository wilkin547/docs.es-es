---
title: Información general sobre ADO.NET
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: 50881c05c8b6f2602d19817373a16e4661d3d133
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="adonet-overview"></a>Información general sobre ADO.NET
ADO.NET proporciona acceso coherente a orígenes de datos como SQL Server y XML, así como a orígenes de datos expuestos mediante OLE DB y ODBC. Las aplicaciones de consumidor que comparten datos pueden utilizar ADO.NET para conectar a estos orígenes de datos y recuperar, controlar y actualizar los datos contenidos.  
  
 ADO.NET separa el acceso a datos de la manipulación de datos y crea componentes discretos que se pueden utilizar por separado o conjuntamente. ADO.NET incluye proveedores de datos .NET Framework para conectarse a una base de datos, ejecutar comandos y recuperar resultados. Los resultados se procesan directamente o se colocan en un objeto <xref:System.Data.DataSet> de ADO.NET con el fin de exponerlos al usuario para un propósito específico, combinados con datos de varios orígenes, o de pasarlos entre niveles. El objeto `DataSet` de ADO.NET también puede utilizarse independientemente de un proveedor de datos .NET Framework para administrar datos que son locales de la aplicación o que proceden de un origen XML.  
  
 Las clases de ADO.NET se encuentran en System.Data.dll y se integran con las clases de XML incluidas en System.Xml.dll. Para código de ejemplo que se conecta a una base de datos, recupera datos de ésta y, a continuación, se muestra que los datos en una ventana de consola, consulte [ejemplos de código de ADO.NET](../../../../docs/framework/data/adonet/ado-net-code-examples.md).  
  
 ADO.NET proporciona funcionalidad a los desarrolladores que escriben código administrado similar a la funcionalidad que los objetos ADO (ActiveX Data Objects) proporcionan a los desarrolladores de modelo de objetos componentes (COM) nativo. Se recomienda utilizar ADO.NET, y no ADO, para obtener acceso a datos de aplicaciones .NET.  
  
 ADO.NET proporciona el método más directo de acceso a datos de .NET Framework. Para una abstracción de alto nivel que permite a las aplicaciones para que funcione en un modelo conceptual en lugar del modelo de almacenamiento subyacente, consulte el [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  
  
 **Declaración de privacidad**: ensamblados el System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll y System.Data.DataSetExtensions.dll no distinguir entre los datos privados y no privados de un usuario.  Estos ensamblados no recopilan, almacenan o transportan datos privados del usuario. No obstante, las aplicaciones de terceros podrían recopilar, almacenar o transportar datos privados de usuario valiéndose de dichos ensamblados.  
  
## <a name="in-this-section"></a>En esta sección  
 [Arquitectura de ADO.NET](../../../../docs/framework/data/adonet/ado-net-architecture.md)  
 Proporciona información general sobre la arquitectura y los componentes de ADO.NET.  
  
 [Directrices y opciones de tecnología de ADO.NET](../../../../docs/framework/data/adonet/ado-net-technology-options-and-guidelines.md)  
 Describe los productos y tecnologías incluidos con la plataforma de datos de entidad.  
  
 [LINQ y ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 Describe cómo se implementa Language-Integrated Query (LINQ) en ADO.NET y proporciona vínculos a los temas pertinentes.  
  
 [Proveedores de datos .NET Framework](../../../../docs/framework/data/adonet/data-providers.md)  
 Proporciona información general acerca del diseño del proveedor de datos .NET Framework y de los proveedores de datos .NET Framework incluidos en ADO.NET.  
  
 [Objetos DataSet de ADO.NET](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 Proporciona información general acerca del diseño y los componentes de `DataSet`.  
  
 [Ejecución en paralelo en ADO.NET](../../../../docs/framework/data/adonet/side-by-side-execution.md)  
 Analiza las diferencias que existen entre las distintas versiones de ADO.NET y cómo afectan a la ejecución en paralelo y a la compatibilidad entre aplicaciones.  
  
 [Ejemplos de código de ADO.NET](../../../../docs/framework/data/adonet/ado-net-code-examples.md)  
 Proporciona ejemplos de código que recuperan datos mediante proveedores de datos de ADO.NET.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Novedades de ADO.NET](../../../../docs/framework/data/adonet/whats-new.md)  
 Presenta características nuevas en [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
 [Proteger aplicaciones de ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Describe algunas recomendaciones de codificación segura para utilizar ADO.NET.  
  
 [Asignaciones de tipos de datos en ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 Describe las asignaciones de tipos de datos entre los tipos de datos de .NET Framework y los proveedores de datos .NET Framework.  
  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Describe cómo conectarse a un origen de datos, y cómo recuperar y modificar datos. Incluye `DataReaders` y `DataAdapters`.  
  
## <a name="see-also"></a>Vea también  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [Obtener acceso a los datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
