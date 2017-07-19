---
title: "Interfaces relacionadas con el enlace de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "datos [Windows Forms], interfaces de enlace de datos"
  - "enlace de datos, interfaces"
  - "IBindingList (interfaz), enlace de datos en formularios Windows Forms"
  - "IBindingListView (interfaz)"
  - "IDataErrorInfo (interfaz), enlace de datos en formularios Windows Forms"
  - "IEditableObject (interfaz), enlace de datos en formularios Windows Forms"
  - "IList (interfaz), enlace de datos en formularios Windows Forms"
  - "INotifyPropertyChanged (interfaz)"
  - "interfaces, enlace de datos en formularios Windows Forms"
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Interfaces relacionadas con el enlace de datos
Con [!INCLUDE[vstecado](../../../includes/vstecado-md.md)], puede crear muchas estructuras de datos distintas para satisfacer las necesidades de enlace de la aplicación y de los datos con los que trabaja.  Quizá desee crear sus propias clases que proporcionen o utilicen datos de formularios Windows Forms.  Estos objetos pueden ofrecer diversos niveles de funcionalidad y complejidad, desde el enlace básico de datos hasta la compatibilidad en tiempo de diseño, la comprobación de errores, la notificación de cambios o, incluso, la compatibilidad con una reversión estructurada de las modificaciones realizadas en los propios datos.  
  
## Consumidores de interfaces de enlace de datos  
 En las secciones siguientes se describen dos grupos de objetos de interfaz.  El primer grupo muestra interfaces que se implementan en orígenes de datos por autores de orígenes de datos.  Estas interfaces están diseñadas para que consumidores del origen de datos las utilicen, que la mayoría de los casos son controles o componentes de formularios Windows Forms.  El segundo grupo muestra interfaces diseñadas para que las utilicen los autores de componentes.  Los autores de componentes utilizan estas interfaces cuando crean componentes que admiten que el motor de enlace de datos de formularios Windows Forms utilice el enlace de datos.  Estas interfaces pueden implementarse en las clases asociadas al formulario para habilitar el enlace de datos; cada caso presenta una clase que implementa una interfaz que habilita la interacción con los datos.  Las herramientas con experiencia en diseño de datos de desarrollo rápido de aplicaciones \(RAD\) de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ya aprovechan esta funcionalidad.  
  
### Interfaces para la implementación de los autores de orígenes de datos  
 Las interfaces siguientes están diseñadas para ser utilizadas por controles de formularios Windows Forms:  
  
-   La interfaz <xref:System.Collections.IList>  
  
     Una clase que implementa la interfaz <xref:System.Collections.IList> podría ser <xref:System.Array>, <xref:System.Collections.ArrayList> o <xref:System.Collections.CollectionBase>.  Estas son listas de elementos indizadas de tipo <xref:System.Object>.  Estas listas deben contener tipos homogéneos porque el primer elemento del índice determina el tipo.  <xref:System.Collections.IList> solo debe estar disponible para el enlace en tiempo de ejecución.  
  
    > [!NOTE]
    >  Si desea crear una lista de objetos comerciales para enlaces con formularios Windows Forms, considere utilizar la clase <xref:System.ComponentModel.BindingList%601>.  <xref:System.ComponentModel.BindingList%601> es una clase extensible que implementa las interfaces principales necesarias para el enlace de datos bidireccional de formularios Windows Forms.  
  
