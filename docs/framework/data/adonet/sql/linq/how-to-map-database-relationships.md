---
title: 'Cómo: Asignar relaciones de base de datos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: c89fb3e11ae8e0f8ea37727446cdf65db9499a1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148379"
---
# <a name="how-to-map-database-relationships"></a>Cómo: Asignar relaciones de base de datos
Puede codificar como referencias de propiedad en la clase de entidad cualquier relación de datos que vaya a ser siempre la misma. En la base de datos de ejemplo Northwind, por ejemplo, dado que los clientes normalmente realizan pedidos, hay siempre una relación en el modelo entre los clientes y sus pedidos.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]define <xref:System.Data.Linq.Mapping.AssociationAttribute> un atributo para ayudar a representar dichas relaciones. Este atributo se utiliza junto con los tipos <xref:System.Data.Linq.EntitySet%601> y <xref:System.Data.Linq.EntityRef%601> para representar lo que sería una relación de clave externa en una base de datos. Para obtener más información, consulte la sección Atributo de asociación de [Asignación basada en atributos](attribute-based-mapping.md).  
  
> [!NOTE]
> Los valores de propiedad AssociationAttribute y ColumnAttribute Storage distinguen entre mayúsculas y minúsculas. Por ejemplo, asegúrese de que los valores utilizados en el atributo de la propiedad AssociationAttribute.Storage coinciden con el uso de mayúsculas y minúsculas para los nombres de propiedad correspondientes del resto del código. Esto se aplica a todos los lenguajes de programación .NET, incluso aquellos que normalmente no distinguen entre mayúsculas y minúsculas, incluido Visual Basic. Para obtener más información acerca de la propiedad Storage, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 La mayoría de las relaciones son de uno a varios, como en el ejemplo que se incluye más adelante en este tema. También puede representar relaciones uno a uno y varios a varios de la manera siguiente:  
  
- Uno a uno: para representar este tipo de relación incluya <xref:System.Data.Linq.EntitySet%601> en ambos lados.  
  
     Por ejemplo, `Customer` - `SecurityCode` considere una relación, creada para que el código `Customer` de seguridad del cliente no se encuentre en la tabla y solo puedan tener acceso a ellos las personas autorizadas.  
  
- Varios a varios: en las relaciones de varios a varios, la clave principal de la tabla de vínculos (también denominada tabla de *cruce)* a menudo está formada por un compuesto de las claves externas de las otras dos tablas.  
  
     Por ejemplo, `Employee` - `Project` considere una relación de varios a `EmployeeProject`varios formada mediante la tabla de vínculos . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requiere que tal relación se modele utilizando tres clases: `Employee`, `Project` y `EmployeeProject`. En este caso, al cambiar la relación entre `Employee` y `Project` puede parecer necesario actualizar la clave principal de `EmployeeProject`. Sin embargo, esta situación se modela mejor eliminando un `EmployeeProject` existente y creando un nuevo `EmployeeProject`.  
  
    > [!NOTE]
    > Las relaciones en las bases de datos relacionales se modelan normalmente como valores de clave externa que hacen referencia a claves principales de otras tablas. Para navegar entre ellas, asocie explícitamente las dos tablas mediante una operación de *combinación* relacional.  
    >
    >  Los [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]objetos de , por otro lado, hacen referencia entre sí mediante referencias de propiedad o colecciones de referencias que se navegan mediante la notación de *puntos.*  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de relación uno a varios, la clase `Customer` tiene una propiedad que declara la relación entre los clientes y sus pedidos.  La propiedad `Orders` es de tipo <xref:System.Data.Linq.EntitySet%601>. Este tipo indica que esta relación es de uno a varios (entre un cliente y varios pedidos). La propiedad <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> se utiliza para describir cómo se logra esta asociación, a saber, especificando el nombre de la propiedad de la clase relacionada que se va a comparar con ésta. En este ejemplo, se compara la `CustomerID` propiedad, del igual que una *combinación* de base de datos compararía ese valor de columna.  
  
> [!NOTE]
> Si usa Visual Studio, puede usar el Diseñador relacional de objetos para crear una asociación entre clases.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 También puede invertir la situación. En lugar de utilizar la clase `Customer` para describir la asociación entre los clientes y los pedidos, puede utilizar la clase `Order`. La clase `Order` utiliza el tipo <xref:System.Data.Linq.EntityRef%601> para describir paso a paso la relación hasta el cliente, como se observa en el ejemplo de código siguiente.  
  
> [!NOTE]
> La <xref:System.Data.Linq.EntityRef%601> clase admite la *carga diferida.* Para obtener más información, *consulte* [Carga diferida frente a carga inmediata](deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Consulte también

- [Personalización de clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [El modelo de objetos LINQ to SQLLINQ to SQL](the-linq-to-sql-object-model.md)
