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
ms.openlocfilehash: 9f102b584d2ed0b5a9d2bbb0e7ce3f7871ec40b2
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046369"
---
# <a name="interfaces-related-to-data-binding"></a>Interfaces relacionadas con el enlace de datos

Con ADO.NET, puede crear muchas estructuras de datos diferentes para satisfacer las necesidades de enlace de la aplicación y los datos con los que está trabajando. Es posible que quiera crear sus propias clases que proporcionen o consuman datos en Windows Forms. Estos objetos pueden ofrecer varios niveles de funcionalidad y complejidad, desde el enlace de datos básico hasta proporcionar compatibilidad en tiempo de diseño, comprobación de errores, notificación de cambios o incluso compatibilidad con la reversión estructurada de los cambios hechos en los datos.

## <a name="consumers-of-data-binding-interfaces"></a>Consumidores de interfaces de enlace de datos

En las secciones siguientes se describen dos grupos de objetos de interfaz. El primer grupo muestra las interfaces que los autores de orígenes de datos implementan en los orígenes de datos. Estas interfaces están diseñadas para que los consumidores de orígenes de datos las usen, los que en muchos casos son controles o componentes de Windows Forms. En el segundo grupo se muestran interfaces diseñadas para su uso por parte de los autores de componentes. Los autores de componentes usan estas interfaces cuando crean un componente que admite que el motor de enlace de datos de Windows Forms use el enlace de datos. Puede implementar estas interfaces dentro de las clases asociadas con el formulario para habilitar el enlace de datos; en cada caso se presenta una clase que implementa una interfaz que permite interactuar con los datos. Las herramientas de experiencia de diseño de datos de desarrollo rápido de aplicaciones (RAD) de Visual Studio ya aprovechan esta funcionalidad.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfaces para la implementación por parte de los autores del origen de datos

Las interfaces siguientes están diseñadas para ser usadas por los controles de Windows Forms:

- <xref:System.Collections.IList>interfaz

  Una clase <xref:System.Collections.IList> que implementa la interfaz podría <xref:System.Array>ser, <xref:System.Collections.ArrayList>o <xref:System.Collections.CollectionBase>. Se trata de listas indizadas de elementos <xref:System.Object>de tipo. Estas listas deben contener tipos homogéneos, porque el primer elemento del índice determina el tipo. <xref:System.Collections.IList>solo estará disponible para el enlace en tiempo de ejecución.

  > [!NOTE]
  > Si desea crear una lista de objetos de negocio para enlazar con Windows Forms, debería considerar la <xref:System.ComponentModel.BindingList%601>posibilidad de usar. <xref:System.ComponentModel.BindingList%601> Es una clase extensible que implementa las interfaces principales necesarias para el enlace de datos de Windows Forms bidireccional.

- <xref:System.ComponentModel.IBindingList>interfaz

  Una clase que implementa la <xref:System.ComponentModel.IBindingList> interfaz proporciona un nivel mucho más alto de funcionalidad de enlace de datos. La implementación ofrece funcionalidades de ordenación y notificación de cambios, ambas para cuando los elementos de la lista cambian (por ejemplo, el tercer elemento de una lista de clientes tiene un cambio en el campo Address), así como cuando cambia la lista misma (por ejemplo, si el número de elementos de la lista aumenta o disminuye). La notificación de cambios es importante si planea tener varios controles enlazados a los mismos datos y desea que los cambios de datos que se hacen en uno de los controles se propague a los otros controles enlazados.

  > [!NOTE]
  > La notificación de cambios <xref:System.ComponentModel.IBindingList> está habilitada para la <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> interfaz a través de `true`la propiedad que <xref:System.ComponentModel.IBindingList.ListChanged> , cuando, genera un evento, que indica que la lista ha cambiado o que se ha cambiado un elemento de la lista.

  La <xref:System.ComponentModel.ListChangedType> propiedad<xref:System.ComponentModel.ListChangedEventArgs> del parámetro describe el tipo de cambio. Por lo tanto, siempre que se actualiza el modelo de datos, también se actualizará toda vista dependiente, como otros controles enlazados al mismo origen de datos. Sin embargo, los objetos contenidos en la lista tendrán que notificar la lista cuando cambien para que la lista pueda <xref:System.ComponentModel.IBindingList.ListChanged> generar el evento.

  > [!NOTE]
  > Proporciona una implementación genérica de la <xref:System.ComponentModel.IBindingList> interfaz. <xref:System.ComponentModel.BindingList%601>

- <xref:System.ComponentModel.IBindingListView>interfaz

  Una clase que implementa la <xref:System.ComponentModel.IBindingListView> interfaz proporciona toda la funcionalidad de una implementación de <xref:System.ComponentModel.IBindingList>, así como la funcionalidad de ordenación avanzada y filtrado. Esta implementación ofrece filtrado basado en cadena y ordenación en varias columnas con pares de descriptor de propiedad y dirección.

