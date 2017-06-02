---
title: "C&#243;mo: Generar c&#243;digo personalizado mediante la modificaci&#243;n de un archivo DBML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Generar c&#243;digo personalizado mediante la modificaci&#243;n de un archivo DBML
Puede generar código fuente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o C\# a partir de un archivo de metadatos de lenguaje de marcado de base de datos \(.dbml\).  Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación.  Ésta es una característica avanzada.  
  
 Los pasos de este proceso son los siguientes.  
  
1.  Genere un archivo .dbml.  
  
2.  Utilice un editor para modificar el archivo .dbml.  Tenga en cuenta que el archivo .dbml debe validarse correctamente con el archivo de definición de esquema \(.xsd\) de los archivos .dbml de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Para obtener más información, consulta [Generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3.  Genere el código fuente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o de C\#.  
  
 En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal.  Para obtener más información, consulta [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Ejemplo  
 El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind.  Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## Ejemplo  
 El código siguiente genera un archivo de código fuente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o C\# a partir de un archivo .dbml.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## Vea también  
 [Generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)   
 [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)   
 [Crear el modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)