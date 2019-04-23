---
title: No se puede consultar una expresión de tipo <type>
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 121c0a95a3a6bb695d9c73347c733cba215a0de4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304160"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="50b19-102">Expresión de tipo \<tipo > no es consultable</span><span class="sxs-lookup"><span data-stu-id="50b19-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="50b19-103">Expresión de tipo \<tipo > no es consultable.</span><span class="sxs-lookup"><span data-stu-id="50b19-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="50b19-104">Asegúrese de que no falta una importación de espacio de nombres o de referencia de ensamblado para el proveedor LINQ.</span><span class="sxs-lookup"><span data-stu-id="50b19-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="50b19-105">Puede consultables tipos se definen en el <xref:System.Linq>, <xref:System.Data.Linq>, y <xref:System.Xml.Linq> espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="50b19-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="50b19-106">Debe importar uno o varios de estos espacios de nombres para realizar consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="50b19-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="50b19-107">El <xref:System.Linq> espacio de nombres permite a los objetos de consulta como colecciones y matrices mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="50b19-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="50b19-108">El <xref:System.Data.Linq> espacio de nombres le permite consultar los conjuntos de datos de ADO.NET y las bases de datos de SQL Server mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="50b19-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="50b19-109">El <xref:System.Xml.Linq> espacio de nombres le permite consultar XML con LINQ y usar características XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="50b19-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="50b19-110">**Identificador de error:** BC36593</span><span class="sxs-lookup"><span data-stu-id="50b19-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="50b19-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="50b19-111">To correct this error</span></span>  
  
1. <span data-ttu-id="50b19-112">Agregar un `Import` instrucción para el <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq> espacio de nombres al archivo de código.</span><span class="sxs-lookup"><span data-stu-id="50b19-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="50b19-113">También puede importar los espacios de nombres para el proyecto mediante el **referencias** página del Diseñador de proyectos (**mi proyecto**).</span><span class="sxs-lookup"><span data-stu-id="50b19-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="50b19-114">Asegúrese de que el tipo que se ha identificado como el origen de la consulta es un tipo consultable.</span><span class="sxs-lookup"><span data-stu-id="50b19-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="50b19-115">Es decir, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="50b19-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b19-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="50b19-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="50b19-117">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50b19-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="50b19-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="50b19-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="50b19-119">XML</span><span class="sxs-lookup"><span data-stu-id="50b19-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="50b19-120">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="50b19-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="50b19-121">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="50b19-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="50b19-122">Página Referencias, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50b19-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
