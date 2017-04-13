---
title: "Estados de objeto y seguimiento de cambios | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Estados de objeto y seguimiento de cambios
Los objetos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] siempre participan en algún *estado*.  Por ejemplo, cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea un nuevo objeto, el objeto está en estado `Unchanged`.  Un objeto nuevo que ha creado es desconocido para <xref:System.Data.Linq.DataContext> y su estado es `Untracked`.  Después de la ejecución correcta de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, todos los objetos que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] reconoce están en estado `Unchanged`.  \(La única excepción son los objetos que se han eliminado correctamente de la base de datos, que están en estado `Deleted` y no se pueden utilizar en esa instancia de <xref:System.Data.Linq.DataContext>.\)  
  
## Estados de objeto  
 La tabla siguiente enumera los posibles estados de los objetos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Estado|Descripción|  
|------------|-----------------|  
|`Untracked`|Objeto del que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no realiza un seguimiento.  Algunos ejemplos son:<br /><br /> -   Un objeto no consultado a través del <xref:System.Data.Linq.DataContext> actual \(como un objeto recientemente creado\).<br />-   Un objeto creado a través de la deserialización.<br />-   Un objeto consultado a través de un <xref:System.Data.Linq.DataContext> diferente.|  
|`Unchanged`|Un objeto recuperado utilizando el <xref:System.Data.Linq.DataContext> actual y que se desconoce si se ha modificado desde que se creó.|  
|`PossiblyModified`|Objeto *asociado* a un <xref:System.Data.Linq.DataContext>.  Para obtener más información, consulta [Recuperación de datos y operaciones CUD en aplicaciones de niveles N \(LINQ to SQL\)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).|  
|`ToBeInserted`|Objeto no recuperado utilizando el <xref:System.Data.Linq.DataContext> actual.  Esto produce una operación `INSERT` en la base de datos durante la ejecución de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeUpdated`|Objeto que se sabe que se modificó desde que se recuperó.  Esto produce una operación `UPDATE` en la base de datos durante la ejecución de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeDeleted`|Objeto marcado para la eliminación, que produce una operación `DELETE` en la base de datos durante la ejecución de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`Deleted`|Objeto eliminado de la base de datos.  Este estado es definitivo y no permite transiciones adicionales.|  
  
## Insertar objetos  
 Puede solicitar `Inserts` explícitamente mediante el método <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.  Como alternativa, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede deducir los elementos `Inserts` mediante la búsqueda de los objetos conectados a uno de los objetos conocidos que deben actualizarse.  Por ejemplo, si agrega un objeto `Untracked` a <xref:System.Data.Linq.EntitySet%601> o establece <xref:System.Data.Linq.EntityRef%601> en un objeto `Untracked`, hace que se pueda obtener acceso al objeto `Untracked` por medio de los objetos del gráfico de los que se realiza un seguimiento.  Durante el procesamiento de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] recorre los objetos de los que se realiza un seguimiento y detecta cualquier objeto persistente accesible del que no se realiza un seguimiento.  Tales objetos son candidatos para la inserción en la base de datos.  
  
 Para las clases de una jerarquía de herencia, <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>\(`o`\) establece también el valor del miembro designado como *discriminador* para que coincida con el tipo del objeto `o`.  Si un tipo que coincide con el valor de discriminador predeterminado, esta acción hace que dicho valor se sobrescriba con el valor predeterminado.  Para obtener más información, consulta [Compatibilidad de la herencia](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
> [!IMPORTANT]
>  Un objeto agregado a `Table` no se encuentra en la memoria caché de identidad.  La memoria caché de identidad solo refleja lo que se recupera de la base de datos.  Después de una llamada a <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, la entidad agregada no aparece en las consultas en la base de datos hasta que se complete <xref:System.Data.Linq.DataContext.SubmitChanges%2A> correctamente.  
  
## Eliminar objetos  
 Un objeto `o` del que se realiza un seguimiento se marca para la eliminación mediante una llamada a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> en el objeto <xref:System.Data.Linq.Table%601> adecuado.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] considera la eliminación de un objeto de <xref:System.Data.Linq.EntitySet%601> como una operación de actualización y el valor de clave externa correspondiente se establece en null.  El destino de la operación \(`o`\) no se elimina de su tabla.  Por ejemplo, `cust.Orders.DeleteOnSubmit(ord)` indica una actualización donde la relación entre `cust` y `ord` se rompe estableciendo la clave externa `ord.CustomerID` en null.  Esto no produce la eliminación de la fila que corresponde a `ord`.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] realiza el procesamiento siguiente cuando se elimina un objeto \(<xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>\) de su tabla:  
  
