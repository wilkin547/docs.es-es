---
title: Arquitectura del componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 81559444b6e3da2861e48bdc637ae01d246c0758
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165352"
---
# <a name="bindingsource-component-architecture"></a>Arquitectura del componente BindingSource
Con el <xref:System.Windows.Forms.BindingSource> , componente, puede enlazar universalmente todos los controles de Windows Forms a orígenes de datos.  
  
 El <xref:System.Windows.Forms.BindingSource> componente simplifica el proceso de enlazar controles a un origen de datos y proporciona las siguientes ventajas sobre el enlace de datos tradicional:  
  
-   Habilita el enlace de tiempo de diseño a objetos de negocios.  
  
-   Encapsula <xref:System.Windows.Forms.CurrencyManager> funcionalidad y expone <xref:System.Windows.Forms.CurrencyManager> eventos en tiempo de diseño.  
  
-   Simplifica la creación de una lista que admite el <xref:System.ComponentModel.IBindingList> interfaz proporcionando una notificación de cambio de la lista de notificación de cambio de orígenes de datos que no admiten de forma nativa la lista.  
  
-   Proporciona un punto de extensibilidad para el <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> método.  
  
-   Proporciona un nivel de direccionamiento indirecto entre el origen de datos y el control. Este direccionamiento indirecto es importante cuando el origen de datos puede cambiar en tiempo de ejecución.  
  
-   Interopera con otros controles de formularios de Windows relacionadas con los datos, específicamente el <xref:System.Windows.Forms.BindingNavigator> y <xref:System.Windows.Forms.DataGridView> controles.  
  
 Por estas razones, el <xref:System.Windows.Forms.BindingSource> componente es la mejor manera de enlazar los controles de Windows Forms a orígenes de datos.  
  
## <a name="bindingsource-features"></a>Características de BindingSource  
 El <xref:System.Windows.Forms.BindingSource> componente proporciona varias características para enlazar controles a datos. Con estas características, puede implementar la mayoría de escenarios de enlace de datos con casi ninguna codificación por su parte.  
  
 El <xref:System.Windows.Forms.BindingSource> componente realiza esto proporcionando una interfaz coherente para tener acceso a muchos tipos diferentes de orígenes de datos. Esto significa que use el mismo procedimiento para enlazar a cualquier tipo. Por ejemplo, puede adjuntar el <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad a un <xref:System.Data.DataSet> o a un objeto de negocios y en ambos casos use el mismo conjunto de propiedades, métodos y eventos para manipular el origen de datos.  
  
 La coherente interfaz proporcionada por el <xref:System.Windows.Forms.BindingSource> componente simplifica enormemente el proceso de enlazar datos a controles. Para los tipos de origen de datos que proporcionan notificación de cambios, el <xref:System.Windows.Forms.BindingSource> componente comunica automáticamente los cambios entre el control y el origen de datos. Para los tipos de origen de datos que no proporcionan notificación de cambio, los eventos son siempre que le permiten generar notificaciones de cambios. La siguiente lista muestra las características admitidas por el <xref:System.Windows.Forms.BindingSource> componente:  
  
-   Direccionamiento indirecto.  
  
-   Administración de moneda.  
  
-   Origen de datos como una lista.  
  
-   <xref:System.Windows.Forms.BindingSource> como un <xref:System.ComponentModel.IBindingList>.  
  
-   Creación de elementos personalizada.  
  
-   Creación de un artículo transaccional.  
  
-   <xref:System.Collections.IEnumerable> soporte técnico.  
  
-   Compatibilidad en tiempo de diseño.  
  
-   Estática <xref:System.Windows.Forms.ListBindingHelper> métodos.  
  
-   Ordenar y filtrar con el <xref:System.ComponentModel.IBindingListView> interfaz.  
  
