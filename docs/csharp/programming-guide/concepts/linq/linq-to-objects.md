---
title: LINQ to Objects (C#)
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: c488e49283f3e30ea729adf111fd9ca297039838
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241570"
---
# <a name="linq-to-objects-c"></a>LINQ to Objects (C#)
El término "LINQ to Objects" se refiere al uso de consultas LINQ con cualquier colección <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> directamente, sin usar un proveedor o una API de LINQ intermedios como [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](./linq-to-xml-overview.md). Puede usar LINQ para consultar cualquier colección enumerable, como <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>. La colección puede haberla definido el usuario, o bien puede que la haya devuelto una API de .NET.  
  
 Básicamente, LINQ to Objects representa un nuevo enfoque para las colecciones. En el sistema antiguo, tenía que escribir complejos bucles `foreach` que especificaban cómo recuperar los datos de una colección. En el enfoque de LINQ, se escribe código declarativo que describe qué se quiere recuperar.  
  
 Además, las consultas LINQ ofrecen tres ventajas principales respecto a los bucles `foreach` tradicionales:  
  
1. Son más concisas y legibles, especialmente cuando se filtran varias condiciones.  
  
2. Proporcionan funcionalidades eficaces para filtrar, ordenar y agrupar con un código de aplicación mínimo.  
  
3. Se pueden migrar a otros orígenes de datos con muy poca o ninguna modificación.  
  
 Por lo general, cuanto más compleja sea la operación que quiere realizar en los datos, más ventajas obtendrá al usar LINQ en lugar de las técnicas de iteración tradicionales.  
  
 El propósito de esta sección es mostrar el enfoque de LINQ con algunos ejemplos seleccionados. No pretende ser exhaustiva.  
  
## <a name="in-this-section"></a>En esta sección  
 [LINQ y cadenas (C#)](./linq-and-strings.md)  
 Explica cómo se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas. También incluye vínculos a temas que muestran estos principios.  
  
 [LINQ y reflexión (C#)](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 Vincula a un ejemplo que muestra cómo usa LINQ la reflexión.  
  
 [LINQ y directorios de archivos (C#)](./linq-and-file-directories.md)  
 Explica cómo se puede usar LINQ para interactuar con sistemas de archivos. También incluye vínculos a temas que muestran estos conceptos.  
  
 [Procedimiento para consultar un objeto ArrayList con LINQ (C#)](./how-to-query-an-arraylist-with-linq.md)  
 Muestra cómo consultar un objeto ArrayList en C#.  
  
 [Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)](./how-to-add-custom-methods-for-linq-queries.md)  
 Explica cómo extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [Language Integrated Query (LINQ) (C#)](./index.md)  
 Proporciona vínculos a temas que explican LINQ y que proporcionan ejemplos de código que realizan consultas.
