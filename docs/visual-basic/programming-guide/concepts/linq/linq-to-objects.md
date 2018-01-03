---
title: LINQ to Objects (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c2a48e792c656a84c07730b67f734f6b539ab97d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
El término "LINQ to Objects" se refiere al uso de consultas LINQ con cualquier colección <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> directamente, sin usar un proveedor o una API de LINQ intermedios como [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13). Puede usar LINQ para consultar cualquier colección enumerable, como <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>. La colección puede ser definida por el usuario o haber sido devuelta por una API de .NET Framework.  
  
 Básicamente, LINQ to Objects representa un nuevo enfoque para las colecciones. En el sistema antiguo, tenía que escribir complejos bucles `For Each` que especificaban cómo recuperar los datos de una colección. En el enfoque de LINQ, se escribe código declarativo que describe qué se quiere recuperar.  
  
 Además, las consultas LINQ ofrecen tres ventajas principales respecto a los bucles `For Each` tradicionales:  
  
1.  Son más concisas y legibles, especialmente cuando se filtran varias condiciones.  
  
2.  Proporcionan funcionalidades eficaces para filtrar, ordenar y agrupar con un código de aplicación mínimo.  
  
3.  Se pueden migrar a otros orígenes de datos con muy poca o ninguna modificación.  
  
 Por lo general, cuanto más compleja sea la operación que quiere realizar en los datos, más ventajas obtendrá al usar LINQ en lugar de las técnicas de iteración tradicionales.  
  
 El propósito de esta sección es mostrar el enfoque de LINQ con algunos ejemplos seleccionados. No pretende ser exhaustiva.  
  
## <a name="in-this-section"></a>En esta sección  
 [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 Explica cómo se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas. También incluye vínculos a temas que muestran estos principios.  
  
 [LINQ y reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 Vincula a un ejemplo que muestra cómo usa LINQ la reflexión.  
  
 [LINQ y directorios de archivos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Explica cómo se puede usar LINQ para interactuar con sistemas de archivos. También incluye vínculos a temas que muestran estos conceptos.  
  
 [Cómo: consultar un objeto ArrayList con LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 Muestra cómo consultar un objeto ArrayList en C#.  
  
 [Cómo: agregar métodos personalizados para las consultas LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 Explica cómo extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Proporciona vínculos a temas que explican LINQ y que proporcionan ejemplos de código que realizan consultas.
