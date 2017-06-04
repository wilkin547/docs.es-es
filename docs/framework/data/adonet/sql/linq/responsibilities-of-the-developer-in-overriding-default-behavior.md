---
title: "Responsabilidades del desarrollador en la invalidaci&#243;n del comportamiento predeterminado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Responsabilidades del desarrollador en la invalidaci&#243;n del comportamiento predeterminado
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no exige que se cumplan los requisitos siguientes, pero, en caso de no cumplirse, el comportamiento no está definido.  
  
-   El método de invalidación no debe llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> o <xref:System.Data.Linq.Table%601.Attach%2A>.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una excepción si se llama a estos métodos en un método de invalidación.  
  
-   No se pueden utilizar métodos de invalidación para iniciar, confirmar o detener una transacción.  La operación <xref:System.Data.Linq.DataContext.SubmitChanges%2A> se realiza bajo una transacción.  Una transacción anidada interna puede interferir con la transacción externa.  Los métodos de invalidación de carga solo pueden iniciar una transacción después de determinar que la operación no se realiza en <xref:System.Transactions.Transaction>.  
  
-   Se espera que los métodos de invalidación sigan la asignación de simultaneidad optimista aplicable.  Se espera que el método de invalidación inicie <xref:System.Data.Linq.ChangeConflictException> cuando se produzca un conflicto de simultaneidad optimista.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] detecta esta excepción para que se pueda procesar correctamente la opción <xref:System.Data.Linq.DataContext.SubmitChanges%2A> proporcionada en <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
-   Se espera que los métodos de invalidación de creación \(`Insert`\) y de actualización \(`Update`\) devuelvan los valores de las columnas generadas por la base de datos a los miembros de objeto correspondientes cuando la operación se complete.  
  
     Por ejemplo, si `Order.OrderID` se asigna a una columna de identidad \(clave principal *autoincrement*\), el método de invalidación `InsertOrder()` debe recuperar el identificador generado por la base de datos y establecer el miembro `Order.OrderID` en ese identificador.  De igual forma, los miembros de marca de tiempo deben estar actualizados con los valores de marca de tiempo generados por la base de datos para garantizar que los objetos actualizados sean coherentes.  Si no se propagan los valores generados por la base de datos, puede haber incoherencias entre la base de datos y los objetos de los que <xref:System.Data.Linq.DataContext> realiza un seguimiento.  
  
-   Es el usuario quien debe invocar la API dinámica correcta.  Por ejemplo, en el método de invalidación de actualización, solo se puede llamar al método <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A>.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no detecta ni comprueba si el método dinámico invocado coincide con la operación aplicable.  Los resultados no están definidos si se llama a un método no aplicable \(por ejemplo, <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> para un objeto que se va a actualizar\).  
  
-   Finalmente, se espera que el método de invalidación realice la operación indicada.  La semántica de las operaciones de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], como la carga diligente, la carga aplazada y <xref:System.Data.Linq.DataContext.SubmitChanges%2A> necesita que los métodos de invalidación proporcionen el servicio indicado. Por ejemplo, una invalidación de carga que solo devuelva una colección vacía sin comprobar el contenido en la base de datos probablemente generará datos incoherentes.  
  
## Vea también  
 [Personalizar operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)