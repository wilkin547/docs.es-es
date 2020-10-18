---
title: No se puede consultar una expresión de tipo <type>
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: d605243c213166f20592fdc440a3362f957ebbf2
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163069"
---
# <a name="bc36593-expression-of-type-type-is-not-queryable"></a><span data-ttu-id="d0fdf-102">BC36593: la expresión de tipo \<type> no es consultable</span><span class="sxs-lookup"><span data-stu-id="d0fdf-102">BC36593: Expression of type \<type> is not queryable</span></span>

<span data-ttu-id="d0fdf-103">La expresión de tipo \<type> no es consultable.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="d0fdf-104">Asegúrese de que no falta una referencia de ensamblado o una importación de espacio de nombres para el proveedor LINQ.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>

 <span data-ttu-id="d0fdf-105">Los tipos consultables se definen en <xref:System.Linq> los <xref:System.Data.Linq> espacios de <xref:System.Xml.Linq> nombres, y.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="d0fdf-106">Debe importar uno o varios de estos espacios de nombres para realizar consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>

 <span data-ttu-id="d0fdf-107">El <xref:System.Linq> espacio de nombres permite consultar objetos como colecciones y matrices mediante Linq.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>

 <span data-ttu-id="d0fdf-108">El <xref:System.Data.Linq> espacio de nombres permite consultar conjuntos de datos de ADO.net y bases de datos de SQL Server mediante Linq.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>

 <span data-ttu-id="d0fdf-109">El <xref:System.Xml.Linq> espacio de nombres permite consultar XML mediante LINQ y usar características XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>

 <span data-ttu-id="d0fdf-110">**Identificador de error:** BC36593</span><span class="sxs-lookup"><span data-stu-id="d0fdf-110">**Error ID:** BC36593</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d0fdf-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d0fdf-111">To correct this error</span></span>

1. <span data-ttu-id="d0fdf-112">Agregue una `Import` instrucción para el <xref:System.Linq> <xref:System.Data.Linq> espacio de nombres, o <xref:System.Xml.Linq> al archivo de código.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="d0fdf-113">También puede importar espacios de nombres para el proyecto mediante la página **referencias** del diseñador de proyectos (**mi proyecto**).</span><span class="sxs-lookup"><span data-stu-id="d0fdf-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>

2. <span data-ttu-id="d0fdf-114">Asegúrese de que el tipo que ha identificado como el origen de la consulta es un tipo consultable.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="d0fdf-115">Es decir, un tipo que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="d0fdf-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0fdf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0fdf-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="d0fdf-117">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d0fdf-117">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d0fdf-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="d0fdf-118">LINQ</span></span>](../../programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="d0fdf-119">XML</span><span class="sxs-lookup"><span data-stu-id="d0fdf-119">XML</span></span>](../../programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="d0fdf-120">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="d0fdf-120">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="d0fdf-121">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="d0fdf-121">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="d0fdf-122">Página Referencias, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0fdf-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