- <xref:System.ComponentModel.IEditableObject>interfaz

  Una clase que implementa la <xref:System.ComponentModel.IEditableObject> interfaz permite que un objeto controle cuándo se hacen permanentes los cambios en ese objeto. Esta implementación ofrece los <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>métodos, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , que permiten revertir los cambios realizados en el objeto. A continuación se proporciona una breve explicación del funcionamiento de <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>los <xref:System.ComponentModel.IEditableObject.EndEdit%2A>métodos, <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> y y cómo funcionan conjuntamente entre sí para habilitar una posible reversión de los cambios realizados en los datos:

  - El <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> método señala el inicio de una edición en un objeto. Un objeto que implemente esta interfaz tendrá que almacenar las actualizaciones después de la <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> llamada al método de manera que se puedan descartar las actualizaciones si se llama <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> al método. En el Windows Forms de enlace de datos, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> puede llamar varias veces dentro del ámbito de una única transacción de edición ( <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>por <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>ejemplo <xref:System.ComponentModel.IEditableObject.EndEdit%2A>,,,). Las implementaciones <xref:System.ComponentModel.IEditableObject> de deben realizar un seguimiento <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> de si ya se ha llamado a y omitir las llamadas subsiguientes a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Dado que se puede llamar a este método varias veces, es importante que las llamadas subsiguientes a ella sean no destructivas; es decir, las <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> llamadas subsiguientes no pueden destruir las actualizaciones que se han realizado o cambiar los datos que se <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> guardaron en la primera llamada.

  - El <xref:System.ComponentModel.IEditableObject.EndEdit%2A> método inserciones cualquier cambio desde <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> que se llamó al objeto subyacente, si el objeto está actualmente en modo de edición.

  - El <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> método descarta los cambios realizados en el objeto.

  Para obtener más información sobre cómo <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>funcionan <xref:System.ComponentModel.IEditableObject.EndEdit%2A>los métodos <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , y, vea [guardar datos en la base de datos](/visualstudio/data-tools/save-data-back-to-the-database).

  El control utiliza esta noción transaccional de la <xref:System.Windows.Forms.DataGridView> funcionalidad de datos.

- <xref:System.ComponentModel.ICancelAddNew>interfaz

  Una clase que implementa la <xref:System.ComponentModel.ICancelAddNew> interfaz normalmente implementa la <xref:System.ComponentModel.IBindingList> interfaz y permite revertir una adición realizada al origen de datos con el <xref:System.ComponentModel.IBindingList.AddNew%2A> método. Si el origen de datos implementa la <xref:System.ComponentModel.IBindingList> interfaz, también debe implementar la <xref:System.ComponentModel.ICancelAddNew> interfaz.

- <xref:System.ComponentModel.IDataErrorInfo>interfaz

  Una clase que implementa la <xref:System.ComponentModel.IDataErrorInfo> interfaz permite a los objetos ofrecer información de error personalizada a los controles enlazados:

  - La <xref:System.ComponentModel.IDataErrorInfo.Error%2A> propiedad devuelve el texto del mensaje de error general (por ejemplo, "se ha producido un error").

  - La <xref:System.ComponentModel.IDataErrorInfo.Item%2A> propiedad devuelve una cadena con el mensaje de error específico de la columna (por ejemplo, "el valor de `State` la columna no es válido").

- <xref:System.Collections.IEnumerable>interfaz

  Una clase que implementa la <xref:System.Collections.IEnumerable> interfaz suele ser utilizada por ASP.net. Windows Forms compatibilidad con esta interfaz solo está disponible a través <xref:System.Windows.Forms.BindingSource> del componente.

  > [!NOTE]
  > El <xref:System.Windows.Forms.BindingSource> componente copia todos <xref:System.Collections.IEnumerable> los elementos en una lista independiente para fines de enlace.

- <xref:System.ComponentModel.ITypedList>interfaz

  Una clase de colecciones que implementa la <xref:System.ComponentModel.ITypedList> interfaz proporciona la capacidad de controlar el orden y el conjunto de propiedades que se exponen al control enlazado.

  > [!NOTE]
  > Al implementar el <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> método y la <xref:System.ComponentModel.PropertyDescriptor> matriz no es null, la última entrada de la matriz será el descriptor de propiedad que describe la propiedad de lista que es otra lista de elementos.

- <xref:System.ComponentModel.ICustomTypeDescriptor>interfaz

  Una clase que implementa la <xref:System.ComponentModel.ICustomTypeDescriptor> interfaz proporciona información dinámica sobre sí misma. Esta interfaz es similar a <xref:System.ComponentModel.ITypedList> , pero se usa para objetos en lugar de listas. Utiliza esta interfaz <xref:System.Data.DataRowView> para proyectar el esquema de las filas subyacentes. <xref:System.ComponentModel.ICustomTypeDescriptor> La<xref:System.ComponentModel.CustomTypeDescriptor> clase proporciona una implementación simple de.

  > [!NOTE]
  > Para admitir el enlace en tiempo de diseño a los <xref:System.ComponentModel.ICustomTypeDescriptor>tipos que implementan, el <xref:System.ComponentModel.IComponent> tipo también debe implementar y existir como una instancia en el formulario.

