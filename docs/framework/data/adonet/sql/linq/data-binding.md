---
title: Enlace de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cbec8b02-a1e8-4ae8-a83b-bb5190413ac5
ms.openlocfilehash: c7048d292bdf5c1372d5f8f174f7f0e84efa7593
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634721"
---
# <a name="data-binding"></a>Enlace de datos

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite el enlace a controles comunes, como los controles de cuadrícula. En concreto, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] define los patrones básicos para enlazar a una cuadrícula de datos y controlar el enlace principal-detalle, ambos con respecto a la presentación y la actualización.

## <a name="underlying-principle"></a>Principio subyacente

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] traduce las consultas LINQ a SQL para su ejecución en una base de datos. Los resultados son `IEnumerable` fuertemente tipados. Dado que se trata de objetos CLR (Common Language Runtime) normales, se puede usar el enlace de datos de objeto normal para mostrar los resultados. Por otro lado, las operaciones de cambio (inserciones, actualizaciones y eliminaciones) requieren pasos adicionales.

## <a name="operation"></a>Operación

El enlace implícito a controles de Windows Forms se logra mediante la implementación de <xref:System.ComponentModel.IListSource>. Los orígenes de datos <xref:System.Data.Linq.Table%601> genéricos C# (`Table<T>` en o `Table(Of T)` en Visual Basic) y los `DataQuery` genéricos se han actualizado para implementar <xref:System.ComponentModel.IListSource>. Los motores de enlace de datos de la interfaz de usuario (Windows Forms y Windows Presentation Foundation) comprueban si su origen de datos implementa <xref:System.ComponentModel.IListSource>. Por consiguiente, si se escribe una redirección de una consulta en un origen de datos de un control, se llama implícitamente a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generación de colección, como en el ejemplo siguiente:

