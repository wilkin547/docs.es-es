---
title: "Modelado y asignaci&#243;n | Microsoft Docs"
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
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Modelado y asignaci&#243;n
En [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], puede definir el modelo conceptual, el modelo de almacenamiento y la asignación entre los dos de la forma que mejor convenga a la aplicación.  Las Herramientas de Entity Data Model en [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] permiten crear un [archivo .edmx](http://msdn.microsoft.com/es-es/f4c8e7ce-1db6-417e-9759-15f8b55155d4) a partir de una base de datos o un modelo gráfico y, a continuación, actualizar ese archivo cuando la base de datos o el modelo cambie.  
  
 A partir de Entity Framework 4.0.1 también puede crear un modelo mediante programación usando desarrollo Code First.  Hay dos escenarios diferentes para el desarrollo Code First.  En ambos casos, el desarrollador define un modelo codificando definiciones de clase de .NET Framework y especifica opcionalmente la asignación o configuración adicional usando anotaciones de datos o la API fluida.  
  
 Para obtener más información, vea [Crear y asignar un modelo conceptual](http://go.microsoft.com/fwlink/?LinkId=235016).  
  
 También puede usar el generador de EDM, que se incluye con [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].  EdmGen.exe genera los archivos .csdl, .ssdl y .msl a partir de un origen de datos existente.  También puede crear manualmente el contenido del modelo y la asignación.  Para obtener más información, consulta [Generador de EDM \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).