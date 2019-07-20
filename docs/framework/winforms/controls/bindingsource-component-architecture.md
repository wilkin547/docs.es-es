---
title: Arquitectura del componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 54a23ba899ceb05701fe3580aefbb723c6b3f0fd
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364408"
---
# <a name="bindingsource-component-architecture"></a>Arquitectura del componente BindingSource
Con el <xref:System.Windows.Forms.BindingSource> componente, puede enlazar universalmente todos los controles Windows Forms a los orígenes de datos.  
  
 El <xref:System.Windows.Forms.BindingSource> componente simplifica el proceso de enlazar controles a un origen de datos y proporciona las siguientes ventajas con respecto al enlace de datos tradicional:  
  
- Habilita el enlace en tiempo de diseño a objetos comerciales.  
  
- Encapsula la <xref:System.Windows.Forms.CurrencyManager> funcionalidad y expone eventos en tiempo de diseño. <xref:System.Windows.Forms.CurrencyManager>  
  
- Simplifica la creación de una lista que admita <xref:System.ComponentModel.IBindingList> la interfaz proporcionando una notificación de cambio de lista para los orígenes de datos que no admiten de forma nativa la notificación de cambios de lista.  
  
- Proporciona un punto de extensibilidad para <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> el método.  
  
- Proporciona un nivel de direccionamiento indirecto entre el origen de datos y el control. Este direccionamiento indirecto es importante cuando el origen de datos puede cambiar en tiempo de ejecución.  
  
- Interopera con otros controles de Windows Forms relacionados con datos, específicamente los <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.DataGridView> controles y.  
  
 Por estos motivos, el <xref:System.Windows.Forms.BindingSource> componente es la manera preferida de enlazar los controles de Windows Forms a los orígenes de datos.  
  
## <a name="bindingsource-features"></a>Características de BindingSource  
 El <xref:System.Windows.Forms.BindingSource> componente proporciona varias características para enlazar controles a los datos. Con estas características, puede implementar la mayoría de los escenarios de enlace de datos con casi ninguna codificación por su parte.  
  
 El <xref:System.Windows.Forms.BindingSource> componente logra esto proporcionando una interfaz coherente para tener acceso a muchos tipos diferentes de orígenes de datos. Esto significa que se usa el mismo procedimiento para enlazar a cualquier tipo. Por ejemplo, puede adjuntar <xref:System.Windows.Forms.BindingSource.DataSource%2A> la propiedad a <xref:System.Data.DataSet> un objeto o a un objeto comercial y, en ambos casos, utilizar el mismo conjunto de propiedades, métodos y eventos para manipular el origen de datos.  
  
 La interfaz coherente proporcionada por el <xref:System.Windows.Forms.BindingSource> componente simplifica considerablemente el proceso de enlazar datos a los controles. En el caso de los tipos de origen de datos que <xref:System.Windows.Forms.BindingSource> proporcionan la notificación de cambios, el componente comunica automáticamente los cambios entre el control y el origen de datos. En el caso de los tipos de origen de datos que no proporcionan la notificación de cambios, se proporcionan eventos que permiten generar notificaciones de cambios. En la siguiente lista se muestran las características admitidas por el <xref:System.Windows.Forms.BindingSource> componente:  
  
- Direccionamiento indirecto.  
  
- Administración de moneda.  
  
- Origen de datos como una lista.  
  
- <xref:System.Windows.Forms.BindingSource><xref:System.ComponentModel.IBindingList>como.  
  
- Creación de elementos personalizados.  
  
- Creación de elementos transaccionales.  
  
- <xref:System.Collections.IEnumerable>ser.  
  
- Compatibilidad en tiempo de diseño.  
  
- Métodos <xref:System.Windows.Forms.ListBindingHelper> estáticos.  
  
- Ordenación y filtrado con la <xref:System.ComponentModel.IBindingListView> interfaz.  
  
