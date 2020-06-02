---
title: Información general
description: Lea una introducción a ADO.NET en .NET Framework y obtenga información sobre los recursos para obtener explicaciones y ejemplos más detallados.
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: 2ff3b7ad197bfe1e1c12e382f3a59bd470c57a75
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287160"
---
# <a name="adonet-overview"></a>Información general sobre ADO.NET
ADO.NET proporciona acceso coherente a orígenes de datos como SQL Server y XML, así como a orígenes de datos expuestos mediante OLE DB y ODBC. Las aplicaciones de consumidor que comparten datos pueden utilizar ADO.NET para conectar a estos orígenes de datos y recuperar, controlar y actualizar los datos contenidos.  
  
 ADO.NET separa el acceso a datos de la manipulación de datos y crea componentes discretos que se pueden utilizar por separado o conjuntamente. ADO.NET incluye proveedores de datos .NET Framework para conectarse a una base de datos, ejecutar comandos y recuperar resultados. Los resultados se procesan directamente o se colocan en un objeto <xref:System.Data.DataSet> de ADO.NET con el fin de exponerlos al usuario para un propósito específico, combinados con datos de varios orígenes, o de pasarlos entre niveles. El objeto `DataSet` de ADO.NET también puede utilizarse independientemente de un proveedor de datos .NET Framework para administrar datos que son locales de la aplicación o que proceden de un origen XML.  
  
 Las clases de ADO.NET se encuentran en System.Data.dll y se integran con las clases de XML incluidas en System.Xml.dll. Para ver el código de ejemplo que se conecta a una base de datos, recupera datos de la misma y, a continuación, muestra esos datos en una ventana de la consola, consulte [ejemplos de código ADO.net](ado-net-code-examples.md).  
  
 ADO.NET proporciona funcionalidad a los desarrolladores que escriben código administrado similar a la funcionalidad que los objetos ADO (ActiveX Data Objects) proporcionan a los desarrolladores de modelo de objetos componentes (COM) nativo. Se recomienda utilizar ADO.NET, y no ADO, para obtener acceso a datos de aplicaciones .NET.  
  
 ADO.NET proporciona el método más directo de acceso a datos de .NET Framework. Para obtener una abstracción de nivel superior que permita que las aplicaciones funcionen con un modelo conceptual en lugar del modelo de almacenamiento subyacente, vea el [Entity Framework ADO.net](./ef/index.md).  
  
 **Declaración de privacidad**: los ensamblados System. Data. dll, System. Data. Design. dll, System. Data. OracleClient. dll, System. Data. SqlXml. dll, System. Data. Linq. dll, System. Data. SqlServerCe. dll y System. Data. DataSetExtensions. dll no distinguen entre los datos privados de un usuario y los datos no privados.  Estos ensamblados no recopilan, almacenan o transportan datos privados del usuario. No obstante, las aplicaciones de terceros podrían recopilar, almacenar o transportar datos privados de usuario valiéndose de dichos ensamblados.  
  
## <a name="in-this-section"></a>En esta sección  
 [Arquitectura de ADO.NET](ado-net-architecture.md)  
 Proporciona información general sobre la arquitectura y los componentes de ADO.NET.  
  
 [Directrices y opciones de tecnología de ADO.NET](ado-net-technology-options-and-guidelines.md)  
 Describe los productos y tecnologías incluidos con la plataforma de datos de entidad.  
  
 [LINQ y ADO.NET](linq-and-ado-net.md)  
 Describe cómo se implementa Language-Integrated Query (LINQ) en ADO.NET y proporciona vínculos a los temas pertinentes.  
  
 [Proveedores de datos .NET Framework](data-providers.md)  
 Proporciona información general acerca del diseño del proveedor de datos .NET Framework y de los proveedores de datos .NET Framework incluidos en ADO.NET.  
  
 [Objetos DataSet de ADO.NET](ado-net-datasets.md)  
 Proporciona información general acerca del diseño y los componentes de `DataSet`.  
  
 [Ejecución en paralelo en ADO.NET](side-by-side-execution.md)  
 Analiza las diferencias que existen entre las distintas versiones de ADO.NET y cómo afectan a la ejecución en paralelo y a la compatibilidad entre aplicaciones.  
  
 [Ejemplos de código de ADO.NET](ado-net-code-examples.md)  
 Proporciona ejemplos de código que recuperan datos mediante proveedores de datos de ADO.NET.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Novedades de ADO.NET](whats-new.md)  
 Presenta características nuevas en ADO.NET.  
  
 [Proteger aplicaciones de ADO.NET](securing-ado-net-applications.md)  
 Describe algunas recomendaciones de codificación segura para utilizar ADO.NET.  
  
 [Asignaciones de tipos de datos en ADO.NET](data-type-mappings-in-ado-net.md)  
 Describe las asignaciones de tipos de datos entre los tipos de datos de .NET Framework y los proveedores de datos .NET Framework.  
  
 [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)  
 Describe cómo conectarse a un origen de datos, y cómo recuperar y modificar datos. Incluye `DataReaders` y `DataAdapters`.  
  
## <a name="see-also"></a>Consulte también

- [ADO.NET](index.md)
- [Obtener acceso a datos en Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
