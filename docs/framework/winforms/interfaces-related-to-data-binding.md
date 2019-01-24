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
ms.openlocfilehash: 5a83198a665563c3d283cac042c9fec95c60f8e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547136"
---
# <a name="interfaces-related-to-data-binding"></a>Interfaces relacionadas con el enlace de datos
Con [!INCLUDE[vstecado](../../../includes/vstecado-md.md)], puede crear varias estructuras de datos distintas para satisfacer las necesidades de enlace de la aplicación y los datos con los que trabaja. Es posible que quiera crear sus propias clases que proporcionen o consuman datos en Windows Forms. Estos objetos pueden ofrecer varios niveles de funcionalidad y complejidad, desde el enlace de datos básico hasta proporcionar compatibilidad en tiempo de diseño, comprobación de errores, notificación de cambios o incluso compatibilidad con la reversión estructurada de los cambios hechos en los datos.  
  
## <a name="consumers-of-data-binding-interfaces"></a>Consumidores de interfaces de enlace de datos  
 En las secciones siguientes se describen dos grupos de objetos de interfaz. El primer grupo muestra las interfaces que los autores de orígenes de datos implementan en los orígenes de datos. Estas interfaces están diseñadas para que los consumidores de orígenes de datos las usen, los que en muchos casos son controles o componentes de Windows Forms. En el segundo grupo se muestran interfaces diseñadas para su uso por parte de los autores de componentes. Los autores de componentes usan estas interfaces cuando crean un componente que admite que el motor de enlace de datos de Windows Forms use el enlace de datos. Puede implementar estas interfaces dentro de las clases asociadas con el formulario para habilitar el enlace de datos; en cada caso se presenta una clase que implementa una interfaz que permite interactuar con los datos. Herramientas visuales Studio rapid application development (RAD) datos diseño experiencia ya aprovechan esta funcionalidad.  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfaces para la implementación por parte de los autores del origen de datos  
 Las interfaces siguientes están diseñadas para ser usadas por los controles de Windows Forms:  
  
-   <xref:System.Collections.IList> (interfaz)  
  
     Una clase que implementa el <xref:System.Collections.IList> interfaz podría ser un <xref:System.Array>, <xref:System.Collections.ArrayList>, o <xref:System.Collections.CollectionBase>. Son listas indexadas de elementos de tipo <xref:System.Object>. Estas listas deben contener tipos homogéneos, porque el primer elemento del índice determina el tipo. <xref:System.Collections.IList> estaría disponible para el enlace en tiempo de ejecución.  
  
    > [!NOTE]
    >  Si desea crear una lista de objetos de negocios para enlace con Windows Forms, considere la posibilidad de usar el <xref:System.ComponentModel.BindingList%601>. El <xref:System.ComponentModel.BindingList%601> es una clase extensible que implementa las interfaces principales necesarias para el enlace de datos bidireccional de Windows Forms.  
  
-   <xref:System.ComponentModel.IBindingList> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.IBindingList> interfaz proporciona un nivel mucho mayor de funcionalidad de enlace de datos. La implementación ofrece funcionalidades de ordenación y notificación de cambios, ambas para cuando los elementos de la lista cambian (por ejemplo, el tercer elemento de una lista de clientes tiene un cambio en el campo Address), así como cuando cambia la lista misma (por ejemplo, si el número de elementos de la lista aumenta o disminuye). La notificación de cambios es importante si planea tener varios controles enlazados a los mismos datos y desea que los cambios de datos que se hacen en uno de los controles se propague a los otros controles enlazados.  
  
    > [!NOTE]
    >  Notificación de cambios está habilitada para la <xref:System.ComponentModel.IBindingList> interfaz a través de la <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> propiedad que, cuando `true`, provoca una <xref:System.ComponentModel.IBindingList.ListChanged> eventos, que indica la lista puede cambiar o un elemento en la lista puede cambiar.  
  
     Se describe el tipo de cambio mediante la <xref:System.ComponentModel.ListChangedType> propiedad de la <xref:System.ComponentModel.ListChangedEventArgs> parámetro. Por lo tanto, siempre que se actualiza el modelo de datos, también se actualizará toda vista dependiente, como otros controles enlazados al mismo origen de datos. Sin embargo, los objetos contenidos en la lista deberán notificar a la lista cuando cambian de modo que puede generar la lista el <xref:System.ComponentModel.IBindingList.ListChanged> eventos.  
  
    > [!NOTE]
    >  El <xref:System.ComponentModel.BindingList%601> proporciona una implementación genérica de la <xref:System.ComponentModel.IBindingList> interfaz.  
  
