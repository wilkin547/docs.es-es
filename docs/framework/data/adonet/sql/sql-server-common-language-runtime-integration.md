---
title: "Integración con Common Language Runtime de SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: de415a6282b1d27d803d448bd3225355c08e011b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-common-language-runtime-integration"></a>Integración con Common Language Runtime de SQL Server
SQL Server 2005 introdujo la integración del componente Common Language Runtime (CLR) de .NET Framework para Microsoft Windows. Esto significa que ahora se pueden escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de transmisión por secuencias mediante cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET y Microsoft Visual C#. El espacio de nombres <xref:Microsoft.SqlServer.Server> contiene un conjunto de nuevas interfaces de programación de aplicaciones (API) que permiten que el código administrado interactúe con el entorno de Microsoft SQL Server.  
  
 En esta sección se describen las características y comportamientos que son específicos de la integración Common Language Runtime (CLR) de SQL Server, así como las extensiones específicas en proceso de SQL Server a ADO.NET.  
  
 El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión. Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
1.  [Conceptos de programación integración de Common Language Runtime (CLR)](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a>En esta sección  
 [Introducción a la integración con CLR de SQL Server](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Proporciona una introducción a la integración CLR de SQL Server. También proporciona vínculos a temas adicionales.  
  
 [Funciones definidas por el usuario de CLR](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Describe cómo implementar y utilizar los diferentes tipos de funciones CLR: con valores de tabla, escalares y funciones de agregado definidas por el usuario.  
  
 [Tipos CLR definidos por el usuario](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Describe cómo implementar y utilizar tipos definidos por el usuario CLR. También proporciona vínculos a temas adicionales.  
  
 [Procedimientos almacenados de CLR](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Describe cómo implementar y utilizar procedimientos almacenados CLR. También proporciona vínculos a temas adicionales.  
  
 [Desencadenadores de CLR](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Describe cómo implementar y utilizar desencadenadores CLR. También proporciona vínculos a temas adicionales.  
  
 [Conexión del contexto](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Describe la conexión de contexto.  
  
 [Comportamiento específico en proceso de SQL Server en ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Describe las extensiones específicas en proceso de SQL Server a ADO.NET, y la conexión de contexto. También proporciona vínculos a temas adicionales.  
  
## <a name="see-also"></a>Vea también  
 [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Crear objetos de SQL Server 2005 en código administrado](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
