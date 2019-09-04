---
title: Agregar lógica de negocios utilizando métodos parciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 251d7a05971ff7940f85ec9d555d26f2e57067c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248134"
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Agregar lógica de negocios utilizando métodos parciales
Puede personalizar Visual Basic y C# el código generado en los [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyectos mediante *métodos parciales*. El código que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera define las firmas como parte de un método parcial. Si desea implementar el método, puede agregar un método parcial propio. Si no agrega su propia implementación, el compilador descarta la firma de método parcial y llama a los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
> Si usa Visual Studio, puede usar el Object Relational Designer para agregar la validación y otras personalizaciones a las clases de entidad.  
  
 Por ejemplo, la asignación predeterminada para la clase `Customer` en la base de datos de ejemplo Northwind incluye el método parcial siguiente:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Puede implementar un método propio agregando código como el siguiente a su propia clase `Customer` parcial:  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Este enfoque se usa normalmente en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar los métodos `Insert`predeterminados para, `Update`, `Delete`y para validar las propiedades durante los eventos de ciclo de vida de los objetos.  
  
 Para obtener más información, vea [métodos parciales](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) o [partial (métodoC# ) (referencia)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 En el ejemplo siguiente se muestra primero `ExampleClass` tal como se podría definir con una herramienta que genera código, como SQLMetal, y, a continuación, se muestra cómo se podría implementar solo uno de los dos métodos.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 En el ejemplo siguiente se utiliza la relación entre las entidades `Shipper` y `Order`. Observe, entre los métodos, los métodos parciales, `InsertShipper` y `DeleteShipper`. Estos métodos reemplazan a los métodos parciales predeterminados proporcionados por [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la asignación.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Realización y envío de cambios de datos](making-and-submitting-data-changes.md)
- [Personalización de operaciones de actualización, inserción y eliminación](customizing-insert-update-and-delete-operations.md)