[!code-csharp[DLinqDataBinding#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#1)]
[!code-vb[DLinqDataBinding#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#1)]

Lo mismo sucede con Windows Presentation Foundation:

[!code-csharp[DLinqDataBinding#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#2)]
[!code-vb[DLinqDataBinding#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#2)]

Las generaciones de colecciones se implementan mediante <xref:System.Data.Linq.Table%601> genérico y `DataQuery` genérico en <xref:System.ComponentModel.IListSource.GetList%2A>.

## <a name="ilistsource-implementation"></a>Implementación de IListSource

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa <xref:System.ComponentModel.IListSource> en dos ubicaciones:

- El origen de datos es un <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examina la tabla para rellenar una colección de `DataBindingList` que mantiene una referencia en la tabla.

- El origen de datos es <xref:System.Linq.IQueryable%601>. Hay dos escenarios:

  - Si [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] encuentra el <xref:System.Data.Linq.Table%601> subyacente de la <xref:System.Linq.IQueryable%601>, el origen permite la edición y la situación es la misma que en el primer punto de la viñeta.

  - Si [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no encuentra el <xref:System.Data.Linq.Table%601>subyacente, el origen no permite la edición (por ejemplo, `groupby`). [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examina la consulta para rellenar un `SortableBindingList`genérico, que es un <xref:System.ComponentModel.BindingList%601> simple que implementa la característica de ordenación para entidades T para una propiedad determinada.

## <a name="specialized-collections"></a>Colecciones especializadas

Para muchas de las características antes descritas en este documento, <xref:System.ComponentModel.BindingList%601> se ha especializado en algunas clases diferentes. Estas clases son `SortableBindingList` genérica y `DataBindingList` genérica. Ambas se declaran como internas.

### <a name="generic-sortablebindinglist"></a>SortableBindingList genérica

Esta clase se hereda de <xref:System.ComponentModel.BindingList%601> y es una versión de <xref:System.ComponentModel.BindingList%601> que se puede ordenar. La ordenación es una solución en memoria y nunca entra en contacto con la propia base de datos. <xref:System.ComponentModel.BindingList%601> implementa <xref:System.ComponentModel.IBindingList>, pero no admite la ordenación de forma predeterminada. Sin embargo, <xref:System.ComponentModel.BindingList%601> implementa <xref:System.ComponentModel.IBindingList> con métodos de *núcleo* virtual. Puede invalidar estos métodos con facilidad. La clase `SortableBindingList` genérica invalida <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A> y <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>. `ApplySortCore` llama a <xref:System.ComponentModel.IBindingList.ApplySort%2A> y ordena la lista de elementos T de una propiedad dada.

Se producirá una excepción si la propiedad no pertenece a T.

Para lograr la ordenación, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea una clase de `SortableBindingList.PropertyComparer` genérica que hereda de <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> genérico e implementa un comparador predeterminado para un tipo T determinado, un `PropertyDescriptor`y una dirección. Esta clase crea dinámicamente un `Comparer` de T, donde T es `PropertyType` de `PropertyDescriptor`. Después, el comparador predeterminado se recupera del `Comparer` genérico estático. Se obtiene una instancia predeterminada mediante reflexión.

La clase `SortableBindingList` genérica es también la clase base para `DataBindingList`. La clase `SortableBindingList` genérica proporciona dos métodos virtuales para suspender o reanudar el seguimiento de las operaciones de agregar o quitar elementos. Esos dos métodos se pueden utilizar para características básicas, como la ordenación, pero realmente serán implementados por clases de nivel superior, como la clase `DataBindingList` genérica.

### <a name="generic-databindinglist"></a>Clase DataBindingList genérica

Esta clase se hereda de la clase `SortableBindingLIst` genérica. La clase `DataBindingList` genérica mantiene una referencia en el elemento `Table` genérico subyacente de la interfaz genérica `IQueryable` que se utilizó para el llenado inicial de la colección. La clase `DatabindingList` genérica agrega el seguimiento de las operaciones de agregar o quitar elementos a la colección mediante la invalidación de `InsertItem`() y `RemoveItem`(). También implementa la característica de seguimiento de suspensión/reanudación abstracta para que el seguimiento sea condicional. Esta característica permite que la clase `DataBindingList` genérica se pueda aprovechar del uso polimórfico completo de la característica de seguimiento de las clases primarias.

## <a name="binding-to-entitysets"></a>Enlace a EntitySets

El enlace a `EntitySet` es un caso especial, porque `EntitySet` ya es una colección que implementa <xref:System.ComponentModel.IBindingList>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] agrega compatibilidad con la ordenación y cancelación (<xref:System.ComponentModel.ICancelAddNew>). Una clase `EntitySet` utiliza una lista interna para almacenar las entidades. Esta lista es una colección de nivel inferior basada en una matriz genérica, la clase `ItemList` genérica.

### <a name="adding-a-sorting-feature"></a>Agregar una característica de ordenación

Las matrices proporcionan un método de ordenación (`Array.Sort()`) que se puede utilizar con un `Comparer` de T. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza la clase genérica `SortableBindingList.PropertyComparer` descrita anteriormente en este tema para obtener el `Comparer` de la propiedad y la dirección de ordenación. Para llamar a esta característica, se agrega un método `ApplySort` a la clase `ItemList` genérica.

En el lado `EntitySet`, ahora tiene que declarar la compatibilidad con la ordenación:

- <xref:System.ComponentModel.IBindingList.SupportsSorting%2A> devuelve `true`.

- <xref:System.ComponentModel.IBindingList.ApplySort%2A> llama a `entities.ApplySort()` y después a `OnListChanged()`.

- Las propiedades <xref:System.ComponentModel.IBindingList.SortDirection%2A> y <xref:System.ComponentModel.IBindingList.SortProperty%2A> exponen la definición de la ordenación actual, que se almacena en miembros locales.

Al usar System. Windows. Forms. BindingSource y enlazar un EntitySet\<> de la\<de la carpa a System. Windows. Forms. BindingSource. DataSource, debe llamar a EntitySet la >. Getnewbindinglist con fin actualizar BindingSource. List.

Si usa System. Windows. Forms. BindingSource y establece la propiedad BindingSource. DataMember y establece BindingSource. DataSource en una clase que tiene una propiedad denominada en BindingSource. DataMember que expone el EntitySet\<la > de la carpa, no tiene que llamar a EntitySet\<la > de la carpa. Getnewbindinglist con fin para actualizar BindingSource. List, pero se pierde la capacidad de ordenación.

## <a name="caching"></a>Almacenamiento en caché

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consultas implementan <xref:System.ComponentModel.IListSource.GetList%2A>. Cuando la clase BindingSource de Windows Forms se encuentra con esta interfaz, llama a GetList() tres veces para la misma conexión. Para evitar esta situación, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa una memoria caché por instancia para almacenar y devolver siempre la misma colección generada.

## <a name="cancellation"></a>Cancelación

<xref:System.ComponentModel.IBindingList> define un método <xref:System.ComponentModel.IBindingList.AddNew%2A> que los controles utilizan para crear un nuevo elemento a partir de una colección enlazada. El control `DataGridView` muestra esta característica perfectamente, incluyendo un asterisco en el encabezado de la última fila visible. El asterisco indica que se puede agregar un nuevo elemento.

Además de esta característica, una colección también puede implementar <xref:System.ComponentModel.ICancelAddNew>. Esta característica permite a los controles cancelar o verificar la validación o no validación del nuevo elemento editado.

<xref:System.ComponentModel.ICancelAddNew> se implementa en todas las colecciones de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] enlazadas a datos (`SortableBindingList` genérica y `EntitySet` genérica). En ambas implementaciones, el código actúa de la forma siguiente:

- Permite insertar y después quitar los elementos de la colección.

- No realiza un seguimiento de los cambios hasta que la interfaz de usuario confirma la edición.

- No realiza un seguimiento de los cambios hasta que la edición se cancela (<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>).

- Permite el seguimiento de los cambios cuando se confirma la edición (<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>).

- Permite que la colección se comporte con normalidad si el nuevo elemento no procede de <xref:System.ComponentModel.IBindingList.AddNew%2A>.

## <a name="troubleshooting"></a>Solucionar problemas

En esta sección se describen varios elementos que podrían ayudarle a solucionar los problemas de las aplicaciones de enlace de datos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

- Debe utilizar propiedades; utilizar solo campos no es suficiente. Los Windows Forms requieren que se utilicen.

- De forma predeterminada, los tipos de base de datos `image`, `varbinary`y `timestamp` se asignan a una matriz de bytes. Dado que `ToString()` no se admite en este escenario, estos objetos no se pueden mostrar.

- Un miembro de clase asignado a una clave principal tiene un establecedor, pero [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite el cambio de identidad de objeto. Por consiguiente, la clave principal/única que se usa en la asignación no se puede actualizar en la base de datos. Un cambio en la cuadrícula produce una excepción cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

- Si una entidad está enlazada en dos cuadrículas independientes (por ejemplo, una maestra y otra de detalle), `Delete` en la cuadrícula maestra no se propaga a la cuadrícula de detalle.

## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
