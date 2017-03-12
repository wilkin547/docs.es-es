---
title: "No se puede consultar una expresi&#243;n de tipo &lt;tipo&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36593"
  - "vbc36593"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36593"
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# No se puede consultar una expresi&#243;n de tipo &lt;tipo&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

No se puede consultar una expresión de tipo \<tipo\>.Compruebe que no falta ninguna referencia de ensamblado ni ninguna importación de espacio de nombres para el proveedor LINQ.  
  
 Los tipos que se pueden consultar se definen en los espacios de nombres <xref:System.Linq>, <xref:System.Data.Linq> y <xref:System.Xml.Linq>.  Debe importar uno o más de estos espacios de nombres para realizar consultas LINQ.  
  
 El espacio de nombres <xref:System.Linq> permite consultar objetos como colecciones y matrices mediante LINQ.  
  
 El espacio de nombres <xref:System.Data.Linq> permite consultar conjuntos de datos de ADO.NET y bases de datos de SQL Server mediante LINQ.  
  
 El espacio de nombres <xref:System.Xml.Linq> permite consultar XML mediante LINQ, además de usar las características XML en Visual Basic.  
  
 **Id. de error:** BC36593  
  
### Para corregir este error  
  
1.  Agregue una instrucción `Import` para el espacio de nombres <xref:System.Linq>, <xref:System.Data.Linq> o <xref:System.Xml.Linq> al archivo de código.  También puede importar los espacios de nombres para el proyecto mediante la página **Referencias** del Diseñador de proyectos \(**Mi Proyecto**\).  
  
2.  Asegúrese de que el tipo que ha identificado como el origen de su consulta es un tipo que se puede consultar.  Es decir, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.  
  
## Vea también  
 <xref:System.Linq>   
 <xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)