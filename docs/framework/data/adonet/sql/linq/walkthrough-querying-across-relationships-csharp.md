---
description: 'Más información sobre: Tutorial: realizar consultas en varias relaciones (C#)'
title: 'Tutorial: Realizar consultas en varias relaciones (C#)'
ms.date: 03/30/2017
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
ms.openlocfilehash: 35811043ddd7ecc9aca5e1bd87a370abebf90853
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729450"
---
# <a name="walkthrough-querying-across-relationships-c"></a>Tutorial: Realizar consultas en varias relaciones (C#)

En este tutorial se muestra el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *asociaciones* para representar relaciones de clave externa en la base de datos.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual C#.  
  
## <a name="prerequisites"></a>Requisitos previos  

 Debe haber completado el [Tutorial: modelo de objetos simple y consulta (C#)](walkthrough-simple-object-model-and-query-csharp.md). Este tutorial se basa en el tutorial mencionado, incluida la presencia del archivo northwnd.mdf en c:\linqtest5.  
  
## <a name="overview"></a>Información general  

 Este tutorial conlleva tres tareas principales:  
  
- Agregar una clase de entidad para representar la tabla Orders en la base de datos de ejemplo Northwind.  
  
- Complementar las anotaciones de la clase `Customer` para mejorar la relación entre las clases `Customer` y `Order`.  
  
- Crear y ejecutar una consulta para probar la obtención de información de `Order` mediante la clase `Customer`.  
  
## <a name="mapping-relationships-across-tables"></a>Asignar relaciones entre tablas  

 Después de la definición de la clase `Customer`, cree la definición de la clase de entidad `Order`, que incluye el código siguiente, que indica que `Order.Customer` se relaciona como clave externa con `Customer.CustomerID`.  
  
### <a name="to-add-the-order-entity-class"></a>Para agregar la clase de entidad Order  
  
- Escriba o pegue el código siguiente después de la clase `Customer`:  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a>Anotar la clase Customer  

 En este paso, anotará la clase `Customer` para indicar su relación con la clase `Order`. (Esta adición no es estrictamente necesaria, porque para crear el vínculo basta con definir la relación en cualquier dirección. Sin embargo, al agregar esta anotación, se puede navegar con facilidad por los objetos en cualquier dirección.)  
  
### <a name="to-annotate-the-customer-class"></a>Para anotar la clase Customer  
  
- Escriba o pegue el código siguiente en la clase `Customer`:  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a>Crear y ejecutar una consulta en la relación Customer-Order  

 Ahora puede tener acceso a los objetos `Order` directamente desde los objetos `Customer`, o a la inversa. No necesita una *combinación* explícita entre clientes y pedidos.  
  
### <a name="to-access-order-objects-by-using-customer-objects"></a>Para tener acceso a los objetos Order a través de los objetos Customer  
  
1. Modifique el método `Main`; para ello, escriba o pegue el código siguiente en el método:  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2. Presione F5 para depurar la aplicación.  
  
    > [!NOTE]
    > Puede eliminar el código de SQL en la ventana Consola marcando como comentario `db.Log = Console.Out;`.  
  
3. Presione Entrar en la ventana Consola para detener la depuración.  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a>Crear una vista de la base de datos fuertemente tipados  

 Es mucho más fácil empezar por una vista fuertemente tipada de la base de datos. Si el objeto <xref:System.Data.Linq.DataContext> está fuertemente tipado, no es necesario realizar llamadas a <xref:System.Data.Linq.DataContext.GetTable%2A>. Puede utilizar tablas fuertemente tipadas en todas sus consultas al utilizar el objeto <xref:System.Data.Linq.DataContext> fuertemente tipado.  
  
 En los pasos siguientes, creará `Customers` como una tabla fuertemente tipada que está asignada a la tabla Customers de la base de datos.  
  
### <a name="to-strongly-type-the-datacontext-object"></a>Para que el objeto DataContext esté fuertemente tipado  
  
1. Agregue el siguiente código encima de la declaración de la clase `Customer`.  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2. Modifique el método `Main` para que utilice el objeto <xref:System.Data.Linq.DataContext> fuertemente tipado de la manera siguiente:  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3. Presione F5 para depurar la aplicación.  
  
     El resultado en la ventana Consola es:  
  
     `ID=WHITC`  
  
4. Presione Entrar en la ventana de la consola para detener la depuración.  
  
## <a name="next-steps"></a>Pasos siguientes  

 En el siguiente tutorial ([Tutorial: manipular datos (C#)](walkthrough-manipulating-data-csharp.md)) se muestra cómo manipular los datos. Este tutorial no requiere que guarde los dos tutoriales ya completados de esta serie.  
  
## <a name="see-also"></a>Vea también

- [Aprender con tutoriales](learning-by-walkthroughs.md)
