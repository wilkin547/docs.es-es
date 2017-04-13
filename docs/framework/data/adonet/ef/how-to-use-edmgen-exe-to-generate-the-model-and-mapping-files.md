---
title: "C&#243;mo: Usar EdmGen.exe para generar los archivos de asignaci&#243;n y de modelo | Microsoft Docs"
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
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# C&#243;mo: Usar EdmGen.exe para generar los archivos de asignaci&#243;n y de modelo
En este tema se muestra cómo usar la herramienta EDM Generator \(EdmGen.exe\) para generar los siguientes archivos basados en la base de datos School:  
  
-   Un modelo conceptual \(un archivo .csdl\).  
  
-   Un modelo de almacenamiento \(un archivo .ssdl\).  
  
-   Asignación entre los modelos conceptual y de almacenamiento \(un archivo .msl\).  
  
-   Código del nivel de objeto en Visual Basic o C\#.  
  
-   Archivos de vistas.  
  
 La herramienta EdmGen.exe utiliza \/mode:FullGeneration para generar los archivos enumerados anteriormente.  Para obtener más información sobre los comandos de EdmGen.exe, vea [Generador de EDM \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 Si usa EdmGen.exe para generar los archivos de modelo y asignación, aún tendrá que configurar el proyecto de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] para que utilice [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Para obtener más información, consulta [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/es-es/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Un modelo conceptual generado mediante EdmGen.exe incluye todos los objetos de la base de datos.  Si desea generar un modelo conceptual que solo incluya objetos específicos, use el asistente de Entity Data Model.  Para obtener más información, consulta [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
### Para generar el modelo School para un proyecto de Visual Basic con EdmGen.exe  
  
1.  Cree la base de datos School.  Para obtener más información, consulta [Creating the School Sample Database](http://msdn.microsoft.com/es-es/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
  
    ```  
  
### Para generar el modelo School para un proyecto de C\# con EdmGen.exe  
  
1.  Cree la base de datos School.  Para obtener más información, consulta [Creating the School Sample Database](http://msdn.microsoft.com/es-es/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## Vea también  
 [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/es-es/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/es-es/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/es-es/91076853-0881-421b-837a-f582f36be527)   
 [Cómo: Usar EdmGen.exe para validar los archivos de asignación y de modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)