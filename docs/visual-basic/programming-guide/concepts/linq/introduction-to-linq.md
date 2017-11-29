---
title: "Introducción a LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3edb26616bf53be8a26522775effd079fafbac97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="ba668-102">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba668-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="ba668-103">Language-Integrated Query (LINQ) es una innovación que se ha presentado en la versión 3.5 de .NET Framework que reduce la distancia entre el mundo de los objetos y el de los datos.</span><span class="sxs-lookup"><span data-stu-id="ba668-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="ba668-104">Tradicionalmente, las consultas con datos se expresaban como cadenas simples sin comprobación de tipos en tiempo de compilación ni compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ba668-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="ba668-105">Además, tiene que aprender un lenguaje de consultas diferente para cada tipo de origen de datos: bases de datos SQL, documentos XML y varios servicios web, entre otros.</span><span class="sxs-lookup"><span data-stu-id="ba668-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="ba668-106">LINQ hace un *consulta* una construcción de lenguaje de primera clase en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ba668-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="ba668-107">Escribe consultas en colecciones de objetos fuertemente tipadas con palabras clave del lenguaje y operadores familiares.</span><span class="sxs-lookup"><span data-stu-id="ba668-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="ba668-108">Puede escribir consultas LINQ en Visual Basic para las bases de datos SQL Server, documentos XML, conjuntos de datos ADO.NET y cualquier colección de objetos que admite <xref:System.Collections.IEnumerable> o la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="ba668-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="ba668-109">La compatibilidad con LINQ también se proporciona por terceros para muchos servicios web y otras implementaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba668-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="ba668-110">Puede usar consultas LINQ en proyectos nuevos, o junto con otras consultas que no son de LINQ en proyectos existentes.</span><span class="sxs-lookup"><span data-stu-id="ba668-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="ba668-111">El único requisito es que el proyecto tenga como destino .NET Framework 3.5 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ba668-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="ba668-112">En la siguiente ilustración de Visual Studio se muestra una consulta LINQ parcialmente completa en una base de datos de SQL Server en C# y Visual Basic con la comprobación de tipos completa y la compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ba668-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="ba668-113">![Consulta LINQ con Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="ba668-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ba668-114">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ba668-114">Next Steps</span></span>  
 <span data-ttu-id="ba668-115">Para obtener más detalles acerca de LINQ, empiece por familiarizarse con algunos conceptos básicos en la sección Introducción [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), y, a continuación, lea la documentación de la tecnología LINQ en el que esté ¿está interesado:</span><span class="sxs-lookup"><span data-stu-id="ba668-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="ba668-116">Bases de datos de SQL Server: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="ba668-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="ba668-117">Documentos XML: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="ba668-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="ba668-118">Conjuntos de datos ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="ba668-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="ba668-119">Colecciones. NET, archivos, cadenas y así sucesivamente: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="ba668-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba668-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba668-120">See Also</span></span>  
 [<span data-ttu-id="ba668-121">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba668-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