- Integración con <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Direccionamiento indirecto  
 El <xref:System.Windows.Forms.BindingSource> componente proporciona un nivel de direccionamiento indirecto entre un control y un origen de datos. En lugar de enlazar un control directamente a un origen de datos, debe enlazar el <xref:System.Windows.Forms.BindingSource>control a un y asociar el origen de <xref:System.Windows.Forms.BindingSource> datos a <xref:System.Windows.Forms.BindingSource.DataSource%2A> la propiedad del componente.  
  
 Con este nivel de direccionamiento indirecto, puede cambiar el origen de datos sin restablecer el enlace de control. Esto le ofrece las siguientes capacidades:  
  
- Puede adjuntar <xref:System.Windows.Forms.BindingSource> a distintos orígenes de datos conservando los enlaces de control actuales.  
  
- Puede cambiar los elementos del origen de datos y notificar los controles enlazados. Para obtener más información, consulte [Cómo Reflejar las actualizaciones del origen de datos en un control de](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)Windows Forms con BindingSource.  
  
- Puede enlazar a en <xref:System.Type> lugar de a un objeto en la memoria. Para obtener más información, consulte [Cómo Enlazar un control de Windows Forms a](how-to-bind-a-windows-forms-control-to-a-type.md)un tipo. Después, puede enlazar a un objeto en tiempo de ejecución.  
  
### <a name="currency-management"></a>Administración de moneda  
 El <xref:System.Windows.Forms.BindingSource> componente implementa la interfaz <xref:System.Windows.Forms.ICurrencyManagerProvider> para controlar la administración de moneda. Con la <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaz, también puede tener acceso al administrador de moneda de un <xref:System.Windows.Forms.BindingSource>, además del administrador de moneda para otro <xref:System.Windows.Forms.BindingSource> enlazado al mismo <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 El <xref:System.Windows.Forms.BindingSource> componente <xref:System.Windows.Forms.CurrencyManager> encapsula la funcionalidad y expone las propiedades y eventos más comunes. <xref:System.Windows.Forms.CurrencyManager> En la tabla siguiente se describen algunos de los miembros relacionados con la administración de moneda.  
  
 Propiedad<xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Obtiene el administrador de moneda asociado <xref:System.Windows.Forms.BindingSource>a.  
  
 Método <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Si hay otro <xref:System.Windows.Forms.BindingSource> enlazado al miembro de datos especificado, obtiene su administrador de moneda.  
  
 Propiedad<xref:System.Windows.Forms.BindingSource.Current%2A>  
 Obtiene el elemento actual del origen de datos.  
  
 Propiedad<xref:System.Windows.Forms.BindingSource.Position%2A>  
 Obtiene o establece la posición actual en la lista subyacente.  
  
 Método <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Aplica los cambios pendientes al origen de datos subyacente.  
  
 Método <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Cancela la operación de edición actual.  
  
### <a name="data-source-as-a-list"></a>Origen de datos como una lista  
 El <xref:System.Windows.Forms.BindingSource> componente implementa las <xref:System.ComponentModel.IBindingListView> interfaces y <xref:System.ComponentModel.ITypedList> . Con esta implementación, puede usar el <xref:System.Windows.Forms.BindingSource> propio componente como un origen de datos, sin almacenamiento externo.  
  
 Cuando el <xref:System.Windows.Forms.BindingSource> componente se adjunta a un origen de datos, expone el origen de datos como una lista.  
  
 La <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad se puede establecer en varios orígenes de datos. Estos incluyen tipos, objetos y listas de tipos. El origen de datos resultante se expondrá como una lista. En la tabla siguiente se muestran algunos de los orígenes de datos comunes y la evaluación de la lista resultante.  
  
