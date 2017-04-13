---
title: "Arquitectura del componente BindingSource | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingSource (componente) [Windows Forms], acerca del componente BindingSource"
  - "BindingSource (componente), arquitectura"
  - "enlace de datos, BindingSource (componente)"
  - "Windows Forms, enlace de datos"
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Arquitectura del componente BindingSource
Con el componente <xref:System.Windows.Forms.BindingSource>, puede enlazar universalmente todos los controles de formularios Windows Forms a orígenes de datos.  
  
 El componente <xref:System.Windows.Forms.BindingSource> simplifica el proceso de enlazar controles a un origen de datos y proporciona las siguientes ventajas sobre el enlace de datos tradicional:  
  
-   Permite enlaces a objetos comerciales en tiempo de diseño.  
  
-   Encapsula la funcionalidad <xref:System.Windows.Forms.CurrencyManager> y expone los eventos <xref:System.Windows.Forms.CurrencyManager> en tiempo de diseño.  
  
-   Simplifica la creación de una lista que admite la interfaz <xref:System.ComponentModel.IBindingList> proporcionando una notificación de cambios de lista para los orígenes de datos que no tienen compatibilidad nativa con las notificaciones de cambios de lista.  
  
-   Proporciona un punto de extensibilidad para el método <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=fullName>.  
  
-   Proporciona un nivel de direccionamiento indirecto entre el origen de datos y el control.  Este direccionamiento indirecto es importante cuando el origen de datos puede cambiar en tiempo de ejecución.  
  
-   Interopera con otros controles de formularios Windows Forms relacionados con datos, específicamente los controles <xref:System.Windows.Forms.BindingNavigator> y <xref:System.Windows.Forms.DataGridView>.  
  
 Por esto, el componente <xref:System.Windows.Forms.BindingSource> es la mejor manera de enlazar sus controles de formularios Windows Forms a los orígenes de datos.  
  
## Características de BindingSource  
 El componente <xref:System.Windows.Forms.BindingSource> proporciona varias características para enlazar controles a datos.  Con estas características, puede implementar la mayoría de los escenarios de enlace de datos con casi ninguna codificación por su parte.  
  
 El componente <xref:System.Windows.Forms.BindingSource> realiza esto proporcionando una interfaz coherente para obtener acceso a diferentes tipos de orígenes de datos.  Esto significa que utiliza el mismo procedimiento para enlazar a cualquier tipo.  Por ejemplo, puede asociar la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A> a una clase <xref:System.Data.DataSet> o a un objeto comercial, y en ambos casos se utiliza el mismo conjunto de propiedades, métodos y eventos para manipular el origen de datos.  
  
 La interfaz coherente proporcionada por el componente <xref:System.Windows.Forms.BindingSource> simplifica considerablemente el proceso de enlazar los datos a los controles.  Para tipos de origen de datos que proporcionan la notificación de cambios, el componente <xref:System.Windows.Forms.BindingSource> comunica automáticamente los cambios entre el control y el origen de datos.  Para los tipos de origen de datos que no proporcionan notificación de cambios, se facilitan eventos que le permiten provocar notificaciones de cambios.  La siguiente lista muestra las características admitidas por el componente <xref:System.Windows.Forms.BindingSource>:  
  
-   Direccionamiento indirecto  
  
-   Administración de divisa  
  
-   Origen de datos como una lista  
  
-   <xref:System.Windows.Forms.BindingSource> como una <xref:System.ComponentModel.IBindingList> &#124;  
  
-   Creación de elementos personalizados  
  
-   Creación de elementos transaccionales  
  
-   Compatibilidad con <xref:System.Collections.IEnumerable>  
  
-   Compatibilidad en tiempo de diseño  
  
-   Métodos <xref:System.Windows.Forms.ListBindingHelper> estáticos.  
  
-   Ordenar y filtrar con la interfaz <xref:System.ComponentModel.IBindingListView>  
  
-   Integración con <xref:System.Windows.Forms.BindingNavigator>  
  
