---
title: "Consideraciones de implementaci&#243;n (Entity Framework) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Consideraciones de implementaci&#243;n (Entity Framework)
En este tema se proporciona información sobre cómo implementar aplicaciones que utilizan ADO.NET Entity Framework para el acceso a datos.  Para obtener más información acerca de Entity Framework, vea [Introducción](../../../../../docs/framework/data/adonet/ef/getting-started.md).  
  
 Entity Framework proporciona un conjunto de herramientas que se integran con Visual Studio y facilitan el desarrollo.  Para obtener más información, consulta [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/es-es/91076853-0881-421b-837a-f582f36be527).  En este tema no se describe cómo utilizar tecnologías concretas para implementar una aplicación basada en Entity Framework.  
  
 Visual Studio proporciona funcionalidad para distribuir e implementar aplicaciones, como la implementación ClickOnce.  Para obtener más información, vea [Implementar aplicaciones y componentes](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md) en la documentación de Visual Studio.  
  
 Las consideraciones siguientes se aplican al implementar una aplicación que utiliza Entity Framework:  
  
-   Entity Framework forma parte de .NET Framework a partir de .NET Framework 3.5 Service Pack 1 \(SP1\).  Debe asegurarse de que esté instalado .NET Framework 3.5 Service Pack 1 o posterior al implementar una aplicación basada en Entity Framework.  
  
-   Cuando el Asistente para Entity Data Model genera un modelo conceptual, se crea una cadena de conexión en el archivo de configuración de la aplicación.  Los archivos de asignación y de modelo se pueden incrustar como recursos de aplicación o se pueden copiar en el directorio de resultados.  De forma predeterminada, se implementan como recursos incrustados de la aplicación.  Use la propiedad `Metadata Artifact Processing` del archivo de Entity Designer para seleccionar una de estas opciones.  Para obtener más información, consulta [How to: Copy Model and Mapping Files to the Output Directory](http://msdn.microsoft.com/es-es/e2c9820f-1705-457e-9fdb-8b289f3179b4).  
  
-   Asegúrese de que la información sobre la asignación y el modelo \(expresada en el lenguaje de definición de esquemas conceptuales \(CSDL\), el lenguaje de definición de esquemas de almacenamiento \(SSDL\) y el lenguaje de especificación de asignaciones \(MSL\)\) se implementa junto con la aplicación y en la ubicación especificada por la cadena de conexión.  Para obtener más información, consulta [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
-   Cuando se incrusta información sobre la asignación y el modelo como recursos de la aplicación, se debe recompilar e implementar la aplicación cada vez que se actualiza el modelo conceptual.  
  
-   Dado que Entity Framework es un componente de .NET Framework, se puede redistribuir con la aplicación si lo permite el contrato de licencia de .NET Framework.  
  
## Vea también  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)   
 [Consideraciones de desarrollo e implementación](../../../../../docs/framework/data/adonet/ef/development-and-deployment-considerations.md)