-   Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, se realiza una operación `DELETE` para ese objeto.  
  
-   La eliminación no se propaga a los objetos relacionados, estén cargados o no.  Concretamente, los objetos relacionados no se cargan para actualizar la propiedad de la relación.  
  
-   Después de la ejecución correcta de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, los objetos se establecen en el estado `Deleted`.  Como resultado, no se puede utilizar el objeto ni su `id` en <xref:System.Data.Linq.DataContext>.  La memoria caché interna mantenida por una instancia de <xref:System.Data.Linq.DataContext> no elimina los objetos que se recuperan o que se agregan como nuevos, incluso una vez eliminados de la base de datos.  
  
 Solo se puede llamar a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> en un objeto del que <xref:System.Data.Linq.DataContext> realiza un seguimiento.  Para un objeto `Untracked`, se debe llamar a <xref:System.Data.Linq.Table%601.Attach%2A> antes de llamar a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.  Si se llama a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> en un objeto `Untracked`, se inicia una excepción.  
  
> [!NOTE]
>  Al quitar un objeto de una tabla, se indica a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que genere un comando SQL `DELETE` correspondiente en el momento de ejecutar el método <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  Esta acción no quita el objeto de la memoria caché ni propaga la eliminación a los objetos relacionados.  
>   
>  Para reclamar el `id` de un objeto eliminado, utilice una nueva instancia de <xref:System.Data.Linq.DataContext>.  Para la limpieza de los objetos relacionados, puede utilizar la característica de *eliminación en cascada* de la base de datos, o eliminar los objetos relacionados manualmente.  
>   
>  Los objetos relacionados no tienen que eliminarse en ningún orden especial \(a diferencia de lo que sucede en la base de datos\).  
  
## Actualizar objetos  
 Las `Updates` se detectan observando las notificaciones de cambios.  Las notificaciones se proporcionan a través del evento <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging> en los establecedores de propiedades.  Cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] recibe una notificación del primer cambio de un objeto, crea una copia del mismo y lo considera como candidato para generar una instrucción `Update`.  
  
 Para los objetos que no implementan <xref:System.ComponentModel.INotifyPropertyChanging>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mantiene una copia de los valores que tenían los objetos la primera vez que se materializaron.  Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] compara los valores originales y actuales para decidir si se ha cambiado el objeto.  
  
 Para las actualizaciones de relaciones, la autoridad es la referencia del elemento secundario al elemento primario \(es decir, la referencia que corresponde a la clave externa\).  La referencia en dirección inversa \(es decir, del elemento primario al elemento secundario\) es opcional.  Las clases de relaciones \(<xref:System.Data.Linq.EntitySet%601> y <xref:System.Data.Linq.EntityRef%601>\) garantizan que las referencias bidireccionales son coherentes para las relaciones uno a varios y uno a uno.  Si el modelo de objetos no utiliza <xref:System.Data.Linq.EntitySet%601> o <xref:System.Data.Linq.EntityRef%601> y si la referencia inversa está presente, es su responsabilidad mantenerla coherente con la referencia adelantada cuando se actualice la relación.  
  
 Si actualiza la referencia requerida y la clave externa correspondiente, debe asegurarse de que coinciden.  Se producirá una excepción <xref:System.InvalidOperationException> si ambas no están sincronizadas cuando se llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  Aunque los cambios de los valores de clave externa son suficientes para que se actualice la fila subyacente, debería cambiar la referencia para mantener la conectividad del gráfico de objetos y la coherencia bidireccional de las relaciones.  
  
## Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)