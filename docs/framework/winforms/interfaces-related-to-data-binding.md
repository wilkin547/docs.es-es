---
title: Interfaces relacionadas con el enlace de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 4e40f7ec1922cdf43e6a0b8f5734acaaeefbc514
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834589"
---
# <a name="interfaces-related-to-data-binding"></a>Interfaces relacionadas con el enlace de datos

Con ADO.NET, puede crear muchas estructuras de datos diferentes para satisfacer las necesidades de enlace de la aplicación y los datos con los que está trabajando. Es posible que quiera crear sus propias clases que proporcionen o consuman datos en Windows Forms. Estos objetos pueden ofrecer varios niveles de funcionalidad y complejidad, desde el enlace de datos básico hasta proporcionar compatibilidad en tiempo de diseño, comprobación de errores, notificación de cambios o incluso compatibilidad con la reversión estructurada de los cambios hechos en los datos.

## <a name="consumers-of-data-binding-interfaces"></a>Consumidores de interfaces de enlace de datos

En las secciones siguientes se describen dos grupos de objetos de interfaz. El primer grupo muestra las interfaces que los autores de orígenes de datos implementan en los orígenes de datos. Estas interfaces están diseñadas para que los consumidores de orígenes de datos las usen, los que en muchos casos son controles o componentes de Windows Forms. En el segundo grupo se muestran interfaces diseñadas para su uso por parte de los autores de componentes. Los autores de componentes usan estas interfaces cuando crean un componente que admite que el motor de enlace de datos de Windows Forms use el enlace de datos. Puede implementar estas interfaces dentro de las clases asociadas con el formulario para habilitar el enlace de datos; en cada caso se presenta una clase que implementa una interfaz que permite interactuar con los datos. Las herramientas de experiencia de diseño de datos de desarrollo rápido de aplicaciones (RAD) de Visual Studio ya aprovechan esta funcionalidad.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfaces para la implementación por parte de los autores del origen de datos

Las interfaces siguientes están diseñadas para ser usadas por los controles de Windows Forms:

- interfaz <xref:System.Collections.IList>

  Una clase que implementa la interfaz <xref:System.Collections.IList> podría ser una <xref:System.Array>, <xref:System.Collections.ArrayList>o <xref:System.Collections.CollectionBase>. Se trata de listas indizadas de elementos de tipo <xref:System.Object>. Estas listas deben contener tipos homogéneos, porque el primer elemento del índice determina el tipo. <xref:System.Collections.IList> solo estará disponible para el enlace en tiempo de ejecución.

  > [!NOTE]
  > Si desea crear una lista de objetos de negocio para enlazar con Windows Forms, considere la posibilidad de usar el <xref:System.ComponentModel.BindingList%601>. El <xref:System.ComponentModel.BindingList%601> es una clase extensible que implementa las interfaces principales necesarias para el enlace de datos de Windows Forms bidireccional.

- interfaz <xref:System.ComponentModel.IBindingList>

  Una clase que implementa la interfaz <xref:System.ComponentModel.IBindingList> proporciona un nivel mucho más alto de funcionalidad de enlace de datos. La implementación ofrece funcionalidades de ordenación y notificación de cambios, ambas para cuando los elementos de la lista cambian (por ejemplo, el tercer elemento de una lista de clientes tiene un cambio en el campo Address), así como cuando cambia la lista misma (por ejemplo, si el número de elementos de la lista aumenta o disminuye). La notificación de cambios es importante si planea tener varios controles enlazados a los mismos datos y desea que los cambios de datos que se hacen en uno de los controles se propague a los otros controles enlazados.

  > [!NOTE]
  > La notificación de cambios está habilitada para la interfaz de <xref:System.ComponentModel.IBindingList> a través de la propiedad <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> que, cuando se `true`, genera un evento <xref:System.ComponentModel.IBindingList.ListChanged>, que indica que la lista ha cambiado o que se ha cambiado un elemento de la lista.

  La propiedad <xref:System.ComponentModel.ListChangedType> del parámetro <xref:System.ComponentModel.ListChangedEventArgs> describe el tipo de cambio. Por lo tanto, siempre que se actualiza el modelo de datos, también se actualizará toda vista dependiente, como otros controles enlazados al mismo origen de datos. Sin embargo, los objetos contenidos en la lista tendrán que notificar la lista cuando cambien para que la lista pueda generar el evento <xref:System.ComponentModel.IBindingList.ListChanged>.

  > [!NOTE]
  > El <xref:System.ComponentModel.BindingList%601> proporciona una implementación genérica de la interfaz <xref:System.ComponentModel.IBindingList>.

- interfaz <xref:System.ComponentModel.IBindingListView>

  Una clase que implementa la interfaz <xref:System.ComponentModel.IBindingListView> proporciona toda la funcionalidad de una implementación de <xref:System.ComponentModel.IBindingList>, así como funcionalidad de filtrado y ordenación avanzada. Esta implementación ofrece filtrado basado en cadena y ordenación en varias columnas con pares de descriptor de propiedad y dirección.

