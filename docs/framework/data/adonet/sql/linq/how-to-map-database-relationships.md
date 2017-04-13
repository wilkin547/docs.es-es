---
title: "C&#243;mo: Asignar relaciones de base de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo: Asignar relaciones de base de datos
Puede codificar como referencias de propiedad en la clase de entidad cualquier relación de datos que vaya a ser siempre la misma.  En la base de datos de ejemplo Northwind, por ejemplo, dado que los clientes normalmente realizan pedidos, hay siempre una relación en el modelo entre los clientes y sus pedidos.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] define un atributo <xref:System.Data.Linq.Mapping.AssociationAttribute> para ayudar a representar tales relaciones.  Este atributo se utiliza junto con los tipos <xref:System.Data.Linq.EntitySet%601> y <xref:System.Data.Linq.EntityRef%601> para representar lo que sería una relación de clave externa en una base de datos. Para obtener más información, consulte la sección relativa al atributo de asociación de [Asignación basada en atributos](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
>  Los valores de propiedad AssociationAttribute y ColumnAttribute Storage distinguen entre mayúsculas y minúsculas.  Por ejemplo, asegúrese de que los valores utilizados en el atributo de la propiedad AssociationAttribute.Storage coinciden con el uso de mayúsculas y minúsculas para los nombres de propiedad correspondientes del resto del código.  Esto se aplica a todos los lenguajes de programación de .NET, incluso a los que típicamente no distinguen entre mayúsculas y minúsculas, como [!INCLUDE[vb_current_short](../../../../../../includes/vb-current-short-md.md)].  Para obtener más información acerca de la propiedad Storage, vea <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=fullName>.  
  
 La mayoría de las relaciones son de uno a varios, como en el ejemplo que se incluye más adelante en este tema.  También puede representar relaciones uno a uno y varios a varios de la manera siguiente:  
  
-   Uno a uno: para representar este tipo de relación incluya <xref:System.Data.Linq.EntitySet%601> en ambos lados.  
  
     Por ejemplo, considere una relación `Customer`\-`SecurityCode`, creada de forma que el código de seguridad del cliente no se encuentre en la tabla `Customer` y solo esté accesible para las personas autorizadas.  
  
-   Varios a varios: en las relaciones varios a varios, la clave principal de la tabla de vínculos \(también conocida como tabla de *unión*\) suele estar formada por un conjunto de claves externas de las otras dos tablas.  
  
     Por ejemplo, considere una relación varios a varios `Employee`\-`Project` formada mediante la tabla de vínculos `EmployeeProject`.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requiere que tal relación se modele utilizando tres clases: `Employee`, `Project` y `EmployeeProject`.  En este caso, al cambiar la relación entre `Employee` y `Project` puede parecer necesario actualizar la clave principal de `EmployeeProject`.  Sin embargo, esta situación se modela mejor eliminando un `EmployeeProject` existente y creando un nuevo `EmployeeProject`.  
  
    > [!NOTE]
    >  Las relaciones en las bases de datos relacionales se modelan normalmente como valores de clave externa que hacen referencia a claves principales de otras tablas.  Para navegar entre ellas, las dos tablas se asocian explícitamente, utilizando una operación de *combinación* relacional.  
    >   
    >  Por otra parte, las referencias mutuas entre los objetos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se realizan mediante referencias de propiedad o colecciones de referencias por las que se navega mediante la notación de *punto*.  
  
## Ejemplo  
 En el siguiente ejemplo de relación uno a varios, la clase `Customer` tiene una propiedad que declara la relación entre los clientes y sus pedidos.  La propiedad `Orders` es de tipo <xref:System.Data.Linq.EntitySet%601>.  Este tipo indica que esta relación es de uno a varios \(entre un cliente y varios pedidos\).  La propiedad <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> se utiliza para describir cómo se logra esta asociación, a saber, especificando el nombre de la propiedad de la clase relacionada que se va a comparar con ésta.  En este ejemplo, se compara la propiedad `CustomerID`, de igual forma que una *combinación* de base de datos compararía ese valor de columna.  
  
> [!NOTE]
>  Si utiliza [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], puede utilizar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para crear una asociación entre clases.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## Ejemplo  
 También puede invertir la situación.  En lugar de utilizar la clase `Customer` para describir la asociación entre los clientes y los pedidos, puede utilizar la clase `Order`.  La clase `Order` utiliza el tipo <xref:System.Data.Linq.EntityRef%601> para describir paso a paso la relación hasta el cliente, como se observa en el ejemplo de código siguiente.  
  
> [!NOTE]
>  La clase <xref:System.Data.Linq.EntityRef%601> admite la *carga aplazada*.  Para obtener más información, *consulte* [Comparación entre carga aplazada y carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## Vea también  
 [Cómo: Personalizar clases de entidad mediante el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)   
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)