---
title: Introducción a LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
ms.openlocfilehash: c74c4d3261354bdd2b8194371b4b37f014397e85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626568"
---
# <a name="introduction-to-linq-c"></a><span data-ttu-id="998d4-102">Introducción a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="998d4-102">Introduction to LINQ (C#)</span></span>
<span data-ttu-id="998d4-103">Language-Integrated Query (LINQ) es una innovación que se ha presentado en la versión 3.5 de .NET Framework que reduce la distancia entre el mundo de los objetos y el de los datos.</span><span class="sxs-lookup"><span data-stu-id="998d4-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="998d4-104">Tradicionalmente, las consultas con datos se expresaban como cadenas simples sin comprobación de tipos en tiempo de compilación ni compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="998d4-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="998d4-105">Además, tendrá que aprender un lenguaje de consulta diferente para cada tipo de origen de datos: bases de datos SQL, documentos XML, varios servicios web y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="998d4-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="998d4-106">LINQ hace que una *consulta* sea una construcción de lenguaje de primera clase en C#.</span><span class="sxs-lookup"><span data-stu-id="998d4-106">LINQ makes a *query* a first-class language construct in C#.</span></span> <span data-ttu-id="998d4-107">Escribe consultas en colecciones de objetos fuertemente tipadas con palabras clave del lenguaje y operadores familiares.</span><span class="sxs-lookup"><span data-stu-id="998d4-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="998d4-108">Puede escribir consultas LINQ en C# para bases de datos de SQL Server, documentos XML, conjuntos de datos ADO.NET y cualquier colección de objetos que admita <xref:System.Collections.IEnumerable> o la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="998d4-108">You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="998d4-109">La compatibilidad con LINQ también se proporciona por terceros para muchos servicios web y otras implementaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="998d4-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="998d4-110">Puede usar consultas LINQ en proyectos nuevos, o junto con otras consultas que no son de LINQ en proyectos existentes.</span><span class="sxs-lookup"><span data-stu-id="998d4-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="998d4-111">El único requisito es que el proyecto tenga como destino .NET Framework 3.5 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="998d4-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="998d4-112">En la siguiente ilustración de Visual Studio se muestra una consulta LINQ parcialmente completa en una base de datos de SQL Server en C# y Visual Basic con la comprobación de tipos completa y la compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="998d4-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="998d4-113">![Consulta LINQ con Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="998d4-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="998d4-114">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="998d4-114">Next Steps</span></span>  
 <span data-ttu-id="998d4-115">Para obtener más información sobre LINQ, empiece a familiarizarse con algunos conceptos básicos en la sección Introducción de [Introducción a LINQ en C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) y, después, lea la documentación de la tecnología de LINQ en la que esté interesado:</span><span class="sxs-lookup"><span data-stu-id="998d4-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="998d4-116">Bases de datos de SQL Server: [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="998d4-116">SQL Server databases: [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)</span></span>  
  
-   <span data-ttu-id="998d4-117">Documentos XML: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="998d4-117">XML documents: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="998d4-118">Conjuntos de datos de ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="998d4-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="998d4-119">Colecciones .NET, archivos y cadenas, entre otros: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="998d4-119">.NET collections, files, strings and so on: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="998d4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="998d4-120">See also</span></span>

- [<span data-ttu-id="998d4-121">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="998d4-121">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
