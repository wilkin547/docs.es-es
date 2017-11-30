---
title: "Expresión de tipo &lt;tipo&gt; no es consultable"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords: BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f2b98bf48f0b3965929f9211c2944ff97754f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="f7f5e-102">Expresión de tipo &lt;tipo&gt; no es consultable</span><span class="sxs-lookup"><span data-stu-id="f7f5e-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="f7f5e-103">Expresión de tipo \<tipo > no es consultable.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="f7f5e-104">Asegúrese de que no falta una importación de referencia o espacio de nombres de ensamblado para el proveedor LINQ.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="f7f5e-105">Puede consultables tipos se definen en el <xref:System.Linq>, <xref:System.Data.Linq>, y <xref:System.Xml.Linq> los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="f7f5e-106">Debe importar uno o varios de estos espacios de nombres para realizar consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="f7f5e-107">El <xref:System.Linq> espacio de nombres permite a los objetos de consulta como colecciones y matrices mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="f7f5e-108">El <xref:System.Data.Linq> espacio de nombres le permite consultar conjuntos de datos de ADO.NET y bases de datos de SQL Server mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="f7f5e-109">El <xref:System.Xml.Linq> espacio de nombres permite consultar XML usando LINQ y para usar características XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="f7f5e-110">**Id. de error:** BC36593</span><span class="sxs-lookup"><span data-stu-id="f7f5e-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7f5e-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f7f5e-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="f7f5e-112">Agregar un `Import` instrucción para el <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq> espacio de nombres al archivo de código.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="f7f5e-113">También puede importar espacios de nombres para el proyecto mediante el **referencias** página del Diseñador de proyectos (**My Project**).</span><span class="sxs-lookup"><span data-stu-id="f7f5e-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="f7f5e-114">Asegúrese de que el tipo que se ha identificado como el origen de la consulta es un tipo consultable.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="f7f5e-115">Es decir, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f5e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7f5e-116">See Also</span></span>  
 <xref:System.Linq>  
 <xref:System.Data.Linq>  
 <xref:System.Xml.Linq>  
 [<span data-ttu-id="f7f5e-117">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7f5e-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="f7f5e-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="f7f5e-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="f7f5e-119">XML</span><span class="sxs-lookup"><span data-stu-id="f7f5e-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="f7f5e-120">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="f7f5e-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="f7f5e-121">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="f7f5e-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="f7f5e-122">Página Referencias, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7f5e-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