-   La interfaz <xref:System.ComponentModel.IBindingList>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.IBindingList> proporciona un nivel mucho mayor de funcionalidad de enlace de datos.  Esta implementación ofrece posibilidades de ordenación básicas y notificación de cambios, ambas para cuando cambian los elementos de lista \(por ejemplo, el tercer elemento de una lista de clientes tiene un cambio en el campo Dirección\), así como cuando cambia la lista en sí \(por ejemplo, aumenta o disminuye el número de elementos de la lista\).  Es importante la notificación de cambios si tiene previsto tener varios controles enlazados a los mismos datos y desea que los cambios de datos realizados en uno de los controles se propaguen a los demás controles enlazados.  
  
    > [!NOTE]
    >  La notificación de cambios para la interfaz <xref:System.ComponentModel.IBindingList> se habilita mediante la propiedad <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> que, cuando es `true`, provoca un evento <xref:System.ComponentModel.IBindingList.ListChanged>, que indica que ha cambiado la lista o un elemento de la lista.  
  
     La propiedad <xref:System.ComponentModel.ListChangedType> del parámetro <xref:System.ComponentModel.ListChangedEventArgs> describe el tipo de cambio.  Por lo tanto, cada vez que se actualiza el modelo de datos, cualquier vista dependiente, como otros controles enlazados al mismo origen de datos, también se actualizará.  No obstante, cuando los objetos contenidos en la lista cambien deberán enviar una notificación a la lista, para que ésta pueda provocar el evento <xref:System.ComponentModel.IBindingList.ListChanged>.  
  
    > [!NOTE]
    >  La clase <xref:System.ComponentModel.BindingList%601> proporciona una implementación genérica de la interfaz <xref:System.ComponentModel.IBindingList>.  
  
-   La interfaz <xref:System.ComponentModel.IBindingListView>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.IBindingListView> proporciona todas las funciones de una implementación de <xref:System.ComponentModel.IBindingList>, así como funciones de filtrado y ordenación avanzada.  Esta implementación proporciona el filtrado basado en cadena y la ordenación multicolumna con pares de descriptor de propiedad y dirección.  
  
-   La interfaz <xref:System.ComponentModel.IEditableObject>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.IEditableObject> permite que un objeto controle cuándo se hacen permanentes los cambios realizados en el objeto.  Esta implementación ofrece los métodos <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, que le permiten revertir los cambios realizados en el objeto.  A continuación figura una breve descripción del funcionamiento de los métodos <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> y cómo funcionan entre ellos para permitir la posibilidad de revertir los cambios realizados en los datos:  
  
    -   El método <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> señala el inicio de una modificación de un objeto.  Un objeto que implemente esta interfaz necesitará almacenar las actualizaciones que se produzcan después de la llamada al método <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> de modo que puedan descartarse las actualizaciones si se llama al método <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>.  En el enlace de datos de formularios Windows Forms, puede llamar varias veces al método <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> dentro del ámbito de una transacción de edición única \(por ejemplo, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>\).  Las implementaciones de <xref:System.ComponentModel.IEditableObject> deberían mantener el seguimiento que comprueba si se ha llamado ya al método <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> y omitir las llamadas subsiguientes a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>.  Dado que es posible llamar varias veces a este método, es importante que las llamadas subsiguientes no sean destructivas; es decir, las llamadas subsiguientes a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> no pueden destruir las actualizaciones realizadas ni modificar los datos guardados en la primera llamada a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>.  
  
    -   El método <xref:System.ComponentModel.IEditableObject.EndEdit%2A> inserta en el objeto subyacente los cambios realizados desde la llamada a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, si el objeto se encuentra en modo de edición.  
  
    -   El método <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> descarta los cambios realizados en el objeto.  
  
     Para obtener más información sobre cómo funcionan los métodos: <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> y <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, vea [Guardar los datos en conjuntos de datos](../Topic/Save%20data%20back%20to%20the%20database.md).  
  
     El control <xref:System.Windows.Forms.DataGridView> utiliza esta noción transaccional de funciones de datos.  
  
-   La interfaz <xref:System.ComponentModel.ICancelAddNew>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.ICancelAddNew> normalmente implementa la interfaz <xref:System.ComponentModel.IBindingList> y permite revertir las agregaciones realizadas en el origen de datos con el método <xref:System.ComponentModel.IBindingList.AddNew%2A>.  Si el origen de datos implementa la interfaz <xref:System.ComponentModel.IBindingList>, establezca también que implemente la interfaz <xref:System.ComponentModel.ICancelAddNew>.  
  
