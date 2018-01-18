---
title: "Agregar lógica de negocios utilizando métodos parciales"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9704ad7d4030ee85701f1f95f87c539c1fbd0122
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="57c77-102">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="57c77-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="57c77-103">Puede personalizar [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] y C# generado código en su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyectos mediante *métodos parciales*.</span><span class="sxs-lookup"><span data-stu-id="57c77-103">You can customize [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="57c77-104">El código que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera define las firmas como parte de un método parcial.</span><span class="sxs-lookup"><span data-stu-id="57c77-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="57c77-105">Si desea implementar el método, puede agregar un método parcial propio.</span><span class="sxs-lookup"><span data-stu-id="57c77-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="57c77-106">Si no agrega su propia implementación, el compilador descarta la firma de método parcial y llama a los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57c77-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57c77-107">Si utiliza [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], puede usar [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para agregar funciones de validación y otras personalizaciones a las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="57c77-107">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="57c77-108">Por ejemplo, la asignación predeterminada para la clase `Customer` en la base de datos de ejemplo Northwind incluye el método parcial siguiente:</span><span class="sxs-lookup"><span data-stu-id="57c77-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="57c77-109">Puede implementar un método propio agregando código como el siguiente a su propia clase `Customer` parcial:</span><span class="sxs-lookup"><span data-stu-id="57c77-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="57c77-110">Este enfoque se usa normalmente en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar métodos predeterminados para `Insert`, `Update`, `Delete`y para validar las propiedades durante los eventos de ciclo de vida de objeto.</span><span class="sxs-lookup"><span data-stu-id="57c77-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="57c77-111">Para obtener más información, consulte [métodos parciales](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) o [parcial (método) (referencia de C#)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="57c77-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57c77-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57c77-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="57c77-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="57c77-113">Description</span></span>  
 <span data-ttu-id="57c77-114">En el ejemplo siguiente se muestra primero `ExampleClass` tal como se podría definir con una herramienta que genera código, como SQLMetal, y, a continuación, se muestra cómo se podría implementar solo uno de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="57c77-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="57c77-115">Código</span><span class="sxs-lookup"><span data-stu-id="57c77-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="57c77-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57c77-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="57c77-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="57c77-117">Description</span></span>  
 <span data-ttu-id="57c77-118">En el ejemplo siguiente se utiliza la relación entre las entidades `Shipper` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="57c77-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="57c77-119">Observe, entre los métodos, los métodos parciales, `InsertShipper` y `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="57c77-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="57c77-120">Estos métodos invalidan los métodos parciales predeterminados proporcionados por [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asignación.</span><span class="sxs-lookup"><span data-stu-id="57c77-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="57c77-121">Código</span><span class="sxs-lookup"><span data-stu-id="57c77-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="57c77-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="57c77-122">See Also</span></span>  
 [<span data-ttu-id="57c77-123">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="57c77-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="57c77-124">Personalización de operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="57c77-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