-   Integración con <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Direccionamiento indirecto  
 El <xref:System.Windows.Forms.BindingSource> componente proporciona un nivel de direccionamiento indirecto entre un control y un origen de datos. En lugar de enlazar un control directamente a un origen de datos, enlaza el control a un <xref:System.Windows.Forms.BindingSource>, y adjuntar el origen de datos a la <xref:System.Windows.Forms.BindingSource> del componente <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad.  
  
 Con este nivel de direccionamiento indirecto, puede cambiar el origen de datos sin restablecer el enlace del control. Esto le ofrece las siguientes funcionalidades:  
  
-   Puede adjuntar el <xref:System.Windows.Forms.BindingSource> a diferentes orígenes de datos conservando los enlaces del control actual.  
  
-   Puede cambiar los elementos del origen de datos y notificar a los controles enlazados. Para obtener más información, vea [Cómo: Reflejar las actualizaciones del origen de datos en un Control de Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   Puede enlazar a un <xref:System.Type> en lugar de un objeto en memoria. Para obtener más información, vea [Cómo: Enlazar un Control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md). A continuación, puede enlazar a un objeto en tiempo de ejecución.  
  
### <a name="currency-management"></a>Administración de moneda  
 El <xref:System.Windows.Forms.BindingSource> componente implementa el <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaz para administrar la moneda para usted. Con el <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaz, también puede acceder al administrador de moneda para un <xref:System.Windows.Forms.BindingSource>, así como al administrador de moneda para otro <xref:System.Windows.Forms.BindingSource> enlazados al mismo <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 El <xref:System.Windows.Forms.BindingSource> componente encapsula <xref:System.Windows.Forms.CurrencyManager> funcionalidad y expone los más comunes <xref:System.Windows.Forms.CurrencyManager> propiedades y eventos. En la tabla siguiente se describe algunos de los miembros relacionados con la administración de moneda.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> propiedad  
 Obtiene el Administrador de moneda asociado con el <xref:System.Windows.Forms.BindingSource>.  
  
 <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A> método  
 Si hay otro <xref:System.Windows.Forms.BindingSource> enlazados al miembro de datos especificado, obtiene su administrador de moneda.  
  
 <xref:System.Windows.Forms.BindingSource.Current%2A> propiedad  
 Obtiene el elemento actual del origen de datos.  
  
 <xref:System.Windows.Forms.BindingSource.Position%2A> propiedad  
 Obtiene o establece la posición actual en la lista subyacente.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> método  
 Aplica los cambios pendientes al origen de datos subyacente.  
  
 <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> método  
 Cancela la operación de edición actual.  
  
### <a name="data-source-as-a-list"></a>Origen de datos como una lista  
 El <xref:System.Windows.Forms.BindingSource> componente implementa el <xref:System.ComponentModel.IBindingListView> y <xref:System.ComponentModel.ITypedList> interfaces. Con esta implementación, puede usar el <xref:System.Windows.Forms.BindingSource> componente como un origen de datos, sin ningún almacenamiento externo.  
  
 Cuando el <xref:System.Windows.Forms.BindingSource> componente se adjunta a un origen de datos, que expone el origen de datos como una lista.  
  
 El <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad puede establecerse en varios orígenes de datos. Éstos incluyen tipos, objetos y listas de tipos. El origen de datos resultante se expondrá como una lista. La siguiente tabla muestra algunos de los orígenes de datos comunes y la evaluación de la lista resultante.  
  
|Propiedad de origen de datos|Resultados de la lista|  
|-------------------------|------------------|  
|Una referencia nula (`Nothing` en Visual Basic)|Un valor vacío <xref:System.ComponentModel.IBindingList> de objetos. Agregar un elemento, Establece la lista para el tipo del elemento agregado.|  
|Una referencia nula (`Nothing` en Visual Basic) con <xref:System.Windows.Forms.BindingSource.DataMember%2A> establecido|No se admite; genera <xref:System.ArgumentException>.|  
|Tipo no de lista o un objeto de tipo "T"|Un valor vacío <xref:System.ComponentModel.IBindingList> de tipo "T".|  
|Instancia de matriz|Un <xref:System.ComponentModel.IBindingList> que contiene los elementos de matriz.|  
|<xref:System.Collections.IEnumerable> instancia|Un <xref:System.ComponentModel.IBindingList> que contiene el <xref:System.Collections.IEnumerable> elementos|  
|"T" de la instancia que contiene el tipo de lista|Un <xref:System.ComponentModel.IBindingList> instancia que contiene el tipo "T".|  
  
 Además, <xref:System.Windows.Forms.BindingSource.DataSource%2A> se puede establecer en otros tipos de lista, como <xref:System.ComponentModel.IListSource> y <xref:System.ComponentModel.ITypedList>y el <xref:System.Windows.Forms.BindingSource> controlará adecuadamente. En este caso, el tipo que se encuentra en la lista debe tener un constructor predeterminado.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource como IBindingList  
 El <xref:System.Windows.Forms.BindingSource> componente proporciona miembros para obtener acceso y manipular los datos subyacentes como un <xref:System.ComponentModel.IBindingList>. En la tabla siguiente se describe algunos de estos miembros.  
  
|Miembro|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.List%2A> propiedad|Obtiene la lista que es el resultado de la evaluación de la <xref:System.Windows.Forms.BindingSource.DataSource%2A> o <xref:System.Windows.Forms.BindingSource.DataMember%2A> propiedades.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> método|Agrega un nuevo elemento a la lista subyacente. Se aplica a los orígenes de datos que implementan la <xref:System.ComponentModel.IBindingList> interfaz y permiten agregar elementos (es decir, el <xref:System.Windows.Forms.BindingSource.AllowNew%2A> propiedad está establecida en `true`).|  
  
### <a name="custom-item-creation"></a>Creación de elementos personalizada  
 Puede controlar la <xref:System.Windows.Forms.BindingSource.AddingNew> eventos para proporcionar su propia lógica de creación de elementos. El <xref:System.Windows.Forms.BindingSource.AddingNew> evento se produce antes de que se agrega un nuevo objeto a la <xref:System.Windows.Forms.BindingSource>. Este evento se desencadena después de la <xref:System.Windows.Forms.BindingSource.AddNew%2A> método se llama, pero antes de que el nuevo elemento se agrega a la lista subyacente. Al controlar este evento, puede proporcionar el comportamiento de creación de elemento personalizado sin que derivar de la <xref:System.Windows.Forms.BindingSource> clase. Para obtener más información, vea [Cómo: Personalizar elemento con el componente BindingSource de Windows Forms](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### <a name="transactional-item-creation"></a>Creación de elemento transaccional  
 El <xref:System.Windows.Forms.BindingSource> componente implementa el <xref:System.ComponentModel.ICancelAddNew> interfaz, que permite la creación de un artículo transaccional. Después de un nuevo elemento provisionalmente se crea mediante una llamada a <xref:System.Windows.Forms.BindingSource.AddNew%2A>, la adición es posible que se confirma o revierte en las siguientes maneras:  
  
-   El <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> método confirmará explícitamente la adición pendiente.  
  
-   Realizar otra operación de colección, como una inserción, eliminación o movimiento, se confirmará implícitamente la adición pendiente.  
  
-   El <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> método revertirá la adición pendiente si el método no ya se ha confirmado.  
  
### <a name="ienumerable-support"></a>Compatibilidad con IEnumerable  
 El <xref:System.Windows.Forms.BindingSource> componente permite enlazar controles a <xref:System.Collections.IEnumerable> orígenes de datos. Con este componente, puede enlazar a un origen de datos, como un <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>.  
  
 Cuando un <xref:System.Collections.IEnumerable> origen de datos se asigna a la <xref:System.Windows.Forms.BindingSource> componente, el <xref:System.Windows.Forms.BindingSource> crea un <xref:System.ComponentModel.IBindingList> y agrega el contenido de la <xref:System.Collections.IEnumerable> origen de datos a la lista.  
  
### <a name="design-time-support"></a>Compatibilidad en tiempo de diseño  
 No se puede crear algunos tipos de objetos en tiempo de diseño, como objetos creados a partir de una clase de generador, los objetos devueltos por un servicio Web. A veces puede tener que enlazar los controles a estos tipos en tiempo de diseño, aunque no hay ningún objeto en la memoria a la que se pueden enlazar los controles. Es posible que, por ejemplo, deberá etiquetar los encabezados de columna de un <xref:System.Windows.Forms.DataGridView> control con los nombres de las propiedades públicas de su tipo personalizado.  
  
 Para admitir este escenario, el <xref:System.Windows.Forms.BindingSource> componente admite el enlace a un <xref:System.Type>. Al asignar un <xref:System.Type> a la <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad, el <xref:System.Windows.Forms.BindingSource> crea un componente <xref:System.ComponentModel.BindingList%601> de <xref:System.Type> elementos. Todos los controles que enlaza posteriormente a la <xref:System.Windows.Forms.BindingSource> componente notificará a la presencia de las propiedades o el esquema de su tipo en tiempo de diseño o en tiempo de ejecución. Para obtener más información, vea [Cómo: Enlazar un Control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>Métodos ListBindingHelper estáticos  
 El <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, y <xref:System.Windows.Forms.BindingSource> lógica común de todos los recursos compartidos para generar una lista de los tipos de un `DataSource` / `DataMember` par. Además, esta lógica común se expone de públicamente para su uso por los autores de controles y otras terceras partes en la siguiente `static` métodos:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Ordenar y filtrar con IBindingListView (interfaz)  
 El <xref:System.Windows.Forms.BindingSource> componente implementa el <xref:System.ComponentModel.IBindingListView> interfaz, que amplía el <xref:System.ComponentModel.IBindingList> interfaz. El <xref:System.ComponentModel.IBindingList> ofrece la ordenación de columna única y la <xref:System.ComponentModel.IBindingListView> ofrece avanzadas de ordenación y filtrado. Con <xref:System.ComponentModel.IBindingListView>, puede ordenar y filtrar los elementos del origen de datos, si el origen de datos también implementa una de estas interfaces. El <xref:System.Windows.Forms.BindingSource> componente no proporciona una implementación de referencia de estos miembros. En su lugar, las llamadas se reenvían a la lista subyacente.  
  
 En la tabla siguiente se describe las propiedades que se usa para ordenar y filtrar.  
  
|Miembro|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> propiedad|Si el origen de datos es una <xref:System.ComponentModel.IBindingListView>, obtiene o establece la expresión usada para filtrar qué filas se ven.|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> propiedad|Si el origen de datos es una <xref:System.ComponentModel.IBindingList>, obtiene o establece el nombre de columna usado para ordenar y el criterio de ordenación.<br /><br /> -o bien-<br /><br /> Si el origen de datos es un <xref:System.ComponentModel.IBindingListView> y admite la ordenación avanzada, obtiene varios nombres de columna usados para ordenar y el criterio de ordenación|  
  
### <a name="integration-with-bindingnavigator"></a>Integración con BindingNavigator  
 Puede usar el <xref:System.Windows.Forms.BindingSource> componente para enlazar cualquier control de Windows Forms a un origen de datos, pero la <xref:System.Windows.Forms.BindingNavigator> control está diseñado específicamente para trabajar con el <xref:System.Windows.Forms.BindingSource> componente. El <xref:System.Windows.Forms.BindingNavigator> control proporciona una interfaz de usuario para controlar la <xref:System.Windows.Forms.BindingSource> elemento actual del componente. De forma predeterminada, el <xref:System.Windows.Forms.BindingNavigator> control proporciona botones que corresponden a los métodos de navegación en el <xref:System.Windows.Forms.BindingSource> componente. Para obtener más información, vea [Cómo: Explorar datos con el Control BindingNavigator de Windows Forms](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Información general sobre el componente BindingSource](bindingsource-component-overview.md)
- [Control BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Filtrar para enlazar un control de formularios Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Filtrar para reflejar las actualizaciones de los orígenes de datos en un control de formularios Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
