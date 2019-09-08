---
title: Procedimientos almacenados
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 80ea105eef33ebb2a0e52d91a631258400ea3dff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792481"
---
# <a name="stored-procedures"></a><span data-ttu-id="a9998-102">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="a9998-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a9998-103">utiliza métodos en el modelo de objetos para representar procedimientos almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a9998-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="a9998-104">Los métodos se designan como procedimientos almacenados aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a9998-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="a9998-105">Para obtener más información, vea [el LINQ to SQL modelo de objetos](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="a9998-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="a9998-106">Los desarrolladores que usan Visual Studio normalmente usarían el Object Relational Designer para asignar procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="a9998-106">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="a9998-107">Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.</span><span class="sxs-lookup"><span data-stu-id="a9998-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9998-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a9998-108">In This Section</span></span>  
 [<span data-ttu-id="a9998-109">Cómo: Devolver conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="a9998-109">How to: Return Rowsets</span></span>](how-to-return-rowsets.md)  
 <span data-ttu-id="a9998-110">Describe cómo devolver filas de datos y cómo utilizar un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="a9998-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="a9998-111">Cómo: Usar procedimientos almacenados que toman parámetros</span><span class="sxs-lookup"><span data-stu-id="a9998-111">How to: Use Stored Procedures that Take Parameters</span></span>](how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="a9998-112">Describe cómo utilizar parámetros de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="a9998-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="a9998-113">Cómo: Usar procedimientos almacenados asignados para varias formas de resultados</span><span class="sxs-lookup"><span data-stu-id="a9998-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="a9998-114">Describe cómo hacer que se devuelvan varias formas en el mismo procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a9998-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="a9998-115">Cómo: Usar procedimientos almacenados asignados para formas de resultados secuenciales</span><span class="sxs-lookup"><span data-stu-id="a9998-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="a9998-116">Describe cómo obtener varias formas cuando se conoce la secuencia devuelta.</span><span class="sxs-lookup"><span data-stu-id="a9998-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="a9998-117">Personalización de operaciones utilizando procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="a9998-117">Customizing Operations By Using Stored Procedures</span></span>](customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="a9998-118">Describe cómo utilizar procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="a9998-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="a9998-119">Personalización de operaciones utilizando exclusivamente procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="a9998-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="a9998-120">Describe cómo utilizar únicamente procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="a9998-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a9998-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a9998-121">Related Sections</span></span>  
 [<span data-ttu-id="a9998-122">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="a9998-122">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="a9998-123">Proporciona información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9998-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="a9998-124">Tutorial: Usar solo procedimientos almacenados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9998-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="a9998-125">Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a9998-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a9998-126">Tutorial: Usar solo procedimientos almacenados (C#)</span><span class="sxs-lookup"><span data-stu-id="a9998-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="a9998-127">Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en C#.</span><span class="sxs-lookup"><span data-stu-id="a9998-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
