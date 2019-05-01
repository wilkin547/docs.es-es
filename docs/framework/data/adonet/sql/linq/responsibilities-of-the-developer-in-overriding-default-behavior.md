---
title: Responsabilidades del desarrollador al invalidar un comportamiento predeterminado
ms.date: 03/30/2017
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
ms.openlocfilehash: 12ea526d71946cdc7ab821f5e38948fcbb57d158
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033493"
---
# <a name="responsibilities-of-the-developer-in-overriding-default-behavior"></a>Responsabilidades del desarrollador al invalidar un comportamiento predeterminado
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no aplica los siguientes requisitos, pero el comportamiento es indefinido si no se cumplen estos requisitos.  
  
- El método de invalidación no debe llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> o <xref:System.Data.Linq.Table%601.Attach%2A>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] produce una excepción si se llama a estos métodos en un método de invalidación.  
  
- No se pueden utilizar métodos de invalidación para iniciar, confirmar o detener una transacción. La operación <xref:System.Data.Linq.DataContext.SubmitChanges%2A> se realiza bajo una transacción. Una transacción anidada interna puede interferir con la transacción externa. Los métodos de invalidación de carga solo pueden iniciar una transacción después de determinar que la operación no se realiza en <xref:System.Transactions.Transaction>.  
  
- Se espera que los métodos de invalidación sigan la asignación de simultaneidad optimista aplicable. Se espera que el método de invalidación inicie <xref:System.Data.Linq.ChangeConflictException> cuando se produzca un conflicto de simultaneidad optimista. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] detecta esta excepción, por lo que se puede procesar correctamente el <xref:System.Data.Linq.DataContext.SubmitChanges%2A> opción proporcionada en <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
- Se espera que los métodos de invalidación de creación (`Insert`) y de actualización (`Update`) devuelvan los valores de las columnas generadas por la base de datos a los miembros de objeto correspondientes cuando la operación se complete.  
  
     Por ejemplo, si `Order.OrderID` se asigna a una columna de identidad (*autoincrement* clave principal), el `InsertOrder()` método de invalidación debe recuperar el identificador generado por base de datos y establezca el `Order.OrderID` miembro para ese identificador. De igual forma, los miembros de marca de tiempo deben estar actualizados con los valores de marca de tiempo generados por la base de datos para garantizar que los objetos actualizados sean coherentes. Si no se propagan los valores generados por la base de datos, puede haber incoherencias entre la base de datos y los objetos de los que <xref:System.Data.Linq.DataContext> realiza un seguimiento.  
  
- Es el usuario quien debe invocar la API dinámica correcta. Por ejemplo, en el método de invalidación de actualización, solo se puede llamar al método <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no detecta ni comprueba si el método dinámico invocado coincide con la operación aplicable. Los resultados no están definidos si se llama a un método no aplicable (por ejemplo, <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> para un objeto que se va a actualizar).  
  
- Finalmente, se espera que el método de invalidación realice la operación indicada. Las semántica de las operaciones de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], como la carga diligente, la carga aplazada y <xref:System.Data.Linq.DataContext.SubmitChanges%2A> requieren que los métodos de invalidación proporcionen el servicio indicado. Por ejemplo, una invalidación de carga que solo devuelva una colección vacía sin comprobar el contenido en la base de datos probablemente generará datos incoherentes.  
  
## <a name="see-also"></a>Vea también

- [Personalización de operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
