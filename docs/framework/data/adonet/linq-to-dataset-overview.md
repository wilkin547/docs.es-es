---
title: "Informaci&#243;n general de LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dc20a8fb-03f6-4b68-9c2b-7f7299e3070b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Informaci&#243;n general de LINQ to DataSet
<xref:System.Data.DataSet> es uno de los componentes más ampliamente utilizados de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. Es un elemento fundamental del modelo de programación desconectado en el que se basa [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] y permite almacenar explícitamente en caché datos de diferentes orígenes de datos. Para el nivel de presentación, <xref:System.Data.DataSet> está estrechamente integrado en los controles de GUI para el enlace de datos. Para el nivel medio, proporciona una caché que conserva la forma relacional de los datos e incluye servicios de exploración de jerarquías y consultas rápidos y sencillos.  Una técnica común que se usa para reducir el número de solicitudes de una bases de datos consiste en utilizar <xref:System.Data.DataSet> para el almacenamiento en caché en el nivel medio.  Por ejemplo, piense en una aplicación web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] controlada por datos.  A menudo una parte importante de los datos de aplicación no cambia frecuentemente y es común entre sesiones o usuarios.  Estos datos se pueden conservar en memoria o en un servidor web, lo que reduce el número de solicitudes en la base de datos y acelera las interacciones del usuario.  Otro aspecto útil de <xref:System.Data.DataSet> es que permite que una aplicación lleve subconjuntos de datos de uno o más orígenes de datos al espacio de la aplicación.  La aplicación puede manipular los datos en memoria mientras retiene su forma relacional.  
  
 A pesar de su importancia, <xref:System.Data.DataSet> tiene capacidades de consulta limitadas.  El método <xref:System.Data.DataTable.Select%2A> se puede usar para filtrar y ordenar y los métodos <xref:System.Data.DataRow.GetChildRows%2A> y <xref:System.Data.DataRow.GetParentRow%2A> se pueden usar para la exploración de jerarquías.  Sin embargo, para cualquier tarea más compleja, el programador debe escribir una consulta personalizada.  Esto puede tener como resultado aplicaciones con un bajo rendimiento y con un mantenimiento difícil.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] facilita y acelera las consultas en datos almacenados en caché en un objeto <xref:System.Data.DataSet>.  Esas consultas se expresan en el lenguaje de programación mismo, en lugar de como literales de cadena incrustados en el código de la aplicación.  Esto significa que los desarrolladores no tienen que aprender un lenguaje de consultas diferente.  Adicionalmente, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] permite a los desarrolladores de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] trabajar de forma más productiva, ya que la IDE de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] proporciona comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad de IntelliSense con [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] también se puede usar para consultar los datos que se han consolidado de uno o más orígenes de datos.  Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos.  En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.  
  
## Consultar conjuntos de datos usando LINQ to DataSet  
 Antes de poder empezar a consultar un objeto <xref:System.Data.DataSet> usando [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], se debe rellenar el <xref:System.Data.DataSet>. Existen varias formas de cargar datos en un <xref:System.Data.DataSet>, como usar la clase <xref:System.Data.Common.DataAdapter> o [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  Cuando se han cargado los datos en un objeto <xref:System.Data.DataSet>, se puede empezar a realizar consultas en él.  La formulación de consultas usando [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] es similar a usar [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] en otros orígenes de datos habilitados para [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].  Se pueden realizar consultas de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] en tablas únicas en un <xref:System.Data.DataSet>o en más de una tabla usando los operadores de consulta estándar <xref:System.Linq.Enumerable.Join%2A>y <xref:System.Linq.Enumerable.GroupJoin%2A>.  
  
 Se admiten consultas de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] en objetos <xref:System.Data.DataSet> con tipo y sin tipo.  Si el esquema de <xref:System.Data.DataSet> es desconocido en tiempo de diseño de la aplicación, se recomienda un <xref:System.Data.DataSet> con tipo. En un <xref:System.Data.DataSet> con tipo, las tablas y las filas tienen miembros con tipo para cada una de las columnas, lo que hace que las consultas sean más sencillas y legibles.  
  
 Además de los operadores de consulta estándar implementados en System.Core.dll, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] agrega varias extensiones específicas de <xref:System.Data.DataSet> que hacen que realizar consultas en un conjunto de objetos <xref:System.Data.DataRow> sea sencillo.  Estas extensiones específicas de <xref:System.Data.DataSet> incluyen operadores para comparar secuencias de filas, así como métodos que proporcionan acceso a los valores de columna de un <xref:System.Data.DataRow>.  
  
## Aplicaciones con n niveles y LINQ to DataSet  
 Las aplicaciones de datos con n niveles son aplicaciones centradas en datos separadas en varias capas lógicas \(o niveles\).  Una aplicación con n capas típica incluye una capa de presentación, una capa media y una capa de datos.  Al separar los componentes de la aplicación en niveles independientes, se aumenta la facilidad de  mantenimiento y la escalabilidad de la aplicación.  Para obtener más información acerca de las aplicaciones de datos con n niveles, vea [Trabajar con conjuntos de datos en aplicaciones de n capas](../Topic/Work%20with%20datasets%20in%20n-tier%20applications.md).  
  
 En las aplicaciones con n niveles, a menudo se utiliza <xref:System.Data.DataSet> en el nivel medio para almacenar en caché información para una aplicación web.  La funcionalidad de consulta de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] se implementa mediante los métodos de extensión y <xref:System.Data.DataSet> de ADO.NET 2.0 existente.  
  
## Vea también  
 [Consultar DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ a SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)