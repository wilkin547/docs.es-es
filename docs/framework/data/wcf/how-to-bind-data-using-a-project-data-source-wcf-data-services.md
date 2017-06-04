---
title: "C&#243;mo: Enlazar datos mediante un origen de datos del proyecto (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlace de datos, Servicios de datos de Microsoft WCF"
  - "Servicios de datos de Microsoft WCF, enlace de datos"
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Enlazar datos mediante un origen de datos del proyecto (WCF Data Services)
Puede crear orígenes de datos basados en los objetos de datos generados en una aplicación cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  Al agregar una referencia a un servicio de datos usando el cuadro de diálogo **Agregar referencia de servicio**, se crea un origen de datos del proyecto junto con las clases de datos cliente generadas. Se crea un origen de datos para cada conjunto de entidades que el servicio de datos expone.  Puede crear formularios que muestran datos procedentes del servicio arrastrando estos elementos del origen de datos desde la ventana **Orígenes de datos** al diseñador.  Estos elementos se convierten en controles enlazados al origen de datos.  Durante la ejecución, este origen de datos se enlaza a una instancia de la clase <xref:System.Data.Services.Client.DataServiceCollection%601>, que se rellena con los objetos devueltos por una consulta al servicio de datos.  Para obtener más información, consulta [Enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 En los ejemplos de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos del cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### Para usar un origen de datos del proyecto en una ventana de WPF  
  
1.  En un proyecto WPF, agregue una referencia al servicio de datos de Northwind.  Para obtener más información, consulta [Cómo: Agregar una referencia a un servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
2.  En la ventana **Orígenes de datos**, expanda el nodo `Customers` del origen de datos del proyecto **NorthwindEntities**.  
  
3.  Haga clic en el elemento **CustomerID**, seleccione **ComboBox** en la lista y arrastre el elemento **CustomerID** desde el nodo **Customers** al diseñador.  
  
     Con ello se crean los siguientes elementos de objeto en el archivo XAML de la ventana:  
  
    -   Un elemento <xref:System.Windows.Data.CollectionViewSource> denominado `customersViewSource`.  La propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> del elemento de objeto <xref:System.Windows.Controls.Grid> de nivel superior se establece en este nuevo elemento <xref:System.Windows.Data.CollectionViewSource>.  
  
    -   Un control <xref:System.Windows.Controls.ComboBox> enlazado a datos denominado `CustomerID`.  
  
    -   Un objeto <xref:System.Windows.Controls.Label>.  
  
4.  Arrastre la propiedad de navegación **Orders** al diseñador.  
  
     Con ello se crean los siguientes elementos de objeto adicionales en el archivo XAML de la ventana:  
  
    -   Un segundo elemento <xref:System.Windows.Data.CollectionViewSource> denominado `customersOrdersViewSource`, cuyo origen es `customerViewSource`.  
  
    -   Un control <xref:System.Windows.Controls.DataGrid> enlazado a datos denominado `ordersDataGrid`.  
  
5.  \(Opcional\) Arrastre elementos adicionales desde el nodo **Customers** al diseñador.  
  
6.  Abra la página de códigos del formulario y agregue las instrucciones `using` siguientes \(`Imports` en Visual Basic\):  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]  
  
7.  En la clase parcial que define el formulario, agregue el código siguiente que crea una instancia de <xref:System.Data.Objects.ObjectContext> y define la constante `customerID`.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]  
  
8.  En el diseñador, seleccione la ventana.  
  
    > [!NOTE]
    >  Asegúrese de que selecciona la ventana, y no el contenido situado dentro de ella.  Cuando está seleccionada la ventana, el cuadro de texto **Nombre** situado cerca de la parte superior de la ventana **Propiedades** debería contener el nombre de la ventana.  
  
9. En la ventana **Propiedades**, seleccione el botón **Eventos**.  
  
10. Busque el evento **Loaded** y, a continuación, haga doble clic en la lista desplegable situada junto a este evento.  
  
     Visual Studio abre el archivo de código subyacente para la ventana y genera un controlador de eventos <xref:System.Windows.FrameworkElement.Loaded>.  
  
11. En el controlador de eventos <xref:System.Windows.FrameworkElement.Loaded> que se acaba de crear, copie y pegue el código siguiente.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]  
  
12. Este código crea una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> para el tipo `Customers` basándose en la ejecución de una consulta LINQ que devuelve una interfaz <xref:System.Collections.Generic.IEnumerable%601> de `Customers` junto con los objetos `Orders` relacionados desde el servicio de datos de Northwind y la enlaza con el elemento `customersViewSource`.  
  
### Para usar un origen de datos del proyecto en un formulario de Windows  
  
1.  En la ventana **Orígenes de datos**, expanda el nodo **Customers** del origen de datos del proyecto **NorthwindEntities**.  
  
2.  Haga clic en el elemento **CustomerID**, seleccione **ComboBox** en la lista y arrastre el elemento **CustomerID** desde el nodo **Customers** al diseñador.  
  
     De esta forma se crean los controles siguientes en el formulario:  
  
    -   Una instancia de <xref:System.Windows.Forms.BindingSource> denominada `customersBindingSource`.  
  
    -   Una instancia de <xref:System.Windows.Forms.BindingNavigator> denominada `customersBindingNavigator`.  Puede eliminar este control, dado que no será necesario.  
  
    -   Un control <xref:System.Windows.Forms.ComboBox> enlazado a datos denominado `CustomerID`.  
  
    -   Un objeto <xref:System.Windows.Forms.Label>.  
  
3.  Arrastre la propiedad de navegación **Orders** al formulario.  
  
4.  De esta forma se crea el control `ordersBindingSource` con la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A> del control establecida en `customersBindingSource` y la propiedad <xref:System.Windows.Forms.BindingSource.DataMember%2A> establecida en `Customers`.  También se crea el control enlazado a datos `ordersDataGridView` en el formulario, acompañado de un control de etiqueta con el título apropiado.  
  
5.  \(Opcional\) Arrastre elementos adicionales desde el nodo **Customers** al diseñador.  
  
6.  Abra la página de códigos del formulario y agregue las instrucciones `using` siguientes \(`Imports` en Visual Basic\):  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersusing)]  
  
7.  En la clase parcial que define el formulario, agregue el código siguiente que crea una instancia de <xref:System.Data.Objects.ObjectContext> y define la constante `customerID`.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdefinition)]  
  
8.  En el diseñador de formularios, haga doble clic en el formulario.  
  
     De esta forma se abre la página de código del formulario y se crea el método que administra el evento `Load` para el formulario.  
  
9. En el controlador de eventos `Load`, copie y pegue el siguiente código.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdatabinding)]  
  
10. Este código crea una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> para el tipo `Customers` basándose en la ejecución de una instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> que devuelve una interfaz <xref:System.Collections.Generic.IEnumerable%601> de `Customers` desde el servicio de datos de Northwind y la enlaza con el elemento `customersBindingSource`.  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Cómo: Enlazar datos a elementos de Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)