|Propiedad DataSource|Resultados de la lista|  
|-------------------------|------------------|  
|Una referencia nula (`Nothing` en Visual Basic)|Un objeto <xref:System.ComponentModel.IBindingList> vacío de objetos. Al agregar un elemento, se establece la lista en el tipo del elemento agregado.|  
|Referencia nula (`Nothing` en Visual Basic) con <xref:System.Windows.Forms.BindingSource.DataMember%2A> set|No se admiten; genera <xref:System.ArgumentException>.|  
|Tipo no de lista u objeto de tipo "T"|Una matriz <xref:System.ComponentModel.IBindingList> vacía de tipo "T".|  
|Instancia de matriz|<xref:System.ComponentModel.IBindingList> Que contiene los elementos de la matriz.|  
|<xref:System.Collections.IEnumerable>repetición|Que contiene los <xref:System.Collections.IEnumerable>elementos. <xref:System.ComponentModel.IBindingList>|  
|Instancia de lista que contiene el tipo "T"|<xref:System.ComponentModel.IBindingList> Instancia de que contiene el tipo "T".|  
  
 Además, <xref:System.Windows.Forms.BindingSource.DataSource%2A> se puede establecer en otros tipos de lista, <xref:System.ComponentModel.IListSource> como y <xref:System.ComponentModel.ITypedList>, y el <xref:System.Windows.Forms.BindingSource> controlará adecuadamente. En este caso, el tipo contenido en la lista debe tener un constructor sin parámetros.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource como IBindingList  
 El <xref:System.Windows.Forms.BindingSource> componente proporciona miembros para obtener acceso y manipular los datos subyacentes <xref:System.ComponentModel.IBindingList>como. En la tabla siguiente se describen algunos de estos miembros.  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|Propiedad<xref:System.Windows.Forms.BindingSource.List%2A>|Obtiene la lista resultante de la evaluación de las <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedades o. <xref:System.Windows.Forms.BindingSource.DataMember%2A>|  
|Método <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Agrega un nuevo elemento a la lista subyacente. Se aplica a los orígenes de datos <xref:System.ComponentModel.IBindingList> que implementan la interfaz y permiten agregar elementos ( <xref:System.Windows.Forms.BindingSource.AllowNew%2A> es decir, la `true`propiedad está establecida en).|  
  
### <a name="custom-item-creation"></a>Creación de elementos personalizados  
 Puede controlar el <xref:System.Windows.Forms.BindingSource.AddingNew> evento para proporcionar su propia lógica de creación de elementos. El <xref:System.Windows.Forms.BindingSource.AddingNew> evento tiene lugar antes de <xref:System.Windows.Forms.BindingSource>que se agregue un nuevo objeto a. Este evento se desencadena después de <xref:System.Windows.Forms.BindingSource.AddNew%2A> que se llame al método, pero antes de que el nuevo elemento se agregue a la lista subyacente. Controlando este evento, puede proporcionar el comportamiento de creación de elementos personalizados sin derivar <xref:System.Windows.Forms.BindingSource> de la clase. Para obtener más información, consulte [Cómo Personalizar la adición de elementos con el](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)Windows Forms BindingSource.  
  
### <a name="transactional-item-creation"></a>Creación de elementos transaccionales  
 El <xref:System.Windows.Forms.BindingSource> componente implementa la interfaz <xref:System.ComponentModel.ICancelAddNew> , que permite la creación de elementos transaccionales. Después de que un nuevo elemento se cree de forma aprovisionada mediante una <xref:System.Windows.Forms.BindingSource.AddNew%2A>llamada a, la adición se puede confirmar o revertir de las siguientes maneras:  
  
- El <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> método confirma explícitamente la adición pendiente.  
  
- Al realizar otra operación de recopilación, como una inserción, eliminación o movimiento, se confirma implícitamente la adición pendiente.  
  
- El <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> método revertirá la adición pendiente si aún no se ha confirmado el método.  
  
### <a name="ienumerable-support"></a>Compatibilidad con IEnumerable  
 El <xref:System.Windows.Forms.BindingSource> componente permite enlazar controles <xref:System.Collections.IEnumerable> a orígenes de datos. Con este componente, puede enlazar a un origen de datos como <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>.  
  
 Cuando un <xref:System.Collections.IEnumerable> origen de datos se asigna <xref:System.Windows.Forms.BindingSource> al <xref:System.ComponentModel.IBindingList> componente, <xref:System.Windows.Forms.BindingSource> <xref:System.Collections.IEnumerable> crea y agrega el contenido del origen de datos a la lista.  
  