- <xref:System.ComponentModel.IListSource>interfaz

  Una clase que implementa la interfaz <xref:System.ComponentModel.IListSource> habilita el enlace basado en lista en objetos que no son de lista. El <xref:System.ComponentModel.IListSource.GetList%2A> método de <xref:System.ComponentModel.IListSource> se utiliza para devolver una lista enlazable de un objeto que no hereda de <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource>la <xref:System.Data.DataSet> clase utiliza.

- <xref:System.ComponentModel.IRaiseItemChangedEvents>interfaz

  Una clase que implementa la <xref:System.ComponentModel.IRaiseItemChangedEvents> interfaz es una lista enlazable que también implementa la <xref:System.ComponentModel.IBindingList> interfaz. Esta interfaz se utiliza para indicar si el tipo genera <xref:System.ComponentModel.IBindingList.ListChanged> eventos de tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> a través <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> de su propiedad.

  > [!NOTE]
  > Debe implementar el <xref:System.ComponentModel.IRaiseItemChangedEvents> si el origen de datos proporciona la conversión de la propiedad a la lista de eventos que se ha descrito <xref:System.Windows.Forms.BindingSource> anteriormente y está interactuando con el componente. De lo contrario <xref:System.Windows.Forms.BindingSource> , también realizará la conversión de la propiedad para mostrar el evento de lista, con lo que el rendimiento será más lento.

- <xref:System.ComponentModel.ISupportInitialize>interfaz

  Un componente que implementa la <xref:System.ComponentModel.ISupportInitialize> interfaz aprovecha las ventajas de las optimizaciones por lotes para establecer las propiedades e inicializar las propiedades codependientes. <xref:System.ComponentModel.ISupportInitialize> Contiene dos métodos:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>indica que se está iniciando la inicialización del objeto.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>indica que la inicialización del objeto está finalizando.

- <xref:System.ComponentModel.ISupportInitializeNotification>interfaz

  Un componente que implementa la <xref:System.ComponentModel.ISupportInitializeNotification> interfaz también implementa la <xref:System.ComponentModel.ISupportInitialize> interfaz. Esta interfaz permite notificar a otros <xref:System.ComponentModel.ISupportInitialize> componentes que la inicialización se ha completado. La <xref:System.ComponentModel.ISupportInitializeNotification> interfaz contiene dos miembros:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>Devuelve un `boolean` valor que indica si el componente está inicializado.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized>se produce <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> cuando se llama a.

- <xref:System.ComponentModel.INotifyPropertyChanged>interfaz

  Una clase que implementa esta interfaz es un tipo que genera un evento cuando cambia cualquiera de sus valores de propiedad. Esta interfaz está diseñada para reemplazar el patrón de tener un evento de cambio para cada propiedad de un control. Cuando se usa en <xref:System.ComponentModel.BindingList%601>una, un objeto comercial debe implementar <xref:System.ComponentModel.INotifyPropertyChanged> la interfaz y la\`BindingList 1 convertirá <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> los <xref:System.ComponentModel.BindingList%601.ListChanged> eventos en eventos <xref:System.ComponentModel.ListChangedType.ItemChanged>de tipo.

  > [!NOTE]
  > Para que se produzca una notificación de cambios en un enlace entre un cliente enlazado y un origen de datos, el tipo de origen <xref:System.ComponentModel.INotifyPropertyChanged> de datos enlazado debe implementar la interfaz (preferida) o puede proporcionar los eventos *PropertyName* `Changed` para el tipo enlazado. pero no debe hacer ambas cosas.

### <a name="interfaces-for-implementation-by-component-authors"></a>Interfaces para la implementación por parte de los autores de componentes

Las interfaces siguientes están diseñadas para que las use el motor de enlace de datos de Windows Forms:

- <xref:System.Windows.Forms.IBindableComponent>interfaz

  Una clase que implementa esta interfaz es un componente no de control que admite el enlace de datos. Esta clase devuelve los enlaces de datos y el contexto de enlace del componente a <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> través <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> de las propiedades y de esta interfaz.

  > [!NOTE]
  > Si el componente hereda de <xref:System.Windows.Forms.Control>, no es necesario implementar la <xref:System.Windows.Forms.IBindableComponent> interfaz.

- <xref:System.Windows.Forms.ICurrencyManagerProvider>interfaz

  Una clase que implementa la <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaz es un componente que proporciona su propio <xref:System.Windows.Forms.CurrencyManager> objeto para administrar los enlaces asociados a este componente determinado. <xref:System.Windows.Forms.CurrencyManager> La<xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> propiedad proporciona acceso al personalizado.

  > [!NOTE]
  > Una clase que hereda de <xref:System.Windows.Forms.Control> administra los enlaces automáticamente a través de su <xref:System.Windows.Forms.Control.BindingContext%2A> propiedad, por lo que los <xref:System.Windows.Forms.ICurrencyManagerProvider> casos en los que es necesario implementar son bastante poco frecuentes.

## <a name="see-also"></a>Vea también

- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
- [Cómo: Crear un control de enlace simple en Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
