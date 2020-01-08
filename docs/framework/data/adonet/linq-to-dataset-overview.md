---
title: Información general de LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: dc20a8fb-03f6-4b68-9c2b-7f7299e3070b
ms.openlocfilehash: 20d9be052ba2567c16718b4b1c1019427c9b5df1
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634825"
---
# <a name="linq-to-dataset-overview"></a>Información general de LINQ to DataSet
La <xref:System.Data.DataSet> es uno de los componentes más utilizados de ADO.NET. Es un elemento clave del modelo de programación desconectado en el que se basa ADO.NET y permite almacenar explícitamente en caché los datos de diferentes orígenes de datos. Para el nivel de presentación, <xref:System.Data.DataSet> está estrechamente integrado en los controles de GUI para el enlace de datos. Para el nivel medio, proporciona una caché que conserva la forma relacional de los datos e incluye servicios de exploración de jerarquías y consultas rápidos y sencillos. Una técnica común que se usa para reducir el número de solicitudes en una base de datos es usar el <xref:System.Data.DataSet> para el almacenamiento en caché en el nivel intermedio. Por ejemplo, considere una aplicación Web ASP.NET controlada por datos. A menudo una parte importante de los datos de aplicación no cambia frecuentemente y es común entre sesiones o usuarios. Estos datos se pueden conservar en memoria o en un servidor web, lo que reduce el número de solicitudes en la base de datos y acelera las interacciones del usuario. Otro aspecto útil del <xref:System.Data.DataSet> es que permite que una aplicación lleve subconjuntos de datos de uno o varios orígenes de datos al espacio de la aplicación. La aplicación puede manipular los datos en memoria mientras retiene su forma relacional.  
  
 A pesar de su importancia, <xref:System.Data.DataSet> tiene capacidades de consulta limitadas. El método <xref:System.Data.DataTable.Select%2A> se puede usar para filtrar y ordenar y los métodos <xref:System.Data.DataRow.GetChildRows%2A> y <xref:System.Data.DataRow.GetParentRow%2A> se pueden usar para la exploración de jerarquías. Sin embargo, para cualquier tarea más compleja, el programador debe escribir una consulta personalizada. Esto puede tener como resultado aplicaciones con un bajo rendimiento y con un mantenimiento difícil.  
  
 LINQ to DataSet facilita y agiliza la consulta de datos almacenados en caché en un objeto <xref:System.Data.DataSet>. Esas consultas se expresan en el lenguaje de programación mismo, en lugar de como literales de cadena incrustados en el código de la aplicación. Esto significa que los desarrolladores no tienen que aprender un lenguaje de consultas diferente. Además, LINQ to DataSet permite a los desarrolladores de Visual Studio trabajar de forma más productiva, ya que el IDE de Visual Studio proporciona comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense para LINQ. LINQ to DataSet también puede usarse para consultar los datos que se han consolidado de uno o varios orígenes de datos. Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos. En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.  
  
## <a name="querying-datasets-using-linq-to-dataset"></a>Consultar conjuntos de datos usando LINQ to DataSet  
 Antes de poder empezar a consultar un objeto de <xref:System.Data.DataSet> mediante LINQ to DataSet, debe rellenar el <xref:System.Data.DataSet>. Hay varias maneras de cargar datos en un <xref:System.Data.DataSet>, como el uso de la clase <xref:System.Data.Common.DataAdapter> o [LINQ to SQL](./sql/linq/index.md). Una vez que los datos se han cargado en un objeto <xref:System.Data.DataSet>, puede empezar a consultarlos. La formulación de consultas mediante LINQ to DataSet es similar al uso de Language-Integrated Query (LINQ) en otros orígenes de datos habilitados para LINQ. Las consultas LINQ se pueden realizar en tablas únicas en un <xref:System.Data.DataSet> o en más de una tabla usando los operadores de consulta estándar <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A>.  
  
 Las consultas LINQ se admiten en objetos de <xref:System.Data.DataSet> con tipo y sin tipo. Si el esquema de <xref:System.Data.DataSet> es desconocido en tiempo de diseño, se recomienda un <xref:System.Data.DataSet> con tipo. En un <xref:System.Data.DataSet> con tipo, las tablas y las filas tienen miembros con tipo para cada una de las columnas, lo que hace que las consultas sean más sencillas y legibles.  
  
 Además de los operadores de consulta estándar implementados en System. Core. dll, LINQ to DataSet agrega varias extensiones específicas de <xref:System.Data.DataSet>que facilitan la consulta en un conjunto de objetos <xref:System.Data.DataRow>. Estas extensiones específicas de <xref:System.Data.DataSet> incluyen operadores para comparar secuencias de filas, así como métodos que proporcionan acceso a los valores de columna de un <xref:System.Data.DataRow>.  
  
## <a name="n-tier-applications-and-linq-to-dataset"></a>Aplicaciones con n niveles y LINQ to DataSet  
 Las aplicaciones de datos con n niveles son aplicaciones centradas en datos que están separadas en varias capas lógicas (o niveles). Una aplicación con n capas típica incluye una capa de presentación, una capa media y una capa de datos. Al separar los componentes de la aplicación en niveles independientes, se aumenta la facilidad de  mantenimiento y la escalabilidad de la aplicación. Para obtener más información sobre las aplicaciones de datos con N niveles, vea [trabajar con conjuntos de datos en aplicaciones de n niveles](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).  
  
 En las aplicaciones con n niveles, a menudo se utiliza <xref:System.Data.DataSet> en el nivel medio para almacenar en caché información para una aplicación web. La funcionalidad de consulta de LINQ to DataSet se implementa a través de métodos de extensión y extiende el <xref:System.Data.DataSet>ADO.NET 2,0 existente.  
  
## <a name="see-also"></a>Vea también

- [Consulta de conjuntos de datos](querying-datasets-linq-to-dataset.md)
- [Language Integrated Query (LINQ) (C#)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Language Integrated Query (LINQ) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ to SQL](./sql/linq/index.md)