### Direccionamiento indirecto  
 El componente <xref:System.Windows.Forms.BindingSource> proporciona un nivel de direccionamiento indirecto entre un control y un origen de datos.  En lugar de enlazar un control directamente a un origen de datos, enlace el control a <xref:System.Windows.Forms.BindingSource> y asocie el origen de datos a la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A> del componente <xref:System.Windows.Forms.BindingSource>.  
  
 Con este nivel de direccionamiento indirecto, puede cambiar el origen de datos sin restablecer el enlace del control.  Esto le proporciona las funciones siguientes:  
  
-   Puede asociar <xref:System.Windows.Forms.BindingSource> a los orígenes de datos diferentes conservando los enlaces del control actuales.  
  
-   Puede cambiar los elementos en el origen de datos y notificar los controles enlazados.  Para obtener más información, vea [Cómo: Reflejar las actualizaciones de los orígenes de datos en un control de Windows Forms con BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   Puede enlazar a un <xref:System.Type> en lugar de un objeto en memoria.  Para obtener más información, vea [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  A continuación puede enlazar a un objeto en tiempo de ejecución.  
  
### Administración de divisa  
 El componente <xref:System.Windows.Forms.BindingSource> implementa la interfaz <xref:System.Windows.Forms.ICurrencyManagerProvider> para controlar la administración de divisa para usted.  Con la interfaz <xref:System.Windows.Forms.ICurrencyManagerProvider> también puede tener acceso al administrador de divisa de un <xref:System.Windows.Forms.BindingSource>, así como al administrador de divisa de otro <xref:System.Windows.Forms.BindingSource> enlazado al mismo <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 El componente <xref:System.Windows.Forms.BindingSource> encapsula la funcionalidad <xref:System.Windows.Forms.CurrencyManager> y expone los eventos y las propiedades <xref:System.Windows.Forms.CurrencyManager> más comunes.  La tabla siguiente describe algunos de los miembros relacionados con la administración de divisa.  
  
 Propiedad <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Obtiene el administrador de divisa asociado a <xref:System.Windows.Forms.BindingSource>.  
  
 Método <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Si hay otro <xref:System.Windows.Forms.BindingSource> enlazado al miembro de datos especificado, obtiene su administrador de divisa.  
  
 Propiedad <xref:System.Windows.Forms.BindingSource.Current%2A>  
 Obtiene el elemento activo del origen de datos.  
  
 Propiedad <xref:System.Windows.Forms.BindingSource.Position%2A>  
 Obtiene o establece la posición actual en la lista subyacente.  
  
 Método <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Aplica los cambios pendientes al origen de datos subyacente.  
  
 Método <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Cancela la operación de edición actual.  
  
### Origen de datos como una lista  
 El componente <xref:System.Windows.Forms.BindingSource> implementa las interfaces <xref:System.ComponentModel.IBindingListView> y <xref:System.ComponentModel.ITypedList>.  Con esta implementación, puede utilizar el propio componente <xref:System.Windows.Forms.BindingSource> como un origen de datos, sin ningún almacenamiento externo.  
  
 Cuando el componente <xref:System.Windows.Forms.BindingSource> se asocia a un origen de datos, presenta el origen de datos como una lista.  
  
 La propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A> se puede establecer en varios orígenes de datos.  Éstos incluyen tipos, objetos y listas de tipos.  El origen de datos resultante se presentará como una lista.  La tabla siguiente muestra algunos de los orígenes de datos comunes y la evaluación de la lista resultante.  
  
|Propiedad DataSource|Resultados de la lista|  
|--------------------------|----------------------------|  
|Una referencia nula \(`Nothing` en Visual Basic\)|Una <xref:System.ComponentModel.IBindingList> vacío de objetos.  Al agregar un elemento, se establece la lista en el tipo del elemento agregado.|  
|Una referencia nula \(`Nothing` en Visual Basic\) con <xref:System.Windows.Forms.BindingSource.DataMember%2A> establecido|No se admite; provoca <xref:System.ArgumentException>.|  
|Tipo de no lista u objeto de tipo "T"|Un <xref:System.ComponentModel.IBindingList> vacío de tipo "T".|  
|Instancia de la matriz|<xref:System.ComponentModel.IBindingList> que contiene los elementos de la matriz.|  
|Instancia de <xref:System.Collections.IEnumerable>|<xref:System.ComponentModel.IBindingList> que contiene los elementos de<xref:System.Collections.IEnumerable>|  
|Instancia de la lista que contiene el tipo "T"|Una instancia de <xref:System.ComponentModel.IBindingList> que contiene el tipo "T".|  
  
 Además, <xref:System.Windows.Forms.BindingSource.DataSource%2A> se puede establecer en otros tipos de lista, como <xref:System.ComponentModel.IListSource> y <xref:System.ComponentModel.ITypedList>, y <xref:System.Windows.Forms.BindingSource> los controlará adecuadamente.  En este caso, el tipo contenido en la lista debería tener un constructor predeterminado.  
  
### BindingSource como una IBindingList  
 El componente <xref:System.Windows.Forms.BindingSource> proporciona los miembros para obtener acceso y manipular los datos subyacentes como una <xref:System.ComponentModel.IBindingList>.  La tabla siguiente describe algunos de estos miembros.  
  
|Miembro|Descripción|  
|-------------|-----------------|  
|Propiedad <xref:System.Windows.Forms.BindingSource.List%2A>|Obtiene la lista que es el resultado de la evaluación de las propiedades <xref:System.Windows.Forms.BindingSource.DataSource%2A> o <xref:System.Windows.Forms.BindingSource.DataMember%2A>.|  
|Método <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Agrega un nuevo elemento a la lista subyacente.  Se aplica a los orígenes de datos que implementan la interfaz <xref:System.ComponentModel.IBindingList> y permiten agregar elementos \(es decir, la propiedad <xref:System.Windows.Forms.BindingSource.AllowNew%2A> se establece en `true`\).|  
  
### Creación del elemento personalizada  
 Puede controlar el evento <xref:System.Windows.Forms.BindingSource.AddingNew> para proporcionar su propia lógica de creación de elemento.  El evento <xref:System.Windows.Forms.BindingSource.AddingNew> se produce antes de agregar un nuevo objeto a <xref:System.Windows.Forms.BindingSource>.  Este evento se produce después de llamar al método <xref:System.Windows.Forms.BindingSource.AddNew%2A>, pero antes de agregar el nuevo elemento a la lista subyacente.  Controlando este evento, puede proporcionar un comportamiento de creación de elemento personalizado sin derivar de la clase <xref:System.Windows.Forms.BindingSource>.  Para obtener más información, vea [Cómo: Personalizar la forma de agregar elementos con el control BindingSource de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### Creación de elemento transaccional  
 El componente <xref:System.Windows.Forms.BindingSource> implementa la interfaz <xref:System.ComponentModel.ICancelAddNew> que habilita la creación de elemento transaccional.  Después de crear provisionalmente un nuevo elemento mediante una llamada a <xref:System.Windows.Forms.BindingSource.AddNew%2A>, se puede confirmar que se agrega el elemento o revertir la acción de la siguiente manera:  
  
-   El método <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> confirmará explícitamente la inclusión pendiente.  
  
-   Al realizar otra operación de colección, como una inserción, eliminación o movimiento, implícitamente confirmará la inclusión pendiente.  
  
-   El método <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> revertirá la inclusión pendiente si todavía no se ha confirmado éste.  
  
### Compatibilidad con IEnumerable  
 El componente <xref:System.Windows.Forms.BindingSource> permite enlazar controles a los orígenes de datos de <xref:System.Collections.IEnumerable>.  Con este componente, se puede enlazar a un origen de datos como un <xref:System.Data.SqlClient.SqlDataReader?displayProperty=fullName>.  
  
 Cuando se asigna un origen de datos de <xref:System.Collections.IEnumerable> al componente <xref:System.Windows.Forms.BindingSource>, <xref:System.Windows.Forms.BindingSource> crea una <xref:System.ComponentModel.IBindingList> y agrega el contenido del origen de datos de <xref:System.Collections.IEnumerable> a la lista.  
  
### Compatibilidad en tiempo de diseño  
 Algunos tipos de objetos no pueden crearse en tiempo de diseño \(por ejemplo, los objetos creados a partir de un generador de clases o los devueltos por un servicio Web\).  En ocasiones tendrá que enlazar los controles a estos tipos en tiempo de diseño, incluso aunque no exista ningún objeto en memoria al que se puedan enlazar los controles.  Por ejemplo, puede necesitar etiquetar los encabezados de columna de un control <xref:System.Windows.Forms.DataGridView> con los nombres de las propiedades públicas de su tipo personalizado.  
  
 Para que exista compatibilidad con este escenario, el componente <xref:System.Windows.Forms.BindingSource> admite enlazarse a <xref:System.Type>.  Cuando asigna una clase <xref:System.Type> a la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A>, el componente <xref:System.Windows.Forms.BindingSource> crea una <xref:System.ComponentModel.BindingList%601> vacía de elementos <xref:System.Type>.  Cualquier control que enlace posteriormente al componente <xref:System.Windows.Forms.BindingSource> estará avisado de la presencia de propiedades, o esquema, de su tipo en tiempo de diseño o de ejecución.  Para obtener más información, vea [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### Métodos ListBindingHelper estáticos  
 <xref:System.Windows.Forms.BindingContext?displayProperty=fullName>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=fullName> y los tipos <xref:System.Windows.Forms.BindingSource> comparten la lógica común para generar una lista a partir de un par `DataSource`\/`DataMember`.  Además, esta lógica común se expone públicamente para que lo utilicen los creadores del control y terceros en los métodos `static` siguientes:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### Ordenar y filtrar con la interfaz IBindingListView  
 El componente <xref:System.Windows.Forms.BindingSource> implementa la interfaz <xref:System.ComponentModel.IBindingListView> que extiende la interfaz <xref:System.ComponentModel.IBindingList>.  <xref:System.ComponentModel.IBindingList> proporciona ordenación de columnas única y <xref:System.ComponentModel.IBindingListView> proporciona ordenación y filtrado avanzados.  Con <xref:System.ComponentModel.IBindingListView>, puede ordenar y filtrar los elementos del origen de datos, si éste también implementa una de estas interfaces.  El componente <xref:System.Windows.Forms.BindingSource> no proporciona una implementación de la referencia de estos miembros.  En su lugar, las llamadas se reenvían a la lista subyacente.  
  
 La tabla siguiente describe las propiedades que se utilizan para ordenar y filtrar.  
  
|Miembro|Descripción|  
|-------------|-----------------|  
|Propiedad <xref:System.Windows.Forms.BindingSource.Filter%2A>|Si el origen de datos es una <xref:System.ComponentModel.IBindingListView>, obtiene o establece la expresión utilizada para filtrar las filas que se ven.|  
|Propiedad <xref:System.Windows.Forms.BindingSource.Sort%2A>|Si el origen de datos es una <xref:System.ComponentModel.IBindingList>, obtiene o establece un nombre de columna utilizado para ordenar y la información del criterio de ordenación.<br /><br /> O bien<br /><br /> Si el origen de datos es una <xref:System.ComponentModel.IBindingListView> y admite la ordenación avanzada, obtiene varios nombres de columna utilizados para ordenar así como el criterio de ordenación.|  
  
### Integración con BindingNavigator  
 Puede utilizar el componente <xref:System.Windows.Forms.BindingSource> para enlazar cualquier control de formularios Windows Forms al origen de datos, pero el control <xref:System.Windows.Forms.BindingNavigator> se designa específicamente para trabajar con el componente <xref:System.Windows.Forms.BindingSource>.  El control <xref:System.Windows.Forms.BindingNavigator> proporciona una interfaz de usuario para controlar el elemento actual del componente <xref:System.Windows.Forms.BindingSource>.  De manera predeterminada, el control <xref:System.Windows.Forms.BindingNavigator> proporciona botones que corresponden a los métodos de navegación en el componente <xref:System.Windows.Forms.BindingSource>.  Para obtener más información, vea [Cómo: Explorar datos con el control BindingNavigator de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.BindingNavigator>   
 [Información general sobre el componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)   
 [BindingNavigator \(Control\)](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [Cómo: Reflejar las actualizaciones de los orígenes de datos en un control de Windows Forms con BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)