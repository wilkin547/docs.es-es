---
title: "C&#243;mo hacer que los archivos de asignaci&#243;n y de modelo sean recursos incrustados | Microsoft Docs"
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
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo hacer que los archivos de asignaci&#243;n y de modelo sean recursos incrustados
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] permite implementar archivos de asignación y de modelo como recursos incrustados de una aplicación.  El ensamblado con los archivos de asignación y de modelo incrustados se debe cargar en el mismo dominio de aplicación que la conexión de entidad.  Para obtener más información, consulta [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  De forma predeterminada, las herramientas de [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incrustan los archivos de asignación y de modelo. Cuando defina los archivos de asignación y de modelo manualmente, use este procedimiento para asegurarse de que dichos archivos se implementan como recursos incrustados junto con una aplicación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Para mantener los recursos incrustados, deberá repetir este procedimiento cada vez que se modifiquen los archivos de asignación y de modelo.  
  
### Para incrustar los archivos de asignación y de modelo  
  
1.  En el **Explorador de soluciones**, seleccione el archivo conceptual \(.csdl\).  
  
2.  En el panel **Propiedades**, establezca **Acción de compilación** en **Recurso incrustado**.  
  
3.  Repita los pasos 1 y 2 para el archivo de almacenamiento \(.ssdl\) y el archivo de asignación \(.msl\).  
  
4.  En el **Explorador de soluciones**, haga doble clic en el archivo App.config y, a continuación, modifique el parámetro `Metadata` del atributo `connectionString` usando uno de los formatos siguientes:  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Para obtener más información, consulta [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
## Ejemplo  
 La cadena de conexión siguiente hace referencia a los archivos de asignación y de modelo incrustados para el [modelo AdventureWorks Sales](http://msdn.microsoft.com/es-es/f16cd988-673f-4376-b034-129ca93c7832).  Esta cadena de conexión está almacenada en el archivo App.config del proyecto.  
  
  
  
## Vea también  
 [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [Definir la cadena de conexión](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)   
 [Cómo generar una cadena de conexión EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/es-es/91076853-0881-421b-837a-f582f36be527)