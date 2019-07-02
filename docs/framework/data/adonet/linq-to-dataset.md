---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: c4069ef760877935c4ce194144d131d0dc58b4d3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504355"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
LINQ to DataSet resulta más sencillo y más rápido para consultar los datos en caché en un <xref:System.Data.DataSet> objeto. En concreto, LINQ to DataSet simplifica la consulta permitiendo a los desarrolladores escribir consultas desde el lenguaje de programación mismo, en lugar de mediante un lenguaje de consulta independiente. Esto es especialmente útil para los desarrolladores de Visual Studio, que ahora pueden aprovechar las ventajas de la comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense proporcionado por Visual Studio en las consultas.  
  
 También se puede usar LINQ a conjunto de datos para consultar los datos que se han consolidado de uno o varios orígenes de datos. Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos, como consultar datos agregados localmente y almacenar en caché en el nivel medio en aplicaciones web. En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.  
  
 LINQ to DataSet funcionalidad se expone principalmente a través de los métodos de extensión en el <xref:System.Data.DataRowExtensions> y <xref:System.Data.DataTableExtensions> clases. LINQ to DataSet se basa en y usa la arquitectura de ADO.NET existente y no pretende reemplazar ADO.NET en el código de la aplicación. El código de ADO.NET existente seguirán funcionando en una aplicación de LINQ to DataSet. En el diagrama siguiente, se ilustra la relación de LINQ to DataSet en ADO.NET y el almacén de datos.  
  
 ![Diagrama que muestra que LINQ to DataSet se basa en el proveedor de ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>En esta sección  
 [Introducción](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Referencia  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>Vea también

- [Language Integrated Query (LINQ) (C#)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Language Integrated Query (LINQ) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ y ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
