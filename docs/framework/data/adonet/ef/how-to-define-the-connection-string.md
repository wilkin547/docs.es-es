---
title: "Definir la cadena de conexi&#243;n | Microsoft Docs"
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
  - "ESQL"
  - "jsharp"
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Definir la cadena de conexi&#243;n
En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual.  Este tema se basa en el modelo conceptual de [AdventureWorks Sales](http://msdn.microsoft.com/es-es/f16cd988-673f-4376-b034-129ca93c7832).  El modelo AdventureWorks Sales se usa en todos los temas relacionados con tareas de la documentación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  En este tema se da por supuesto que el usuario ya ha configurado [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y ha definido el modelo AdventureWorks Sales.  Para obtener más información, consulta [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/es-es/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  Los procedimientos de este tema también se incluyen en el tema [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/es-es/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Si usa el Asistente para [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] en un proyecto de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)], el asistente genera automáticamente un archivo .edmx y configura el proyecto para que use [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Para obtener más información, vea [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### Para definir la cadena de conexión de Entity Framework  
  
-   Abra el archivo de configuración de la aplicación del proyecto \(app.config\) y, a continuación, agregue la siguiente cadena de conexión:  
  
  
  
     Si el proyecto no tiene un archivo de configuración de la aplicación, puede agregar uno seleccionando **Agregar nuevo elemento** en el menú **Proyecto**, seleccionando la categoría **General**, **Archivo de configuración de la aplicación** y, después, haciendo clic en **Agregar**.  
  
## Vea también  
 [Quickstart](http://msdn.microsoft.com/es-es/0bc534be-789f-4819-b9f6-76e51d961675)   
 [How to: Create a New .edmx File](http://msdn.microsoft.com/es-es/beb8189e-e51c-4051-839c-9902c224abf2)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/es-es/91076853-0881-421b-837a-f582f36be527)