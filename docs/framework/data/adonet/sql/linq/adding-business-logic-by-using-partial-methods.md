---
description: Más información acerca de cómo agregar lógica de negocios mediante métodos parciales
title: Agregar lógica de negocios utilizando métodos parciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: c34d0d25fa9dba074f1c7ff2abe2e9e24c931a8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672275"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="ca957-103">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="ca957-103">Adding Business Logic By Using Partial Methods</span></span>

<span data-ttu-id="ca957-104">Puede personalizar el código generado por C# y Visual Basic en los [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyectos mediante *métodos parciales*.</span><span class="sxs-lookup"><span data-stu-id="ca957-104">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="ca957-105">El código que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera define las firmas como parte de un método parcial.</span><span class="sxs-lookup"><span data-stu-id="ca957-105">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="ca957-106">Si desea implementar el método, puede agregar un método parcial propio.</span><span class="sxs-lookup"><span data-stu-id="ca957-106">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="ca957-107">Si no agrega su propia implementación, el compilador descarta la firma de método parcial y llama a los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca957-107">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca957-108">Si usa Visual Studio, puede usar el Object Relational Designer para agregar la validación y otras personalizaciones a las clases de entidad.</span><span class="sxs-lookup"><span data-stu-id="ca957-108">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="ca957-109">Por ejemplo, la asignación predeterminada para la clase `Customer` en la base de datos de ejemplo Northwind incluye el método parcial siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca957-109">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="ca957-110">Puede implementar un método propio agregando código como el siguiente a su propia clase `Customer` parcial:</span><span class="sxs-lookup"><span data-stu-id="ca957-110">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="ca957-111">Este enfoque se usa normalmente en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar los métodos predeterminados para `Insert` , `Update` , `Delete` y para validar las propiedades durante los eventos de ciclo de vida de los objetos.</span><span class="sxs-lookup"><span data-stu-id="ca957-111">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="ca957-112">Para obtener más información, vea [métodos parciales](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) o [partial (método, referencia de c#)](../../../../../csharp/language-reference/keywords/partial-method.md) (c#).</span><span class="sxs-lookup"><span data-stu-id="ca957-112">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca957-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca957-113">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ca957-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca957-114">Description</span></span>  

 <span data-ttu-id="ca957-115">En el ejemplo siguiente se muestra primero `ExampleClass` tal como se podría definir con una herramienta que genera código, como SQLMetal, y, a continuación, se muestra cómo se podría implementar solo uno de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="ca957-115">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ca957-116">Código</span><span class="sxs-lookup"><span data-stu-id="ca957-116">Code</span></span>  

 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="ca957-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca957-117">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ca957-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca957-118">Description</span></span>  

 <span data-ttu-id="ca957-119">En el ejemplo siguiente se utiliza la relación entre las entidades `Shipper` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="ca957-119">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="ca957-120">Observe, entre los métodos, los métodos parciales, `InsertShipper` y `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="ca957-120">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="ca957-121">Estos métodos reemplazan a los métodos parciales predeterminados proporcionados por la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asignación.</span><span class="sxs-lookup"><span data-stu-id="ca957-121">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ca957-122">Código</span><span class="sxs-lookup"><span data-stu-id="ca957-122">Code</span></span>  

 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ca957-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca957-123">See also</span></span>

- [<span data-ttu-id="ca957-124">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="ca957-124">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="ca957-125">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="ca957-125">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