-   La interfaz <xref:System.ComponentModel.IDataErrorInfo>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.IDataErrorInfo> permite a los objetos ofrecer la información de error personalizada a los controles enlazados:  
  
    -   La propiedad <xref:System.ComponentModel.IDataErrorInfo.Error%2A> devuelve un texto de mensaje de error general \(por ejemplo, "Se produjo un error"\).  
  
    -   La propiedad <xref:System.ComponentModel.IDataErrorInfo.Item%2A> devuelve una cadena con el mensaje de error específico de la columna \(por ejemplo, "El valor de la columna `State`  no es válido"\).  
  
-   La interfaz <xref:System.Collections.IEnumerable>  
  
     [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] utiliza normalmente una clase que implementa la interfaz <xref:System.Collections.IEnumerable>.  Sólo está disponible la compatibilidad de formularios Windows Forms con esta interfaz a través del componente <xref:System.Windows.Forms.BindingSource>.  
  
    > [!NOTE]
    >  El componente <xref:System.Windows.Forms.BindingSource> copia todos los elementos <xref:System.Collections.IEnumerable> en una lista independiente para fines de enlace.  
  
-   La interfaz <xref:System.ComponentModel.ITypedList>  
  
     Una clase de colecciones que implementa la interfaz <xref:System.ComponentModel.ITypedList> proporciona la posibilidad de controlar el orden y el conjunto de propiedades expuestas al control enlazado.  
  
    > [!NOTE]
    >  Cuando implementa el método <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> y la matriz <xref:System.ComponentModel.PropertyDescriptor> no es null, la última entrada de la matriz será el descriptor de propiedad que describe la propiedad de lista que es otra lista de elementos.  
  
-   La interfaz <xref:System.ComponentModel.ICustomTypeDescriptor>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.ICustomTypeDescriptor> proporciona información dinámica sobre sí misma.  Esta interfaz es similar a <xref:System.ComponentModel.ITypedList> pero la utilizan objetos en lugar de listas.  <xref:System.Data.DataRowView> utiliza esta interfaz para proyectar el esquema de las filas subyacentes.  La clase <xref:System.ComponentModel.CustomTypeDescriptor> proporciona una implementación sencilla de <xref:System.ComponentModel.ICustomTypeDescriptor>.  
  
    > [!NOTE]
    >  Para admitir el enlace en tiempo de diseño a tipos que implementan <xref:System.ComponentModel.ICustomTypeDescriptor>, el tipo debe implementar también <xref:System.ComponentModel.IComponent> y existir como una instancia en el formulario.  
  
-   La interfaz <xref:System.ComponentModel.IListSource>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.IListSource> habilita el enlace basado en lista en objetos que no son lista.  El método <xref:System.ComponentModel.IListSource.GetList%2A> de <xref:System.ComponentModel.IListSource> se usa para devolver una lista enlazable de un objeto que no hereda de <xref:System.Collections.IList>.  La clase <xref:System.Data.DataSet> utiliza <xref:System.ComponentModel.IListSource>.  
  
-   La interfaz <xref:System.ComponentModel.IRaiseItemChangedEvents>  
  
     Una clase que implementa la interfaz <xref:System.ComponentModel.IRaiseItemChangedEvents> es una lista enlazable que también implementa la interfaz <xref:System.ComponentModel.IBindingList>.  Esta interfaz se utiliza para indicar si su tipo provoca eventos <xref:System.ComponentModel.IBindingList.ListChanged> de tipo <xref:System.ComponentModel.ListChangedType> a través de la propiedad <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A>.  
  
    > [!NOTE]
    >  Implemente <xref:System.ComponentModel.IRaiseItemChangedEvents> si el origen de datos proporciona la conversión de propiedad a evento de lista descrita anteriormente e interactúa con el componente <xref:System.Windows.Forms.BindingSource>.  De lo contrario, <xref:System.Windows.Forms.BindingSource> también ejecutará la conversión de propiedad a evento de lista, lo que provocará un rendimiento más lento.  
  
