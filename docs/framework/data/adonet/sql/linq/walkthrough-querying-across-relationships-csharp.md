---
title: "Tutorial: Realizar consultas en varias relaciones (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Tutorial: Realizar consultas en varias relaciones (C#)
Este tutorial muestra el uso de *asociaciones* [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para representar relaciones de clave externa en la base de datos.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual C\#.  
  
## Requisitos previos  
 Debe de haber completado [Tutorial: Modelo de objetos simple y consultas \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md).  Este tutorial se basa en el tutorial mencionado, incluida la presencia del archivo northwnd.mdf en c:\\linqtest5.  
  
## Información general  
 Este tutorial conlleva tres tareas principales:  
  
-   Agregar una clase de entidad para representar la tabla Orders en la base de datos de ejemplo Northwind.  
  
-   Complementar las anotaciones de la clase `Customer` para mejorar la relación entre las clases `Customer` y `Order`.  
  
-   Crear y ejecutar una consulta para probar la obtención de información de `Order` mediante la clase `Customer`.  
  
## Asignar relaciones entre tablas  
 Después de la definición de la clase `Customer`, cree la definición de la clase de entidad `Order`, que incluye el código siguiente, que indica que `Order.Customer` se relaciona como clave externa con `Customer.CustomerID`.  
  
#### Para agregar la clase de entidad Order  
  
-   Escriba o pegue el código siguiente después de la clase `Customer`:  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## Anotar la clase Customer  
 En este paso, anotará la clase `Customer` para indicar su relación con la clase `Order`.  \(Esta adición no es estrictamente necesaria, porque para crear el vínculo basta con definir la relación en cualquier dirección.  Sin embargo, al agregar esta anotación, se puede navegar con facilidad por los objetos en cualquier dirección.\)  
  
#### Para anotar la clase Customer  
  
-   Escriba o pegue el código siguiente en la clase `Customer`:  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## Crear y ejecutar una consulta en la relación Customer\-Order  
 Ahora puede tener acceso a los objetos `Order` directamente desde los objetos `Customer`, o a la inversa.  No necesita una *combinación* explícita entre clientes y pedidos.  
  
#### Para tener acceso a los objetos Order a través de los objetos Customer  
  
1.  Modifique el método `Main`; para ello, escriba o pegue el código siguiente en el método:  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2.  Presione F5 para depurar la aplicación.  
  
    > [!NOTE]
    >  Puede eliminar el código de SQL en la ventana Consola marcando como comentario `db.Log = Console.Out;`.  
  
3.  Presione Entrar en la ventana Consola para detener la depuración.  
  
## Crear una vista de la base de datos fuertemente tipados  
 Es mucho más fácil empezar por una vista fuertemente tipada de la base de datos.  Si el objeto <xref:System.Data.Linq.DataContext> está fuertemente tipado, no es necesario realizar llamadas a <xref:System.Data.Linq.DataContext.GetTable%2A>.  Puede utilizar tablas fuertemente tipadas en todas sus consultas al utilizar el objeto <xref:System.Data.Linq.DataContext> fuertemente tipado.  
  
 En los pasos siguientes, creará `Customers` como una tabla fuertemente tipada que está asignada a la tabla Customers de la base de datos.  
  
#### Para que el objeto DataContext esté fuertemente tipado  
  
1.  Agregue el siguiente código encima de la declaración de la clase `Customer`.  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2.  Modifique el método `Main` para que utilice el objeto <xref:System.Data.Linq.DataContext> fuertemente tipado de la manera siguiente:  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3.  Presione F5 para depurar la aplicación.  
  
     El resultado en la ventana Consola es:  
  
     `ID=WHITC`  
  
4.  Presione Entrar en la ventana de la consola para detener la depuración.  
  
## Pasos siguientes  
 El tutorial siguiente \([Tutorial: Manipular datos \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)\) muestra cómo manipular los datos.  Este tutorial no requiere que guarde los dos tutoriales ya completados de esta serie.  
  
## Vea también  
 [Aprender mediante tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)