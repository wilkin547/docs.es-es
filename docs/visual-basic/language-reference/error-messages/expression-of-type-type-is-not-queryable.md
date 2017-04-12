---
title: "Expresión de tipo &lt;tipo&gt; no es consultable | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
dev_langs:
- VB
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1e7e1e2652cf730ef6d14b0579d8a3ee3de67fbb
ms.lasthandoff: 03/13/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>Expresión de tipo &lt;tipo&gt; no es consultable
Expresión de tipo \<tipo > no es consultable. Asegúrese de que no falta una importación de espacio de nombres o de referencia de ensamblado para el proveedor LINQ.  
  
 Puede consultables tipos se definen en el <xref:System.Linq>, <xref:System.Data.Linq>, y <xref:System.Xml.Linq>los espacios de nombres.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> Debe importar uno o varios de estos espacios de nombres para realizar consultas LINQ.  
  
 El <xref:System.Linq>espacio de nombres permite consultar objetos como colecciones y matrices mediante LINQ.</xref:System.Linq>  
  
 El <xref:System.Data.Linq>espacio de nombres le permite consultar conjuntos de datos de ADO.NET y bases de datos de SQL Server mediante LINQ.</xref:System.Data.Linq>  
  
 El <xref:System.Xml.Linq>espacio de nombres le permite consultar XML mediante LINQ y usar características XML en Visual Basic.</xref:System.Xml.Linq>  
  
 **Id. de error:** BC36593  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Agregar una `Import` instrucción para el <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq>el espacio de nombres al archivo de código.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> También puede importar los espacios de nombres para el proyecto mediante la **referencias** página del Diseñador de proyectos (**mi proyecto**).  
  
2.  Asegúrese de que el tipo que se ha identificado como el origen de la consulta es un tipo consultable. Es decir, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq></xref:System.Linq>   
 <xref:System.Data.Linq></xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Página Referencias, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)
