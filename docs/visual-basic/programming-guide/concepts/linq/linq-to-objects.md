---
title: LINQ to Objects
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: 004198f61569d50b608d002ab752e7381bf1368e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549834"
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
El término "LINQ to Objects" se refiere al uso de consultas LINQ con cualquier colección <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> directamente, sin usar un proveedor o una API de LINQ intermedios como [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](../../../../standard/linq/linq-xml-overview.md). Puede usar LINQ para consultar cualquier colección enumerable, como <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>. La colección puede ser definida por el usuario o haber sido devuelta por una API de .NET Framework.  
  
 Básicamente, LINQ to Objects representa un nuevo enfoque para las colecciones. En el sistema antiguo, tenía que escribir complejos bucles `For Each` que especificaban cómo recuperar los datos de una colección. En el enfoque de LINQ, se escribe código declarativo que describe qué se quiere recuperar.  
  
 Además, las consultas LINQ ofrecen tres ventajas principales respecto a los bucles `For Each` tradicionales:  
  
1. Son más concisas y legibles, especialmente cuando se filtran varias condiciones.  
  
2. Proporcionan funcionalidades eficaces para filtrar, ordenar y agrupar con un código de aplicación mínimo.  
  
3. Se pueden migrar a otros orígenes de datos con muy poca o ninguna modificación.  
  
 Por lo general, cuanto más compleja sea la operación que quiere realizar en los datos, más ventajas obtendrá al usar LINQ en lugar de las técnicas de iteración tradicionales.  
  
 El propósito de esta sección es mostrar el enfoque de LINQ con algunos ejemplos seleccionados. No pretende ser exhaustiva.  
  
## <a name="in-this-section"></a>En esta sección  
 [LINQ y cadenas (Visual Basic)](linq-and-strings.md)  
 Explica cómo se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas. También incluye vínculos a temas que muestran estos principios.  
  
 [LINQ y reflexión (Visual Basic)](linq-and-reflection.md)  
 Vincula a un ejemplo que muestra cómo usa LINQ la reflexión.  
  
 [LINQ y directorios de archivos (Visual Basic)](linq-and-file-directories.md)  
 Explica cómo se puede usar LINQ para interactuar con sistemas de archivos. También incluye vínculos a temas que muestran estos conceptos.  
  
 [Cómo: consultar una ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md)  
 Muestra cómo consultar un objeto ArrayList en C#.  
  
 [Cómo: agregar métodos personalizados para las consultas LINQ (Visual Basic)](how-to-add-custom-methods-for-linq-queries.md)  
 Explica cómo extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [Language-Integrated Query (LINQ) (Visual Basic)](index.md)  
 Proporciona vínculos a temas que explican LINQ y que proporcionan ejemplos de código que realizan consultas.
