---
title: Información general de LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: dc20a8fb-03f6-4b68-9c2b-7f7299e3070b
ms.openlocfilehash: f7659d03005df69d7debe604581ce49973f938cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200620"
---
# <a name="linq-to-dataset-overview"></a>Información general de LINQ to DataSet

<xref:System.Data.DataSet>Es uno de los componentes más utilizados de ADO.net. Es un elemento clave del modelo de programación desconectado en el que se basa ADO.NET y permite almacenar explícitamente en caché los datos de diferentes orígenes de datos. Para el nivel de presentación, <xref:System.Data.DataSet> está estrechamente integrado en los controles de GUI para el enlace de datos. Para el nivel medio, proporciona una caché que conserva la forma relacional de los datos e incluye servicios de exploración de jerarquías y consultas rápidos y sencillos. Una técnica común que se usa para reducir el número de solicitudes en una base de datos es usar <xref:System.Data.DataSet> para el almacenamiento en caché en el nivel intermedio. Por ejemplo, considere una aplicación Web ASP.NET controlada por datos. A menudo una parte importante de los datos de aplicación no cambia frecuentemente y es común entre sesiones o usuarios. Estos datos se pueden conservar en memoria o en un servidor web, lo que reduce el número de solicitudes en la base de datos y acelera las interacciones del usuario. Otro aspecto útil de <xref:System.Data.DataSet> es que permite que una aplicación lleve subconjuntos de datos de uno o más orígenes de datos al espacio de la aplicación. La aplicación puede manipular los datos en memoria mientras retiene su forma relacional.  
  
 A pesar de su importancia, <xref:System.Data.DataSet> tiene capacidades de consulta limitadas. El método <xref:System.Data.DataTable.Select%2A> se puede usar para filtrar y ordenar y los métodos <xref:System.Data.DataRow.GetChildRows%2A> y <xref:System.Data.DataRow.GetParentRow%2A> se pueden usar para la exploración de jerarquías. Sin embargo, para cualquier tarea más compleja, el programador debe escribir una consulta personalizada. Esto puede tener como resultado aplicaciones con un bajo rendimiento y con un mantenimiento difícil.  
  
 LINQ to DataSet hace que sea más fácil y rápido consultar los datos almacenados en caché en un <xref:System.Data.DataSet> objeto. Esas consultas se expresan en el lenguaje de programación mismo, en lugar de como literales de cadena incrustados en el código de la aplicación. Esto significa que los desarrolladores no tienen que aprender un lenguaje de consultas diferente. Además, LINQ to DataSet permite a los desarrolladores de Visual Studio trabajar de forma más productiva, ya que el IDE de Visual Studio proporciona comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense para LINQ. LINQ to DataSet también puede usarse para consultar los datos que se han consolidado de uno o varios orígenes de datos. Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos. En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.  
  
## <a name="querying-datasets-using-linq-to-dataset"></a>Consultar conjuntos de datos usando LINQ to DataSet  

 Antes de poder empezar a consultar un <xref:System.Data.DataSet> objeto mediante LINQ to DataSet, debe rellenar el <xref:System.Data.DataSet> . Hay varias maneras de cargar datos en un <xref:System.Data.DataSet> , como usar la <xref:System.Data.Common.DataAdapter> clase o [LINQ to SQL](./sql/linq/index.md). Una vez que los datos se han cargado en un <xref:System.Data.DataSet> objeto, puede empezar a consultarlos. La formulación de consultas mediante LINQ to DataSet es similar al uso de Language-Integrated Query (LINQ) en otros orígenes de datos habilitados para LINQ. Las consultas LINQ se pueden realizar en tablas únicas en un <xref:System.Data.DataSet> o en más de una tabla mediante el uso de los <xref:System.Linq.Enumerable.Join%2A> operadores de <xref:System.Linq.Enumerable.GroupJoin%2A> consulta estándar y.  
  
 Las consultas LINQ se admiten en objetos con tipo y sin tipo <xref:System.Data.DataSet> . Si el esquema de <xref:System.Data.DataSet> es desconocido en tiempo de diseño, se recomienda un <xref:System.Data.DataSet> con tipo. En un <xref:System.Data.DataSet> con tipo, las tablas y las filas tienen miembros con tipo para cada una de las columnas, lo que hace que las consultas sean más sencillas y legibles.  
  
 Además de los operadores de consulta estándar implementados en System.Core.dll, LINQ to DataSet agrega varias <xref:System.Data.DataSet> extensiones específicas que facilitan la consulta en un conjunto de <xref:System.Data.DataRow> objetos. Estas extensiones específicas de <xref:System.Data.DataSet> incluyen operadores para comparar secuencias de filas, así como métodos que proporcionan acceso a los valores de columna de un <xref:System.Data.DataRow>.  
  
## <a name="n-tier-applications-and-linq-to-dataset"></a>Aplicaciones con n niveles y LINQ to DataSet  

 Las aplicaciones de datos con n niveles son aplicaciones centradas en datos separadas en varias capas lógicas (o niveles). Una aplicación con n capas típica incluye una capa de presentación, una capa media y una capa de datos. Al separar los componentes de la aplicación en niveles independientes, se aumenta la facilidad de  mantenimiento y la escalabilidad de la aplicación. Para obtener más información sobre las aplicaciones de datos con N niveles, vea [trabajar con conjuntos de datos en aplicaciones de n niveles](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).  
  
 En las aplicaciones con n niveles, a menudo se utiliza <xref:System.Data.DataSet> en el nivel medio para almacenar en caché información para una aplicación web. La funcionalidad de consulta de LINQ to DataSet se implementa a través de métodos de extensión y extiende el ADO.NET existente 2,0 <xref:System.Data.DataSet> .  
  
## <a name="see-also"></a>Consulte también

- [Consulta de conjuntos de datos](querying-datasets-linq-to-dataset.md)
- [Language Integrated Query (LINQ) (C#)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Language Integrated Query (LINQ) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ to SQL](./sql/linq/index.md)
