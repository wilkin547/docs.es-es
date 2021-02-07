---
description: 'Más información acerca de: Estados de objetos y Change-Tracking'
title: Estados de objetos y seguimiento de cambios
ms.date: 03/30/2017
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
ms.openlocfilehash: 5f3aa6197fa44d8b5ea9333c85255202cbfe519b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695507"
---
# <a name="object-states-and-change-tracking"></a>Estados de objetos y seguimiento de cambios

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] los objetos siempre participan en algún *Estado*. Por ejemplo, cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea un nuevo objeto, el objeto está en estado `Unchanged`. Un nuevo objeto que usted mismo crea es desconocido para <xref:System.Data.Linq.DataContext> y está en `Untracked` Estado. Después de la ejecución correcta de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, todos los objetos que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] reconoce están en estado `Unchanged`. (La única excepción son los objetos que se han eliminado correctamente de la base de datos, que están en estado `Deleted` y no se pueden utilizar en esa instancia de <xref:System.Data.Linq.DataContext>.)

## <a name="object-states"></a>Estados de objeto

La tabla siguiente enumera los posibles estados de los objetos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

|Estado|Descripción|
|-----------|-----------------|
|`Untracked`|Objeto del que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no realiza un seguimiento. Entre otros, se incluyen los siguientes ejemplos:<br /><br /> : Un objeto no consultado a través de la actual <xref:System.Data.Linq.DataContext> (por ejemplo, un objeto recién creado).<br />: Un objeto creado a través de la deserialización<br />: Un objeto consultado a través de un diferente <xref:System.Data.Linq.DataContext> .|
|`Unchanged`|Un objeto recuperado utilizando el <xref:System.Data.Linq.DataContext> actual y que se desconoce si se ha modificado desde que se creó.|
|`PossiblyModified`|Objeto que está *asociado* a <xref:System.Data.Linq.DataContext> . Para obtener más información, vea [operaciones de recuperación de datos y CUD en aplicaciones de N niveles (LINQ to SQL)](data-retrieval-and-cud-operations-in-n-tier-applications.md).|
|`ToBeInserted`|Objeto no recuperado utilizando el <xref:System.Data.Linq.DataContext> actual. Esto produce una operación `INSERT` en la base de datos durante la ejecución de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeUpdated`|Objeto que se sabe que se modificó desde que se recuperó. Esto produce una operación `UPDATE` en la base de datos durante la ejecución de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeDeleted`|Objeto marcado para la eliminación, que produce una operación `DELETE` en la base de datos durante la ejecución de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`Deleted`|Objeto eliminado de la base de datos. Este estado es definitivo y no permite transiciones adicionales.|

## <a name="inserting-objects"></a>Insertar objetos

Puede solicitar `Inserts` explícitamente mediante el método <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>. Como alternativa, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede deducir los `Inserts` objetos conectados a uno de los objetos conocidos que deben actualizarse. Por ejemplo, si agrega un `Untracked` objeto a una <xref:System.Data.Linq.EntitySet%601> o establece un <xref:System.Data.Linq.EntityRef%601> en un objeto, hace que `Untracked` el `Untracked` objeto sea accesible por medio de objetos de seguimiento en el gráfico. Durante <xref:System.Data.Linq.DataContext.SubmitChanges%2A> el procesamiento, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] recorre los objetos sometidos a seguimiento y detecta cualquier objeto persistente accesible del que no se realiza un seguimiento. Tales objetos son candidatos para la inserción en la base de datos.

En el caso de las clases de una jerarquía de herencia, <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> ( `o` ) también establece el valor del miembro designado como *discriminador* para que coincida con el tipo del objeto `o` . Si un tipo que coincide con el valor de discriminador predeterminado, esta acción hace que dicho valor se sobrescriba con el valor predeterminado. Para obtener más información, consulte [compatibilidad con la herencia](inheritance-support.md).

> [!IMPORTANT]
> Un objeto agregado a `Table` no se encuentra en la memoria caché de identidad. La memoria caché de identidad solo refleja lo que se recupera de la base de datos. Después de una llamada a <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, la entidad agregada no aparece en las consultas en la base de datos hasta que se complete <xref:System.Data.Linq.DataContext.SubmitChanges%2A> correctamente.

## <a name="deleting-objects"></a>Eliminar objetos