- interfaz <xref:System.ComponentModel.IEditableObject>

  Una clase que implementa la interfaz <xref:System.ComponentModel.IEditableObject> permite que un objeto controle cuándo se hacen permanentes los cambios en ese objeto. Esta implementación le ofrece los métodos <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, que permiten revertir los cambios realizados en el objeto. A continuación se proporciona una breve explicación del funcionamiento de los métodos <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> y cómo funcionan conjuntamente entre sí para habilitar una posible reversión de los cambios realizados en los datos:

  - El método <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> señala el inicio de una edición en un objeto. Un objeto que implementa esta interfaz tendrá que almacenar las actualizaciones después de la llamada al método <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> de forma que las actualizaciones se puedan descartar si se llama al método <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>. En el Windows Forms de enlace de datos, puede llamar a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> varias veces dentro del ámbito de una única transacción de edición (por ejemplo, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Las implementaciones de <xref:System.ComponentModel.IEditableObject> deben realizar un seguimiento de si ya se ha llamado a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> y omitir las llamadas subsiguientes a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Dado que se puede llamar a este método varias veces, es importante que las llamadas subsiguientes a ella sean no destructivas; es decir, las llamadas subsiguientes <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> no pueden destruir las actualizaciones que se han realizado o cambiar los datos que se guardaron en la primera llamada <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>.

  - El método <xref:System.ComponentModel.IEditableObject.EndEdit%2A> inserciones cualquier cambio desde que se llamó a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> en el objeto subyacente, si el objeto está actualmente en modo de edición.

  - El método <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> descarta los cambios realizados en el objeto.

  Para obtener más información sobre cómo funcionan los métodos <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, vea [guardar datos en la base de datos](/visualstudio/data-tools/save-data-back-to-the-database).

  El control <xref:System.Windows.Forms.DataGridView> usa esta noción transaccional de la funcionalidad de datos.

- interfaz <xref:System.ComponentModel.ICancelAddNew>

  Una clase que implementa la interfaz <xref:System.ComponentModel.ICancelAddNew> normalmente implementa la interfaz <xref:System.ComponentModel.IBindingList> y permite revertir una adición realizada al origen de datos con el método <xref:System.ComponentModel.IBindingList.AddNew%2A>. Si el origen de datos implementa la interfaz <xref:System.ComponentModel.IBindingList>, también debe implementar la interfaz <xref:System.ComponentModel.ICancelAddNew>.

- interfaz <xref:System.ComponentModel.IDataErrorInfo>

  Una clase que implementa la interfaz <xref:System.ComponentModel.IDataErrorInfo> permite a los objetos ofrecer información de error personalizada a los controles enlazados:

  - La propiedad <xref:System.ComponentModel.IDataErrorInfo.Error%2A> devuelve el texto del mensaje de error general (por ejemplo, "se ha producido un error").

  - La propiedad <xref:System.ComponentModel.IDataErrorInfo.Item%2A> devuelve una cadena con el mensaje de error específico de la columna (por ejemplo, "el valor de la columna `State` no es válido").

- interfaz <xref:System.Collections.IEnumerable>

  ASP.NET suele usar una clase que implementa la interfaz <xref:System.Collections.IEnumerable>. Windows Forms compatibilidad con esta interfaz solo está disponible a través del componente de <xref:System.Windows.Forms.BindingSource>.

  > [!NOTE]
  > El componente <xref:System.Windows.Forms.BindingSource> copia todos los elementos de <xref:System.Collections.IEnumerable> en una lista independiente para el enlace.

- interfaz <xref:System.ComponentModel.ITypedList>

  Una clase de colecciones que implementa la interfaz <xref:System.ComponentModel.ITypedList> proporciona la capacidad de controlar el orden y el conjunto de propiedades que se exponen al control enlazado.

  > [!NOTE]
  > Al implementar el método de <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> y la matriz de <xref:System.ComponentModel.PropertyDescriptor> no es null, la última entrada de la matriz será el descriptor de propiedad que describe la propiedad de lista que es otra lista de elementos.

- interfaz <xref:System.ComponentModel.ICustomTypeDescriptor>

  Una clase que implementa la interfaz <xref:System.ComponentModel.ICustomTypeDescriptor> proporciona información dinámica sobre sí misma. Esta interfaz es similar a <xref:System.ComponentModel.ITypedList> pero se usa para objetos en lugar de listas. <xref:System.Data.DataRowView> usa esta interfaz para proyectar el esquema de las filas subyacentes. La clase <xref:System.ComponentModel.CustomTypeDescriptor> proporciona una implementación simple de <xref:System.ComponentModel.ICustomTypeDescriptor>.

  > [!NOTE]
  > Para admitir el enlace en tiempo de diseño a los tipos que implementan <xref:System.ComponentModel.ICustomTypeDescriptor>, el tipo también debe implementar <xref:System.ComponentModel.IComponent> y existir como una instancia en el formulario.

- interfaz <xref:System.ComponentModel.IListSource>

  Una clase que implementa la interfaz <xref:System.ComponentModel.IListSource> habilita el enlace basado en lista en objetos que no son de lista. El método <xref:System.ComponentModel.IListSource.GetList%2A> de <xref:System.ComponentModel.IListSource> se utiliza para devolver una lista enlazable de un objeto que no hereda de <xref:System.Collections.IList>. la clase <xref:System.Data.DataSet> utiliza <xref:System.ComponentModel.IListSource>.

- interfaz <xref:System.ComponentModel.IRaiseItemChangedEvents>

  Una clase que implementa la interfaz <xref:System.ComponentModel.IRaiseItemChangedEvents> es una lista enlazable que también implementa la interfaz <xref:System.ComponentModel.IBindingList>. Esta interfaz se utiliza para indicar si el tipo genera eventos <xref:System.ComponentModel.IBindingList.ListChanged> de tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> a través de su propiedad <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A>.

  > [!NOTE]
  > Debe implementar el <xref:System.ComponentModel.IRaiseItemChangedEvents> si el origen de datos proporciona la conversión de la propiedad a la lista de eventos que se ha descrito anteriormente y está interactuando con el componente <xref:System.Windows.Forms.BindingSource>. De lo contrario, el <xref:System.Windows.Forms.BindingSource> también realizará la conversión de la propiedad en la lista de eventos, lo que provocará un rendimiento más lento.

- interfaz <xref:System.ComponentModel.ISupportInitialize>

  Un componente que implementa la interfaz de <xref:System.ComponentModel.ISupportInitialize> aprovecha las ventajas de las optimizaciones por lotes para establecer las propiedades e inicializar las propiedades codependientes. El <xref:System.ComponentModel.ISupportInitialize> contiene dos métodos:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> indica que se está iniciando la inicialización del objeto.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> indica que finaliza la inicialización del objeto.

- interfaz <xref:System.ComponentModel.ISupportInitializeNotification>

  Un componente que implementa la interfaz <xref:System.ComponentModel.ISupportInitializeNotification> también implementa la interfaz <xref:System.ComponentModel.ISupportInitialize>. Esta interfaz permite notificar a otros componentes de <xref:System.ComponentModel.ISupportInitialize> que la inicialización se ha completado. La interfaz <xref:System.ComponentModel.ISupportInitializeNotification> contiene dos miembros:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> devuelve un valor `boolean` que indica si el componente está inicializado.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> se produce cuando se llama a <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>.

- interfaz <xref:System.ComponentModel.INotifyPropertyChanged>

  Una clase que implementa esta interfaz es un tipo que genera un evento cuando cambia cualquiera de sus valores de propiedad. Esta interfaz está diseñada para reemplazar el patrón de tener un evento de cambio para cada propiedad de un control. Cuando se usa en una <xref:System.ComponentModel.BindingList%601>, un objeto comercial debe implementar la interfaz de <xref:System.ComponentModel.INotifyPropertyChanged> y la BindingList\`1 convertirá <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos en <xref:System.ComponentModel.BindingList%601.ListChanged> eventos de tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.

  > [!NOTE]
  > Para que se produzca la notificación de cambios en un enlace entre un cliente enlazado y un origen de datos, el tipo de origen de datos enlazado debe implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> (preferida) o puede proporcionar los eventos *propertyName*`Changed` para el tipo enlazado, pero no debe hacer ambas cosas.

### <a name="interfaces-for-implementation-by-component-authors"></a>Interfaces para la implementación por parte de los autores de componentes

Las interfaces siguientes están diseñadas para que las use el motor de enlace de datos de Windows Forms:

- interfaz <xref:System.Windows.Forms.IBindableComponent>

  Una clase que implementa esta interfaz es un componente no de control que admite el enlace de datos. Esta clase devuelve los enlaces de datos y el contexto de enlace del componente a través de las propiedades <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> y <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> de esta interfaz.

  > [!NOTE]
  > Si el componente hereda de <xref:System.Windows.Forms.Control>, no es necesario implementar la interfaz de <xref:System.Windows.Forms.IBindableComponent>.

- interfaz <xref:System.Windows.Forms.ICurrencyManagerProvider>

  Una clase que implementa la interfaz <xref:System.Windows.Forms.ICurrencyManagerProvider> es un componente que proporciona su propio <xref:System.Windows.Forms.CurrencyManager> para administrar los enlaces asociados a este componente determinado. La propiedad <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> proporciona el acceso a la <xref:System.Windows.Forms.CurrencyManager> personalizada.

  > [!NOTE]
  > Una clase que hereda de <xref:System.Windows.Forms.Control> administra los enlaces automáticamente a través de su propiedad <xref:System.Windows.Forms.Control.BindingContext%2A>, por lo que los casos en los que es necesario implementar la <xref:System.Windows.Forms.ICurrencyManagerProvider> son bastante poco frecuentes.

## <a name="see-also"></a>Vea también

- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
- [Crear un control con enlace simple en Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
