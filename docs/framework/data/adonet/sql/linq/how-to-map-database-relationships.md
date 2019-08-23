---
title: Procedimiento para asignar relaciones de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: 42e7a715c8137574bff617715c1f174314080131
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943614"
---
# <a name="how-to-map-database-relationships"></a>Procedimiento para asignar relaciones de base de datos
Puede codificar como referencias de propiedad en la clase de entidad cualquier relación de datos que vaya a ser siempre la misma. En la base de datos de ejemplo Northwind, por ejemplo, dado que los clientes normalmente realizan pedidos, hay siempre una relación en el modelo entre los clientes y sus pedidos.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]define un <xref:System.Data.Linq.Mapping.AssociationAttribute> atributo para ayudar a representar tales relaciones. Este atributo se utiliza junto con los tipos <xref:System.Data.Linq.EntitySet%601> y <xref:System.Data.Linq.EntityRef%601> para representar lo que sería una relación de clave externa en una base de datos. Para obtener más información, vea la sección relativa al atributo de Asociación de [asignación basada en atributos](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
> Los valores de propiedad AssociationAttribute y ColumnAttribute Storage distinguen entre mayúsculas y minúsculas. Por ejemplo, asegúrese de que los valores utilizados en el atributo de la propiedad AssociationAttribute.Storage coinciden con el uso de mayúsculas y minúsculas para los nombres de propiedad correspondientes del resto del código. Esto se aplica a todos los lenguajes de programación de .NET, incluso aquellos que normalmente no distinguen mayúsculas de minúsculas, incluido Visual Basic. Para obtener más información acerca de la propiedad Storage, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 La mayoría de las relaciones son de uno a varios, como en el ejemplo que se incluye más adelante en este tema. También puede representar relaciones uno a uno y varios a varios de la manera siguiente:  
  
- Uno a uno: Representar este tipo de relación mediante la <xref:System.Data.Linq.EntitySet%601> inclusión de en ambos lados.  
  
     Por ejemplo, considere una `Customer` - `SecurityCode` relación creada para que el código de seguridad del cliente no se encuentre en la `Customer` tabla y solo personas autorizadas puedan acceder a él.  
  
- Varios a varios: En las relaciones de varios a varios, la clave principal de la tabla de vínculos (también denominada tabla de *Unión* ) suele estar formada por un compuesto de las claves externas de las otras dos tablas.  
  
     Por ejemplo, considere una `Employee` - `Project` relación de varios a varios formada por el uso de la `EmployeeProject`tabla de vínculos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requiere que tal relación se modele utilizando tres clases: `Employee`, `Project` y `EmployeeProject`. En este caso, al cambiar la relación entre `Employee` y `Project` puede parecer necesario actualizar la clave principal de `EmployeeProject`. Sin embargo, esta situación se modela mejor eliminando un `EmployeeProject` existente y creando un nuevo `EmployeeProject`.  
  
    > [!NOTE]
    > Las relaciones en las bases de datos relacionales se modelan normalmente como valores de clave externa que hacen referencia a claves principales de otras tablas. Para navegar entre ellos, asocie explícitamente las dos tablas mediante una operación de *combinación* relacional.  
    >   
    >  Los objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]de, por otro lado, se refieren entre sí mediante referencias de propiedad o colecciones de referencias que se navegan mediante la notación de *puntos* .  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de relación uno a varios, la clase `Customer` tiene una propiedad que declara la relación entre los clientes y sus pedidos.  La propiedad `Orders` es de tipo <xref:System.Data.Linq.EntitySet%601>. Este tipo indica que esta relación es de uno a varios (entre un cliente y varios pedidos). La propiedad <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> se utiliza para describir cómo se logra esta asociación, a saber, especificando el nombre de la propiedad de la clase relacionada que se va a comparar con ésta. En este ejemplo, se `CustomerID` compara la propiedad, de la misma forma que una *combinación* de base de datos compararía ese valor de columna.  
  
> [!NOTE]
> Si usa Visual Studio, puede usar la Object Relational Designer para crear una asociación entre clases.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 También puede invertir la situación. En lugar de utilizar la clase `Customer` para describir la asociación entre los clientes y los pedidos, puede utilizar la clase `Order`. La clase `Order` utiliza el tipo <xref:System.Data.Linq.EntityRef%601> para describir paso a paso la relación hasta el cliente, como se observa en el ejemplo de código siguiente.  
  
> [!NOTE]
> La <xref:System.Data.Linq.EntityRef%601> clase admite la *carga diferida*. Para obtener más información, *vea* [carga aplazada frente a carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos: Personalización de clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
