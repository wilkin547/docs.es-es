---
title: "C&#243;mo: Usar EdmGen.exe para validar los archivos de asignaci&#243;n y de modelo | Microsoft Docs"
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
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# C&#243;mo: Usar EdmGen.exe para validar los archivos de asignaci&#243;n y de modelo
En este tema se muestra cómo utilizar la herramienta [EDM Generator \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) para validar los archivos del modelo y de asignación.  Para obtener más información, consulta [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### Para validar el modelo School mediante el uso de EdmGen.exe  
  
1.  Cree la base de datos School.  Para obtener más información, consulta [Creating the School Sample Database](http://msdn.microsoft.com/es-es/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Genere el modelo School.  Para obtener más información, consulta [Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```scr  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## Vea también  
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/es-es/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/es-es/91076853-0881-421b-837a-f582f36be527)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/es-es/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [Cómo: Usar EdmGen.exe para generar código de nivel de objeto](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)