---
title: LINQ to Objects (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d2bc048fea9affd4998430783d20b978317f3897
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
Consulta el término "LINQ to Objects" se refiere al uso de LINQ con cualquier <xref:System.Collections.IEnumerable>o <xref:System.Collections.Generic.IEnumerable%601>colección directamente, sin usar un proveedor LINQ intermedio o una API como [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) o [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> Puede usar LINQ para consultar cualquier colección enumerable, como <xref:System.Collections.Generic.List%601>, <xref:System.Array>, o <xref:System.Collections.Generic.Dictionary%602>.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Array> </xref:System.Collections.Generic.List%601> La colección puede ser definida por el usuario o puede devolver una API de .NET Framework.  
  
 Básicamente, LINQ to Objects representa un nuevo enfoque a colecciones. En el sistema antiguo, tenía que escribir complejos bucles `For Each` que especificaban cómo recuperar los datos de una colección. En el enfoque LINQ, se escribe código declarativo que describe lo que desea recuperar.  
  
 Además, las consultas LINQ ofrecen tres ventajas principales respecto a tradicional `For Each` bucles:  
  
1.  Son más concisas y legibles, especialmente cuando se filtran varias condiciones.  
  
2.  Proporcionan funcionalidades eficaces para filtrar, ordenar y agrupar con un código de aplicación mínimo.  
  
3.  Se pueden migrar a otros orígenes de datos con muy poca o ninguna modificación.  
  
 En general, cuanto más compleja es la operación que desea realizar en los datos, más ventajas que obtendrá al usar LINQ en lugar de las técnicas de iteración tradicionales.  
  
 El propósito de esta sección es demostrar el enfoque LINQ con algunos ejemplos seleccionados. No pretende ser exhaustiva.  
  
## <a name="in-this-section"></a>En esta sección  
 [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 Explica cómo se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas. También incluye vínculos a temas que muestran estos principios.  
  
 [LINQ y reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 Vínculos a un ejemplo que muestra cómo LINQ usa la reflexión.  
  
 [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Explica cómo se puede usar LINQ para interactuar con sistemas de archivos. También incluye vínculos a temas que muestran estos conceptos.  
  
 [Cómo: consultar un objeto ArrayList con LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 Muestra cómo consultar un objeto ArrayList en C#.  
  
 [Cómo: agregar métodos personalizados para las consultas LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 Explica cómo extender el conjunto de métodos que puede usar para las consultas LINQ agregando métodos de extensión para el <xref:System.Collections.Generic.IEnumerable%601>interfaz.</xref:System.Collections.Generic.IEnumerable%601>  
  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Proporciona vínculos a temas que explican LINQ y se proporcionan ejemplos de código que realizan las consultas.