Un objeto `o` del que se realiza un seguimiento se marca para la eliminación mediante una llamada a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> en el objeto <xref:System.Data.Linq.Table%601> adecuado. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] considera la eliminación de un objeto de <xref:System.Data.Linq.EntitySet%601> como una operación de actualización y el valor de clave externa correspondiente se establece en NULL. El destino de la operación (`o`) no se elimina de su tabla. Por ejemplo, `cust.Orders.DeleteOnSubmit(ord)` indica una actualización donde la relación entre `cust` y `ord` se rompe estableciendo la clave externa `ord.CustomerID` en null. Esto no produce la eliminación de la fila que corresponde a `ord`.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] realiza el siguiente procesamiento cuando se elimina un objeto ( <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> ) de su tabla:

- Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, se realiza una operación `DELETE` para ese objeto.

- La eliminación no se propaga a los objetos relacionados, estén cargados o no. Concretamente, los objetos relacionados no se cargan para actualizar la propiedad de la relación.

- Después de la ejecución correcta de <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, los objetos se establecen en el estado `Deleted`. Como resultado, no se puede utilizar el objeto ni su `id` en <xref:System.Data.Linq.DataContext>. La memoria caché interna mantenida por una instancia de <xref:System.Data.Linq.DataContext> no elimina los objetos que se recuperan o que se agregan como nuevos, incluso una vez eliminados de la base de datos.

Solo se puede llamar a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> en un objeto del que <xref:System.Data.Linq.DataContext> realiza un seguimiento. Para un objeto `Untracked`, se debe llamar a <xref:System.Data.Linq.Table%601.Attach%2A> antes de llamar a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>. Si se llama a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> en un objeto `Untracked`, se inicia una excepción.

> [!NOTE]
> Al quitar un objeto de una tabla, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se indica a que genere un comando SQL correspondiente `DELETE` en el momento de <xref:System.Data.Linq.DataContext.SubmitChanges%2A> . Esta acción no quita el objeto de la memoria caché ni propaga la eliminación a los objetos relacionados.
>
> Para reclamar el `id` de un objeto eliminado, utilice una nueva instancia de <xref:System.Data.Linq.DataContext>. Para la limpieza de objetos relacionados, puede usar la característica de *eliminación en cascada* de la base de datos o, de lo contrario, eliminar manualmente los objetos relacionados.
>
> Los objetos relacionados no tienen que eliminarse en ningún orden especial (a diferencia de lo que sucede en la base de datos).

## <a name="updating-objects"></a>Actualizar objetos

Las `Updates` se detectan observando las notificaciones de cambios. Las notificaciones se proporcionan a través del evento <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging> en los establecedores de propiedades. Cuando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] recibe una notificación del primer cambio de un objeto, crea una copia del mismo y lo considera como candidato para generar una instrucción `Update`.

En el caso de los objetos que no implementan <xref:System.ComponentModel.INotifyPropertyChanging> , [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mantiene una copia de los valores que tenían los objetos cuando se materializaron por primera vez. Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> , [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] compara los valores originales y actuales para decidir si se ha cambiado el objeto.

Para las actualizaciones de relaciones, la autoridad es la referencia del elemento secundario al elemento primario (es decir, la referencia que corresponde a la clave externa). La referencia en dirección inversa (es decir, del elemento primario al elemento secundario) es opcional. Las clases de relaciones (<xref:System.Data.Linq.EntitySet%601> y <xref:System.Data.Linq.EntityRef%601>) garantizan que las referencias bidireccionales son coherentes para las relaciones uno a varios y uno a uno. Si el modelo de objetos no utiliza <xref:System.Data.Linq.EntitySet%601> o <xref:System.Data.Linq.EntityRef%601> y si la referencia inversa está presente, es su responsabilidad mantenerla coherente con la referencia adelantada cuando se actualice la relación.

Si actualiza la referencia requerida y la clave externa correspondiente, debe asegurarse de que coinciden. Se producirá una excepción <xref:System.InvalidOperationException> si ambas no están sincronizadas cuando se llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Aunque los cambios de los valores de clave externa son suficientes para que se actualice la fila subyacente, debería cambiar la referencia para mantener la conectividad del gráfico de objetos y la coherencia bidireccional de las relaciones.

## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
- [Operaciones de actualización, inserción y eliminación](insert-update-and-delete-operations.md)