-   <xref:System.ComponentModel.IBindingListView> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.IBindingListView> interfaz proporciona toda la funcionalidad de una implementación de <xref:System.ComponentModel.IBindingList>, así como filtrado y avanzada funcionalidad de ordenación. Esta implementación ofrece filtrado basado en cadena y ordenación en varias columnas con pares de descriptor de propiedad y dirección.  
  
-   <xref:System.ComponentModel.IEditableObject> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.IEditableObject> interfaz permite que un objeto controle cuándo se hacen permanentes los cambios a ese objeto. Esta implementación ofrece la <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> métodos, lo que le permite revertir los cambios realizados en el objeto. La siguiente es una breve explicación del funcionamiento de la <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> métodos y cómo funcionan entre sí para habilitar la posibilidad de revertir los cambios realizados en los datos:  
  
    -   El <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> método señala el inicio de la edición de un objeto. Un objeto que implementa esta interfaz necesitará almacenar las actualizaciones tras el <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> llamada al método de tal manera que las actualizaciones se pueden descartar si el <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> se llama al método. En Windows Forms de enlace de datos, se puede llamar a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> varias veces dentro del ámbito de una sola transacción de edición (por ejemplo, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Las implementaciones de <xref:System.ComponentModel.IEditableObject> debe realizar un seguimiento de si <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> ya se ha llamado y omitir las llamadas subsiguientes a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Dado que este método puede llamarse varias veces, es importante que las llamadas subsiguientes sean destructivas; es decir, posteriores <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> llamadas no pueden destruir las actualizaciones que se han realizado o cambian los datos que se guardan en la primera <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> llamar.  
  
    -   El <xref:System.ComponentModel.IEditableObject.EndEdit%2A> método inserta los cambios realizados desde <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> llamó en el objeto subyacente, si el objeto está actualmente en modo de edición.  
  
    -   El <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> método descarta los cambios realizados en el objeto.  
  
     Para obtener más información acerca de cómo los <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> métodos de trabajo, consulte [guardar los datos en la base de datos](/visualstudio/data-tools/save-data-back-to-the-database).  
  
     Esta noción transaccional de la funcionalidad de datos está usando el <xref:System.Windows.Forms.DataGridView> control.  
  
-   <xref:System.ComponentModel.ICancelAddNew> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.ICancelAddNew> normalmente implementa la interfaz de la <xref:System.ComponentModel.IBindingList> interfaz y le permite revertir una incorporación hecha en el origen de datos con el <xref:System.ComponentModel.IBindingList.AddNew%2A> método. Si el origen de datos implementa la <xref:System.ComponentModel.IBindingList> interfaz, también debe tener implementar el <xref:System.ComponentModel.ICancelAddNew> interfaz.  
  
-   <xref:System.ComponentModel.IDataErrorInfo> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.IDataErrorInfo> interfaz permite que los objetos ofrezcan información de error personalizada a los controles enlazados:  
  
    -   El <xref:System.ComponentModel.IDataErrorInfo.Error%2A> propiedad devuelve el texto del mensaje de error general (por ejemplo, "se produjo un error").  
  
    -   El <xref:System.ComponentModel.IDataErrorInfo.Item%2A> propiedad devuelve una cadena con el mensaje de error específico de la columna (por ejemplo, "el valor de la `State` columna no es válida").  
  
-   <xref:System.Collections.IEnumerable> (interfaz)  
  
     Una clase que implementa el <xref:System.Collections.IEnumerable> normalmente consume interfaz [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Soporte técnico de Windows Forms para esta interfaz solo está disponible a través de la <xref:System.Windows.Forms.BindingSource> componente.  
  
    > [!NOTE]
    >  El <xref:System.Windows.Forms.BindingSource> componente copia todos <xref:System.Collections.IEnumerable> elementos en una lista independiente para fines de enlace.  
  
-   <xref:System.ComponentModel.ITypedList> (interfaz)  
  
     Una clase de colección que implementa el <xref:System.ComponentModel.ITypedList> interfaz proporciona la capacidad para controlar el orden y el conjunto de propiedades expuestas al control enlazado.  
  
    > [!NOTE]
    >  Cuando se implementa el <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> método y el <xref:System.ComponentModel.PropertyDescriptor> array no es null, la última entrada de la matriz será el descriptor de propiedad que describe la propiedad de lista que es otra lista de elementos.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.ICustomTypeDescriptor> interfaz proporciona información dinámica sobre sí mismo. Esta interfaz es similar a <xref:System.ComponentModel.ITypedList> , pero se utiliza para objetos en lugar de listas. Esta interfaz se usa por <xref:System.Data.DataRowView> para proyectar el esquema de las filas subyacentes. Una implementación sencilla de <xref:System.ComponentModel.ICustomTypeDescriptor> proporcionada por el <xref:System.ComponentModel.CustomTypeDescriptor> clase.  
  
    > [!NOTE]
    >  Para admitir el enlace de tiempo de diseño para los tipos que implementan <xref:System.ComponentModel.ICustomTypeDescriptor>, también debe implementar el tipo <xref:System.ComponentModel.IComponent> y existir como una instancia en el formulario.  
  
-   <xref:System.ComponentModel.IListSource> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.IListSource> interfaz permite que el enlace basado en objetos fuera de la lista. El <xref:System.ComponentModel.IListSource.GetList%2A> método <xref:System.ComponentModel.IListSource> se usa para devolver una lista enlazable desde un objeto que no hereda de <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource> está usando el <xref:System.Data.DataSet> clase.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents> (interfaz)  
  
     Una clase que implementa el <xref:System.ComponentModel.IRaiseItemChangedEvents> interfaz es una lista enlazable que también implementa la <xref:System.ComponentModel.IBindingList> interfaz. Esta interfaz se utiliza para indicar si el tipo genera <xref:System.ComponentModel.IBindingList.ListChanged> eventos de tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> a través de su <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> propiedad.  
  
    > [!NOTE]
    >  Debe implementar la <xref:System.ComponentModel.IRaiseItemChangedEvents> si el origen de datos proporciona la propiedad a la conversión de eventos de lista se ha descrito anteriormente e interactúa con el <xref:System.Windows.Forms.BindingSource> componente. En caso contrario, el <xref:System.Windows.Forms.BindingSource> también llevan a cabo la propiedad a la conversión de eventos de lista resultante en un rendimiento más lento.  
  
-   <xref:System.ComponentModel.ISupportInitialize> (interfaz)  
  
     Un componente que implementa el <xref:System.ComponentModel.ISupportInitialize> interfaz aprovecha las ventajas de las optimizaciones por lotes para establecer las propiedades e inicializar las propiedades codependientes. El <xref:System.ComponentModel.ISupportInitialize> contiene dos métodos:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> indica que la inicialización del objeto se está iniciando.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> indica que la inicialización del objeto está finalizando.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification> (interfaz)  
  
     Un componente que implementa el <xref:System.ComponentModel.ISupportInitializeNotification> interfaz también implementa el <xref:System.ComponentModel.ISupportInitialize> interfaz. Esta interfaz permite notificar a otros <xref:System.ComponentModel.ISupportInitialize> componentes que la inicialización está completa. El <xref:System.ComponentModel.ISupportInitializeNotification> interfaz contiene dos miembros:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> Devuelve un `boolean` valor que indica si se ha inicializado el componente.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> se produce cuando <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> se llama.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged> (interfaz)  
  
     Una clase que implementa esta interfaz es un tipo que genera un evento cuando cambia cualquiera de sus valores de propiedad. Esta interfaz está diseñada para reemplazar el patrón de tener un evento de cambio para cada propiedad de un control. Cuando se usa en un <xref:System.ComponentModel.BindingList%601>, debe implementar un objeto de negocios la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz y BindingList\`1 convertirá <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos a <xref:System.ComponentModel.BindingList%601.ListChanged> eventos de tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
    > [!NOTE]
    >  Para cambiar notificación que se produzca en un enlace entre un cliente enlazado y datos de origen de tipo de origen de datos enlazado debería implementar el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz (opción preferida) o bien puede proporcionar *propertyName* `Changed` los eventos para el tipo enlazado, pero no ambos.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>Interfaces para la implementación por parte de los autores de componentes  
 Las interfaces siguientes están diseñadas para que las use el motor de enlace de datos de Windows Forms:  
  
-   <xref:System.Windows.Forms.IBindableComponent> (interfaz)  
  
     Una clase que implementa esta interfaz es un componente no de control que admite el enlace de datos. Esta clase devuelve los enlaces de datos y el contexto de enlace del componente a través de la <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> y <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> las propiedades de esta interfaz.  
  
    > [!NOTE]
    >  Si el componente hereda de <xref:System.Windows.Forms.Control>, deberá implementar la <xref:System.Windows.Forms.IBindableComponent> interfaz.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider> (interfaz)  
  
     Una clase que implementa el <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaz es un componente que proporciona su propio <xref:System.Windows.Forms.CurrencyManager> para administrar los enlaces asociados a este componente determinado. Acceso a la personalizada <xref:System.Windows.Forms.CurrencyManager> proporcionada por el <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> propiedad.  
  
    > [!NOTE]
    >  Una clase que hereda de <xref:System.Windows.Forms.Control> administra enlaces automáticamente mediante su <xref:System.Windows.Forms.Control.BindingContext%2A> propiedad, por lo que casos en que necesite implementar el <xref:System.Windows.Forms.ICurrencyManagerProvider> muy poco frecuente.  
  
## <a name="see-also"></a>Vea también
- [Enlace de datos y Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
- [Cómo: Crear un Control con enlace Simple en un formulario de Windows](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
