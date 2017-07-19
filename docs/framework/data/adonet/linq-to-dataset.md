---
title: "LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LINQ to DataSet
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] facilita y acelera las consultas en datos almacenados en caché en un objeto <xref:System.Data.DataSet>.  En concreto, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifica la consulta permitiendo a los desarrolladores escribir consultas a partir del lenguaje de programación mismo, en lugar de utilizar un lenguaje de consulta diferente.  Esto resulta especialmente útil para desarrolladores de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], que ahora pueden aprovechar la comprobación de sintaxis en tiempo de compilación, los tipos estáticos y la compatibilidad con IntelliSense que proporciona [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] en las consultas.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] también se puede usar para consultar los datos que se han consolidado de uno o más orígenes de datos.  Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos, como consultar datos agregados localmente y almacenar en caché en el nivel medio en aplicaciones web.  En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.  
  
 La funcionalidad [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] se expone principalmente mediante métodos de extensión en las clases <xref:System.Data.DataRowExtensions> y <xref:System.Data.DataTableExtensions>. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] se basa en, y utiliza, la arquitectura existente [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)], y no está destinada a reemplazar [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] en el código de aplicación.  El código de ADO.NET 2.0 existente continuará funcionando en una aplicación [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. La relación de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] con [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] y los datos almacenados se muestran en el diagrama siguiente.  
  
 ![LINQ to DataSet se basa en el proveedor de ADO.NET](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")  
  
## En esta sección  
 [Introducción](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## Referencia  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## Vea también  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ y ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)   
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)