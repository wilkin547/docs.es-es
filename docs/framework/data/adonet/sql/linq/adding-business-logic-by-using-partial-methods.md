---
title: Agregar lógica de negocios utilizando métodos parciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: ea7dbc4f760a446440cb7291413d69b1202f80e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162664"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="a8152-102">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="a8152-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="a8152-103">Puede personalizar Visual Basic y C# genera código en su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyectos mediante el uso de *métodos parciales*.</span><span class="sxs-lookup"><span data-stu-id="a8152-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="a8152-104">El código que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera define las firmas como parte de un método parcial.</span><span class="sxs-lookup"><span data-stu-id="a8152-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="a8152-105">Si desea implementar el método, puede agregar un método parcial propio.</span><span class="sxs-lookup"><span data-stu-id="a8152-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="a8152-106">Si no agrega su propia implementación, el compilador descarta la firma de método parcial y llama a los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8152-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8152-107">Si utiliza Visual Studio, puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para agregar validación y otras personalizaciones a las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="a8152-107">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="a8152-108">Por ejemplo, la asignación predeterminada para la clase `Customer` en la base de datos de ejemplo Northwind incluye el método parcial siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8152-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="a8152-109">Puede implementar un método propio agregando código como el siguiente a su propia clase `Customer` parcial:</span><span class="sxs-lookup"><span data-stu-id="a8152-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="a8152-110">Este enfoque se utiliza normalmente en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar los métodos predeterminados para `Insert`, `Update`, `Delete`y para validar las propiedades durante los eventos de ciclo de vida del objeto.</span><span class="sxs-lookup"><span data-stu-id="a8152-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="a8152-111">Para obtener más información, consulte [métodos parciales](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) o [partial (método) (C# referencia)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="a8152-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8152-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8152-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a8152-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8152-113">Description</span></span>  
 <span data-ttu-id="a8152-114">En el ejemplo siguiente se muestra primero `ExampleClass` tal como se podría definir con una herramienta que genera código, como SQLMetal, y, a continuación, se muestra cómo se podría implementar solo uno de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="a8152-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a8152-115">Código</span><span class="sxs-lookup"><span data-stu-id="a8152-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="a8152-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8152-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a8152-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8152-117">Description</span></span>  
 <span data-ttu-id="a8152-118">En el ejemplo siguiente se utiliza la relación entre las entidades `Shipper` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="a8152-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="a8152-119">Observe, entre los métodos, los métodos parciales, `InsertShipper` y `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="a8152-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="a8152-120">Estos métodos invalidan los métodos parciales predeterminados proporcionados por [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asignación.</span><span class="sxs-lookup"><span data-stu-id="a8152-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a8152-121">Código</span><span class="sxs-lookup"><span data-stu-id="a8152-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a8152-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8152-122">See also</span></span>

- [<span data-ttu-id="a8152-123">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="a8152-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="a8152-124">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="a8152-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
