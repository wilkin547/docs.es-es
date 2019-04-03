---
title: No se puede consultar una expresión de tipo <type>
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 7f74d56b47629ff76f9b935d26278ace8df4c353
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842335"
---
# <a name="expression-of-type-type-is-not-queryable"></a>Expresión de tipo \<tipo > no es consultable
Expresión de tipo \<tipo > no es consultable. Asegúrese de que no falta una importación de espacio de nombres o de referencia de ensamblado para el proveedor LINQ.  
  
 Puede consultables tipos se definen en el <xref:System.Linq>, <xref:System.Data.Linq>, y <xref:System.Xml.Linq> espacios de nombres. Debe importar uno o varios de estos espacios de nombres para realizar consultas LINQ.  
  
 El <xref:System.Linq> espacio de nombres permite a los objetos de consulta como colecciones y matrices mediante LINQ.  
  
 El <xref:System.Data.Linq> espacio de nombres le permite consultar los conjuntos de datos de ADO.NET y las bases de datos de SQL Server mediante LINQ.  
  
 El <xref:System.Xml.Linq> espacio de nombres le permite consultar XML con LINQ y usar características XML en Visual Basic.  
  
 **Identificador de error:** BC36593  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Agregar un `Import` instrucción para el <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq> espacio de nombres al archivo de código. También puede importar los espacios de nombres para el proyecto mediante el **referencias** página del Diseñador de proyectos (**mi proyecto**).  
  
2.  Asegúrese de que el tipo que se ha identificado como el origen de la consulta es un tipo consultable. Es decir, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Página Referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
