---
title: Procedimientos almacenados
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: b06dc19aa8b767da6a1c6b00bd5b465465db6060
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742836"
---
# <a name="stored-procedures"></a><span data-ttu-id="73087-102">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="73087-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="73087-103">utiliza los métodos de su modelo de objetos para representar los procedimientos almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="73087-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="73087-104">Los métodos se designan como procedimientos almacenados aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="73087-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="73087-105">Para obtener más información, consulte [el modelo LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="73087-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="73087-106">Los desarrolladores que usan Visual Studio normalmente usaría el Object Relational Designer para asignar procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="73087-106">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="73087-107">Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.</span><span class="sxs-lookup"><span data-stu-id="73087-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73087-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="73087-108">In This Section</span></span>  
 [<span data-ttu-id="73087-109">Procedimientos: Devolver conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="73087-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="73087-110">Describe cómo devolver filas de datos y cómo utilizar un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="73087-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="73087-111">Cómo: Usar procedimientos almacenados que toman parámetros</span><span class="sxs-lookup"><span data-stu-id="73087-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="73087-112">Describe cómo utilizar parámetros de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="73087-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="73087-113">Cómo: Usar procedimientos almacenados asignados en varias formas de resultados</span><span class="sxs-lookup"><span data-stu-id="73087-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="73087-114">Describe cómo hacer que se devuelvan varias formas en el mismo procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="73087-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="73087-115">Cómo: Usar procedimientos almacenados asignados en formas de resultados secuenciales</span><span class="sxs-lookup"><span data-stu-id="73087-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="73087-116">Describe cómo obtener varias formas cuando se conoce la secuencia devuelta.</span><span class="sxs-lookup"><span data-stu-id="73087-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="73087-117">Personalización de operaciones utilizando procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="73087-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="73087-118">Describe cómo utilizar procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="73087-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="73087-119">Personalización de operaciones utilizando exclusivamente procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="73087-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="73087-120">Describe cómo utilizar únicamente procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="73087-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="73087-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="73087-121">Related Sections</span></span>  
 [<span data-ttu-id="73087-122">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="73087-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="73087-123">Proporciona información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73087-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="73087-124">Tutorial: Usar solo procedimientos almacenados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73087-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="73087-125">Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="73087-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="73087-126">Tutorial: Usar solo procedimientos almacenados (C#)</span><span class="sxs-lookup"><span data-stu-id="73087-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="73087-127">Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en C#.</span><span class="sxs-lookup"><span data-stu-id="73087-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