-   La interfaz <xref:System.ComponentModel.ISupportInitialize>  
  
     Un componente que implementa la interfaz <xref:System.ComponentModel.ISupportInitialize> aprovecha las ventajas de las optimizaciones por lotes para establecer las propiedades e inicializar propiedades codependientes.  <xref:System.ComponentModel.ISupportInitialize> contiene dos métodos:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> señala que comienza la inicialización del objeto.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> señala que finaliza la inicialización del objeto.  
  
-   La interfaz <xref:System.ComponentModel.ISupportInitializeNotification>  
  
     Un componente que implementa la interfaz <xref:System.ComponentModel.ISupportInitializeNotification> también implementa la interfaz <xref:System.ComponentModel.ISupportInitialize>.  Esta interfaz permite notificar a otros componentes <xref:System.ComponentModel.ISupportInitialize> que la inicialización está completa.  La interfaz <xref:System.ComponentModel.ISupportInitializeNotification> contiene dos miembros:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> devuelve un valor `boolean` que indica si se inicializa el componente.  
  
    -   Se produce el evento <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> cuando se llama al método <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>.  
  
-   La interfaz <xref:System.ComponentModel.INotifyPropertyChanged>  
  
     Una clase que implementa esta interfaz es un tipo que provoca un evento cuando cualquiera de sus valores de propiedad cambia.  Esta interfaz está diseñada para reemplazar al modelo de tener un evento de cambio para cada propiedad de un control.  Cuando se utiliza en una clase <xref:System.ComponentModel.BindingList%601>, un objeto comercial debe implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y BindingList\`1 convertirá los eventos <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> a eventos <xref:System.ComponentModel.BindingList%601.ListChanged> de tipo <xref:System.ComponentModel.ListChangedType>.  
  
    > [!NOTE]
    >  Para que se produzca la notificación de cambios en un enlace entre un cliente enlazado y un origen de datos, o el tipo de origen de datos enlazado implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> \(preferido\) o puede proporcionar eventos *nombreDePropiedad*`Changed` para el tipo enlazado, pero no ambos.  
  
### Interfaces para la implementación por creadores de componente  
 Las interfaces siguientes están diseñadas para que las utilice el motor de enlace de datos de formularios Windows Forms:  
  
-   La interfaz <xref:System.Windows.Forms.IBindableComponent>  
  
     Una clase que implementa esta interfaz es un componente que no sea un control que admite el enlace de datos.  Esta clase devuelve los enlaces de datos y el contexto de enlace del componente a través de las propiedades <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> y <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> de esta interfaz.  
  
    > [!NOTE]
    >  Si el componente hereda de <xref:System.Windows.Forms.Control>, no tiene que implementar la interfaz <xref:System.Windows.Forms.IBindableComponent>.  
  
-   La interfaz <xref:System.Windows.Forms.ICurrencyManagerProvider>  
  
     Una clase que implementa la interfaz <xref:System.Windows.Forms.ICurrencyManagerProvider> es un componente que proporciona su propio <xref:System.Windows.Forms.CurrencyManager> para administrar los enlaces asociados a este componente determinado.  La propiedad <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> proporciona el acceso al <xref:System.Windows.Forms.CurrencyManager> personalizado.  
  
    > [!NOTE]
    >  Una clase que hereda de <xref:System.Windows.Forms.Control> administra enlaces automáticamente mediante la propiedad <xref:System.Windows.Forms.Control.BindingContext%2A>, de modo que es bastante raro que se den casos en que tenga que implementar <xref:System.Windows.Forms.ICurrencyManagerProvider>.  
  
## Vea también  
 [Enlace de datos y formularios Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Cómo: Crear un control con enlace simple en Windows Forms](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)