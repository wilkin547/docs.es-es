---
title: "Analizar el c&#243;digo fuente de LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Analizar el c&#243;digo fuente de LINQ to SQL
Con ayuda de los pasos siguientes, puede generar código fuente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizando la base de datos de ejemplo Northwind.  Puede comparar elementos del modelo de objetos con elementos de la base de datos para ver mejor cómo se asignan los distintos elementos.  
  
> [!NOTE]
>  Los desarrolladores que utilizan [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] para generar este código.  
  
1.  Si aún no tiene la base de datos de ejemplo Northwind en su equipo de desarrollo, puede descargarla de forma gratuita.  Para obtener más información, consulte [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
2.  Utilice la herramienta de línea de comandos SqlMetal para generar un archivo de código fuente de Visual Basic o C\#.  Para obtener más información, consulte [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  Si escribe los comandos siguientes en un símbolo del sistema, puede generar archivos de código fuente de Visual Basic y C\# que incluyan procedimientos almacenados y funciones:  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## Vea también  
 [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)   
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)