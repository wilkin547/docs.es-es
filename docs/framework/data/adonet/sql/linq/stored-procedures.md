---
title: Procedimientos almacenados
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 9201965192f300de62679c1e5be75cf98a24e700
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360601"
---
# <a name="stored-procedures"></a><span data-ttu-id="0bb91-102">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="0bb91-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0bb91-103"> utiliza los métodos de su modelo de objetos para representar los procedimientos almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0bb91-103"> uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="0bb91-104">Los métodos se designan como procedimientos almacenados aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0bb91-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="0bb91-105">Para obtener más información, consulte [el modelo de LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="0bb91-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="0bb91-106">Los desarrolladores que utilizan Visual Studio utilizaría normalmente el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="0bb91-106">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map stored procedures.</span></span> <span data-ttu-id="0bb91-107">Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.</span><span class="sxs-lookup"><span data-stu-id="0bb91-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bb91-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0bb91-108">In This Section</span></span>  
 [<span data-ttu-id="0bb91-109">Devolución de conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="0bb91-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="0bb91-110">Describe cómo devolver filas de datos y cómo utilizar un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="0bb91-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="0bb91-111">Uso de procedimientos almacenados que toman parámetros</span><span class="sxs-lookup"><span data-stu-id="0bb91-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="0bb91-112">Describe cómo utilizar parámetros de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="0bb91-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="0bb91-113">Uso de procedimientos almacenados asignados en varias formas de resultados</span><span class="sxs-lookup"><span data-stu-id="0bb91-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="0bb91-114">Describe cómo hacer que se devuelvan varias formas en el mismo procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0bb91-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="0bb91-115">Uso de procedimientos almacenados asignados en formas de resultados secuenciales</span><span class="sxs-lookup"><span data-stu-id="0bb91-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="0bb91-116">Describe cómo obtener varias formas cuando se conoce la secuencia devuelta.</span><span class="sxs-lookup"><span data-stu-id="0bb91-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="0bb91-117">Personalización de operaciones utilizando procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="0bb91-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="0bb91-118">Describe cómo utilizar procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="0bb91-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="0bb91-119">Personalización de operaciones utilizando exclusivamente procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="0bb91-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="0bb91-120">Describe cómo utilizar únicamente procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="0bb91-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0bb91-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0bb91-121">Related Sections</span></span>  
 [<span data-ttu-id="0bb91-122">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="0bb91-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="0bb91-123">Proporciona información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bb91-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="0bb91-124">Tutorial: Usar solo procedimientos almacenados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bb91-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="0bb91-125">Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0bb91-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="0bb91-126">Tutorial: Usar solo procedimientos almacenados (C#)</span><span class="sxs-lookup"><span data-stu-id="0bb91-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="0bb91-127">Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en C#.</span><span class="sxs-lookup"><span data-stu-id="0bb91-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