### <a name="design-time-support"></a>Compatibilidad en tiempo de diseño  
 Algunos tipos de objetos no se pueden crear en tiempo de diseño, como los objetos creados a partir de una clase de generador, o los objetos devueltos por un servicio Web. En ocasiones, es posible que tenga que enlazar los controles a estos tipos en tiempo de diseño, aunque no haya ningún objeto en la memoria al que puedan enlazarse los controles. Por ejemplo, puede que necesite etiquetar los encabezados de columna de un <xref:System.Windows.Forms.DataGridView> control con los nombres de las propiedades públicas del tipo personalizado.  
  
 Para admitir este escenario, el <xref:System.Windows.Forms.BindingSource> componente admite el enlace a <xref:System.Type>un. Cuando se asigna un <xref:System.Type> a la <xref:System.Windows.Forms.BindingSource.DataSource%2A> propiedad, el <xref:System.Windows.Forms.BindingSource> componente crea un vacío <xref:System.ComponentModel.BindingList%601> de <xref:System.Type> elementos. Cualquier control que enlace posteriormente al <xref:System.Windows.Forms.BindingSource> componente recibirá una alerta sobre la presencia de las propiedades o el esquema del tipo en tiempo de diseño o en tiempo de ejecución. Para obtener más información, consulte [Cómo Enlazar un control de Windows Forms a](how-to-bind-a-windows-forms-control-to-a-type.md)un tipo.  
  
### <a name="static-listbindinghelper-methods"></a>Métodos estáticos de ListBindingHelper  
 Los <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>tipos <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, `DataMember` y <xref:System.Windows.Forms.BindingSource> comparten la lógica común para generar una lista a partir de `DataSource` un / par. Además, esta lógica común se expone públicamente para su uso por parte de los autores de controles y `static` otros terceros en los métodos siguientes:  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Ordenación y filtrado con la interfaz IBindingListView  
 El <xref:System.Windows.Forms.BindingSource> componente implementa la <xref:System.ComponentModel.IBindingListView> interfaz, que extiende la <xref:System.ComponentModel.IBindingList> interfaz. Ofrece una ordenación de una sola columna <xref:System.ComponentModel.IBindingListView> y ofrece ordenación y filtrado avanzados. <xref:System.ComponentModel.IBindingList> Con <xref:System.ComponentModel.IBindingListView>, puede ordenar y filtrar los elementos del origen de datos, si el origen de datos también implementa una de estas interfaces. El <xref:System.Windows.Forms.BindingSource> componente no proporciona una implementación de referencia de estos miembros. En su lugar, las llamadas se reenvían a la lista subyacente.  
  
 En la tabla siguiente se describen las propiedades que se usan para ordenar y filtrar.  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|Propiedad<xref:System.Windows.Forms.BindingSource.Filter%2A>|Si el origen de datos es una <xref:System.ComponentModel.IBindingListView>, obtiene o establece la expresión usada para filtrar qué filas se ven.|  
|Propiedad<xref:System.Windows.Forms.BindingSource.Sort%2A>|Si el origen de datos es una <xref:System.ComponentModel.IBindingList>, obtiene o establece el nombre de columna usado para ordenar y el criterio de ordenación.<br /><br /> -o bien-<br /><br /> Si el origen de datos es <xref:System.ComponentModel.IBindingListView> y admite la ordenación avanzada, obtiene varios nombres de columna usados para ordenar y ordenar.|  
  
### <a name="integration-with-bindingnavigator"></a>Integración con BindingNavigator  
 Puede utilizar el <xref:System.Windows.Forms.BindingSource> componente para enlazar cualquier control de Windows Forms a un origen de datos, <xref:System.Windows.Forms.BindingNavigator> pero el control está diseñado específicamente para trabajar <xref:System.Windows.Forms.BindingSource> con el componente. El <xref:System.Windows.Forms.BindingNavigator> control proporciona una interfaz de usuario para controlar <xref:System.Windows.Forms.BindingSource> el elemento actual del componente. De forma predeterminada, <xref:System.Windows.Forms.BindingNavigator> el control proporciona botones que corresponden a los métodos <xref:System.Windows.Forms.BindingSource> de navegación del componente. Para obtener más información, consulte [Cómo Navegue por los datos con el control](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)BindingNavigator Windows Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Información general sobre el componente BindingSource](bindingsource-component-overview.md)
- [BindingNavigator (control)](bindingnavigator-control-windows-forms.md)
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Procedimientos: Enlazar un control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Cómo: Reflejar las actualizaciones del origen de datos en un control de Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
