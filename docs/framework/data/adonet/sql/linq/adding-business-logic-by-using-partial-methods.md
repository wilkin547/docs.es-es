---
title: Agregar lógica de negocios utilizando métodos parciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: db18c48d697ae79f8c33c1674544f81cdd1c426a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361456"
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Agregar lógica de negocios utilizando métodos parciales
Puede personalizar código en Visual Basic y C# generan por la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyectos mediante *métodos parciales*. El código que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera define las firmas como parte de un método parcial. Si desea implementar el método, puede agregar un método parcial propio. Si no agrega su propia implementación, el compilador descarta la firma de método parcial y llama a los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
>  Si se utiliza Visual Studio, puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para agregar validación y otras personalizaciones a las clases de entidad.  
  
 Por ejemplo, la asignación predeterminada para la clase `Customer` en la base de datos de ejemplo Northwind incluye el método parcial siguiente:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Puede implementar un método propio agregando código como el siguiente a su propia clase `Customer` parcial:  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Este enfoque se usa normalmente en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar métodos predeterminados para `Insert`, `Update`, `Delete`y para validar las propiedades durante los eventos de ciclo de vida de objeto.  
  
 Para obtener más información, consulte [métodos parciales](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) o [parcial (método) (referencia de C#)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se muestra primero `ExampleClass` tal como se podría definir con una herramienta que genera código, como SQLMetal, y, a continuación, se muestra cómo se podría implementar solo uno de los dos métodos.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se utiliza la relación entre las entidades `Shipper` y `Order`. Observe, entre los métodos, los métodos parciales, `InsertShipper` y `DeleteShipper`. Estos métodos invalidan los métodos parciales predeterminados proporcionados por [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asignación.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Realización y envío de cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [Personalización de operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
