---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 1c03cca80de6003a4e49278871983ed7fcb3dc0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200672"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet

LINQ to DataSet hace que sea más fácil y rápido consultar los datos almacenados en caché en un <xref:System.Data.DataSet> objeto. En concreto, LINQ to DataSet simplifica las consultas, ya que permite a los desarrolladores escribir consultas desde el propio lenguaje de programación, en lugar de usar un lenguaje de consulta independiente. Esto es especialmente útil para los desarrolladores de Visual Studio, que ahora pueden aprovechar las ventajas de la comprobación de sintaxis en tiempo de compilación, los tipos estáticos y la compatibilidad con IntelliSense que proporciona Visual Studio en sus consultas.  
  
 LINQ to DataSet también puede usarse para consultar los datos que se han consolidado de uno o varios orígenes de datos. Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos, como consultar datos agregados localmente y almacenar en caché en el nivel medio en aplicaciones web. En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.  
  
 La funcionalidad de LINQ to DataSet se expone principalmente a través de los métodos de extensión de las <xref:System.Data.DataRowExtensions> <xref:System.Data.DataTableExtensions> clases y. LINQ to DataSet se basa en y usa la arquitectura de ADO.NET existente y no está diseñada para reemplazar ADO.NET en el código de la aplicación. El código de ADO.NET existente seguirá funcionando en una aplicación LINQ to DataSet. La relación de LINQ to DataSet con ADO.NET y el almacén de datos se muestra en el diagrama siguiente.  
  
 ![Diagrama que muestra que LINQ to DataSet se basa en el proveedor ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>En esta sección  

 [Introducción](getting-started-linq-to-dataset.md)  
  
 [Guía de programación](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Referencia  

 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Vea también

- [Language Integrated Query (LINQ) (C#)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Language Integrated Query (LINQ) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ y ADO.NET](linq-and-ado-net.md)
- [ADO.NET](index.md)
