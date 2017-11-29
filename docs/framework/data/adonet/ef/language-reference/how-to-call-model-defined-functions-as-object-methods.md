---
title: "Cómo: Llamar a funciones definidas por el modelo como métodos de objeto"
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
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a934cd8c122a1564c034f8578e8bad680ba919a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a>Cómo: Llamar a funciones definidas por el modelo como métodos de objeto
En este tema se describe cómo llamar a una función definida por el modelo como un método en un objeto <xref:System.Data.Objects.ObjectContext> o como un método estático en una clase personalizada. A *función definida por el modelo* es una función que se define en el modelo conceptual. Los procedimientos de este tema describen cómo llamar directamente a estas funciones en lugar de hacerlo desde consultas LINQ to Entities. Para obtener información sobre cómo llamar a funciones definidas por el modelo en LINQ a consultas de entidades, vea [Cómo: Call Model-Defined funciones en consultas](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md).  
  
 Tanto si se llama a una función definida por el modelo como un método <xref:System.Data.Objects.ObjectContext> o como un método estático en una clase personalizada, primero se deberá asignar el método a dicha función con un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Sin embargo, si se define un método en la clase <xref:System.Data.Objects.ObjectContext>, se debe usar la propiedad <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> para exponer el proveedor LINQ, mientras que si se define un método estático en una clase personalizada, se debe usar la propiedad <xref:System.Linq.IQueryable.Provider%2A> para exponer dicho proveedor. Para obtener más información, vea los ejemplos que aparecen a continuación de los procedimientos siguientes.  
  
 Los procedimientos siguientes proporcionan esquemas generales para llamar a una función definida por el modelo como un método en un objeto <xref:System.Data.Objects.ObjectContext> y como un método estático en una clase personalizada. Los ejemplos que los siguen proporcionan más detalles sobre los pasos de los procedimientos. Los procedimientos dan por hecho que se ha definido una función en el modelo conceptual. Para obtener más información, consulte [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a>Para llamar a una función definida por el modelo como un método en un objeto ObjectContext  
  
1.  Agregue un archivo de código fuente para extender la clase parcial derivada de la clase <xref:System.Data.Objects.ObjectContext>, generada automáticamente por las herramientas de Entity Framework. La definición del código auxiliar de CLR en un archivo de código fuente independiente evitará que se pierdan los cambios cuando se regenere el archivo.  
  
2.  Agregue un método de Common Language Runtime (CLR) a la clase <xref:System.Data.Objects.ObjectContext> que haga lo siguiente:  
  
    -   Se asigne a la función definida en el modelo conceptual. Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente. La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.  
  
    -   Devuelva los resultados del método <xref:System.Linq.IQueryProvider.Execute%2A> devuelto por la propiedad <xref:System.Data.Objects.ObjectContext.QueryProvider%2A>.  
  
3.  Llame al método como un miembro de una instancia de la clase <xref:System.Data.Objects.ObjectContext>.  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a>Para llamar a una función definida por el modelo como un método estático en una clase personalizada  
  
1.  Agregue una clase a la aplicación con un método estático que haga lo siguiente:  
  
    -   Se asigne a la función definida en el modelo conceptual. Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.  
  
    -   Acepte un argumento <xref:System.Linq.IQueryable>.  
  
    -   Devuelva los resultados del método <xref:System.Linq.IQueryProvider.Execute%2A> devuelto por la propiedad <xref:System.Linq.IQueryable.Provider%2A>.  
  
2.  Llame al método como un miembro de un método estático en la clase personalizada  
  
## <a name="example"></a>Ejemplo  
 **Llamar a una función definida por el modelo como un método en un objeto ObjectContext**  
  
 En el siguiente ejemplo se muestra cómo llamar a una función definida por el modelo como un método en un objeto <xref:System.Data.Objects.ObjectContext>. El ejemplo se utiliza la [modelo AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).  
  
 Observe la función de modelo conceptual siguiente que devuelve los ingresos obtenidos para un producto determinado. (Para obtener información acerca de cómo agregar la función en el modelo conceptual, consulte [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a>Ejemplo  
 El código siguiente agrega un método a la clase `AdventureWorksEntities` que se asigna a la función de modelo conceptual anterior.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente llama al método anterior para mostrar los ingresos obtenidos para un producto determinado:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar a una función definida por el modelo que devuelve una colección (como un objeto <xref:System.Linq.IQueryable%601>). Observe la función de modelo conceptual siguiente que devuelve todos los `SalesOrderDetails` para un identificador de producto determinado.  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente agrega un método a la clase `AdventureWorksEntities` que se asigna a la función de modelo conceptual anterior.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente llama al método. Observe que la consulta <xref:System.Linq.IQueryable%601> devuelta se redefine para devolver los totales de línea para cada `SalesOrderDetail`.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a>Ejemplo  
 **Llamar a una función definida por el modelo como un método estático en una clase personalizada**  
  
 En el ejemplo siguiente se muestra cómo llamar a una función definida por el modelo como un método estático en una clase personalizada. El ejemplo se utiliza la [modelo AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).  
  
> [!NOTE]
>  Cuando se llama a una función definida por el modelo como un método estático en una clase personalizada, la función debe aceptar una colección y devolver una agregación de valores de la colección.  
  
 Considere la función de modelo conceptual siguiente que devuelve los ingresos de los productos para una colección SalesOrderDetail. (Para obtener información acerca de cómo agregar la función en el modelo conceptual, consulte [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).).  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a>Ejemplo  
 El código siguiente agrega una clase a la aplicación que contiene un método estático que se asigna a la función de modelo conceptual anterior.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente llama al método anterior para mostrar los ingresos de los productos para una colección SalesOrderDetail:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a>Vea también  
 [información general de archivo .edmx](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Llamar a funciones en consultas LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
