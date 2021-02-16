---
description: 'Más información sobre: Introducción a LINQ (Visual Basic)'
title: Introducción a LINQ
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: b6be93bbf9b458ca19068961617ee08f67601edc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426795"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="e6edf-103">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6edf-103">Introduction to LINQ (Visual Basic)</span></span>

<span data-ttu-id="e6edf-104">Language-Integrated Query (LINQ) es una innovación que se ha presentado en la versión 3.5 de .NET Framework que reduce la distancia entre el mundo de los objetos y el de los datos.</span><span class="sxs-lookup"><span data-stu-id="e6edf-104">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="e6edf-105">Tradicionalmente, las consultas con datos se expresaban como cadenas simples sin comprobación de tipos en tiempo de compilación ni compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e6edf-105">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="e6edf-106">Además, tendrá que aprender un lenguaje de consulta diferente para cada tipo de origen de datos: bases de datos SQL, documentos XML, varios servicios web y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="e6edf-106">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="e6edf-107">LINQ realiza una *consulta* en una construcción de lenguaje de primera clase en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e6edf-107">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="e6edf-108">Escribe consultas en colecciones de objetos fuertemente tipadas con palabras clave del lenguaje y operadores familiares.</span><span class="sxs-lookup"><span data-stu-id="e6edf-108">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="e6edf-109">Puede escribir consultas LINQ en Visual Basic para bases de datos de SQL Server, documentos XML, conjuntos de datos ADO.NET y cualquier colección de objetos que admita <xref:System.Collections.IEnumerable> o la <xref:System.Collections.Generic.IEnumerable%601> interfaz genérica.</span><span class="sxs-lookup"><span data-stu-id="e6edf-109">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="e6edf-110">La compatibilidad con LINQ también se proporciona por terceros para muchos servicios web y otras implementaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e6edf-110">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="e6edf-111">Puede usar consultas LINQ en proyectos nuevos, o junto con otras consultas que no son de LINQ en proyectos existentes.</span><span class="sxs-lookup"><span data-stu-id="e6edf-111">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="e6edf-112">El único requisito es que el proyecto tenga como destino .NET Framework 3.5 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e6edf-112">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="e6edf-113">En la siguiente ilustración de Visual Studio se muestra una consulta LINQ parcialmente completa en una base de datos de SQL Server en C# y Visual Basic con la comprobación de tipos completa y la compatibilidad con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e6edf-113">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Diagrama en el que se muestra una consulta LINQ con IntelliSense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="e6edf-115">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e6edf-115">Next Steps</span></span>  

 <span data-ttu-id="e6edf-116">Para obtener más información sobre LINQ, empiece a familiarizarse con algunos conceptos básicos de la sección Introducción [Introducción con LINQ en Visual Basic](getting-started-with-linq.md)y, a continuación, lea la documentación de la tecnología de LINQ en la que está interesado:</span><span class="sxs-lookup"><span data-stu-id="e6edf-116">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="e6edf-117">Bases de datos de SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="e6edf-117">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="e6edf-118">Documentos XML: [LINQ to XML (Visual Basic)](../../../../standard/linq/linq-xml-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e6edf-118">XML documents: [LINQ to XML (Visual Basic)](../../../../standard/linq/linq-xml-overview.md)</span></span>  
  
- <span data-ttu-id="e6edf-119">Conjuntos de datos ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="e6edf-119">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="e6edf-120">Colecciones, archivos, cadenas de .NET, etc.: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="e6edf-120">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6edf-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6edf-121">See also</span></span>

- [<span data-ttu-id="e6edf-122">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6edf-122">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
