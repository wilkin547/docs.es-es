---
description: 'Más información acerca de: SQL Server la integración con Common Language Runtime'
title: Integración con Common Language Runtime de SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 096bba0d183526ec8e5d272c5ea6a77ad0778e5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767406"
---
# <a name="sql-server-common-language-runtime-integration"></a>Integración con Common Language Runtime de SQL Server

SQL Server 2005 introdujo la integración del componente Common Language Runtime (CLR) de .NET Framework para Microsoft Windows. Esto significa que ahora se pueden escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de transmisión por secuencias mediante cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET y Microsoft Visual C#. El espacio de nombres <xref:Microsoft.SqlServer.Server> contiene un conjunto de nuevas interfaces de programación de aplicaciones (API) que permiten que el código administrado interactúe con el entorno de Microsoft SQL Server.  
  
 En esta sección se describen las características y comportamientos que son específicos de la integración Common Language Runtime (CLR) de SQL Server, así como las extensiones específicas en proceso de SQL Server a ADO.NET.  
  
 El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión. Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.  
  
 **Documentación de SQL Server**  
  
1. [Conceptos de programación en el ámbito de la integración de Common Language Runtime (CLR)](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a>En esta sección  

 [Introducción a la integración con CLR de SQL Server](introduction-to-sql-server-clr-integration.md)  
 Proporciona una introducción a la integración CLR de SQL Server. También proporciona vínculos a temas adicionales.  
  
 [Funciones CLR definidas por el usuario](clr-user-defined-functions.md)  
 Describe cómo implementar y usar los distintos tipos de funciones CLR: funciones de agregado definidas por el usuario, escalares y con valores de tabla.  
  
 [Tipos CLR definidos por el usuario](clr-user-defined-types.md)  
 Describe cómo implementar y usar los tipos definidos por el usuario CLR. También proporciona vínculos a temas adicionales.  
  
 [Procedimientos almacenados de CLR](clr-stored-procedures.md)  
 Describe cómo implementar y usar los procedimientos almacenados CLR. También proporciona vínculos a temas adicionales.  
  
 [Desencadenadores de CLR](clr-triggers.md)  
 Describe cómo implementar y usar los desencadenadores CLR. También proporciona vínculos a temas adicionales.  
  
 [La conexión de contexto](the-context-connection.md)  
 Describe la conexión de contexto.  
  
 [Comportamiento específico en proceso de SQL Server en ADO.NET](sql-server-in-process-specific-behavior-of-adonet.md)  
 Describe las extensiones específicas en proceso de SQL Server a ADO.NET, y la conexión de contexto. También proporciona vínculos a temas adicionales.  
  
## <a name="see-also"></a>Vea también

- [SQL Server y ADO.NET](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
