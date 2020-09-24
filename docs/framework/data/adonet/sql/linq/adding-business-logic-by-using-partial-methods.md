---
title: Agregar lógica de negocios utilizando métodos parciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 9ad3329c621b8bf8eaa0fd5f986ac7e8cff97d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156165"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="6e777-102">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="6e777-102">Adding Business Logic By Using Partial Methods</span></span>

<span data-ttu-id="6e777-103">Puede personalizar el código generado por C# y Visual Basic en los [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyectos mediante *métodos parciales*.</span><span class="sxs-lookup"><span data-stu-id="6e777-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="6e777-104">El código que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera define las firmas como parte de un método parcial.</span><span class="sxs-lookup"><span data-stu-id="6e777-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="6e777-105">Si desea implementar el método, puede agregar un método parcial propio.</span><span class="sxs-lookup"><span data-stu-id="6e777-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="6e777-106">Si no agrega su propia implementación, el compilador descarta la firma de método parcial y llama a los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e777-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e777-107">Si usa Visual Studio, puede usar el Object Relational Designer para agregar la validación y otras personalizaciones a las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="6e777-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="6e777-108">Por ejemplo, la asignación predeterminada para la clase `Customer` en la base de datos de ejemplo Northwind incluye el método parcial siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e777-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="6e777-109">Puede implementar un método propio agregando código como el siguiente a su propia clase `Customer` parcial:</span><span class="sxs-lookup"><span data-stu-id="6e777-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="6e777-110">Este enfoque se usa normalmente en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar los métodos predeterminados para `Insert` , `Update` , `Delete` y para validar las propiedades durante los eventos de ciclo de vida de los objetos.</span><span class="sxs-lookup"><span data-stu-id="6e777-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="6e777-111">Para obtener más información, vea [métodos parciales](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) o [partial (método, referencia de c#)](../../../../../csharp/language-reference/keywords/partial-method.md) (c#).</span><span class="sxs-lookup"><span data-stu-id="6e777-111">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e777-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e777-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6e777-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e777-113">Description</span></span>  

 <span data-ttu-id="6e777-114">En el ejemplo siguiente se muestra primero `ExampleClass` tal como se podría definir con una herramienta que genera código, como SQLMetal, y, a continuación, se muestra cómo se podría implementar solo uno de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="6e777-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6e777-115">Código</span><span class="sxs-lookup"><span data-stu-id="6e777-115">Code</span></span>  

 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="6e777-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e777-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6e777-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e777-117">Description</span></span>  

 <span data-ttu-id="6e777-118">En el ejemplo siguiente se utiliza la relación entre las entidades `Shipper` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="6e777-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="6e777-119">Observe, entre los métodos, los métodos parciales, `InsertShipper` y `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="6e777-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="6e777-120">Estos métodos reemplazan a los métodos parciales predeterminados proporcionados por la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asignación.</span><span class="sxs-lookup"><span data-stu-id="6e777-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6e777-121">Código</span><span class="sxs-lookup"><span data-stu-id="6e777-121">Code</span></span>  

 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6e777-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e777-122">See also</span></span>

- [<span data-ttu-id="6e777-123">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="6e777-123">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="6e777-124">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="6e777-124">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
