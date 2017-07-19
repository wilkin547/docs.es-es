---
title: "C&#243;mo: Convertir entidades en serializables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo: Convertir entidades en serializables
Puede hacer que las entidades sean serializables al generar el código.  Las clases de entidad se decoran con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> y las columnas con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Los desarrolladores que utilizan [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para este propósito.  
  
 Si usa la herramienta de línea de comandos de SQLMetal, use la opción **\/serialization** con el argumento `unidirectional`.  Para obtener más información, consulte [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Ejemplo  
 Con las siguientes líneas de comandos de SQLMetal se generan archivos que tienen entidades serializables.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## Vea también  
 [Serialización](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)   
 [Crear el modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)