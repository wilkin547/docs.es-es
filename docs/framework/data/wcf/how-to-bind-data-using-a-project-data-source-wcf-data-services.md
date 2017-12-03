---
title: "Cómo: Enlazar datos mediante un origen de datos del proyecto (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ee72f1c3eaf2c78a7cdff9b2a4db81ef0b767a2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-bind-data-using-a-project-data-source-wcf-data-services"></a>Cómo: Enlazar datos mediante un origen de datos del proyecto (WCF Data Services)
Puede crear orígenes de datos basados en los objetos de datos generados en una aplicación cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Al agregar una referencia a un servicio de datos mediante el uso de la **Agregar referencia de servicio** cuadro de diálogo, se crea un origen de datos del proyecto junto con las clases de datos de cliente generado. Para cada conjunto de entidades expuesto por el servicio de datos se crea un origen de datos. Puede crear formularios que muestren los datos del servicio arrastrando estos elementos de origen de datos de la **orígenes de datos** ventana hasta el diseñador. Estos elementos se convierten en controles enlazados al origen de datos. Durante la ejecución, este origen de datos se enlaza a una instancia de la <xref:System.Data.Services.Client.DataServiceCollection%601> (clase), que se rellena con los objetos devueltos por una consulta al servicio de datos. Para obtener más información, consulte [enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 En los ejemplos de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos del cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-use-a-project-data-source-in-a-wpf-window"></a>Para usar un origen de datos del proyecto en una ventana de WPF  
  
1.  En un proyecto WPF, agregue una referencia al servicio de datos de Northwind. Para obtener más información, consulte [Cómo: agregar una referencia de servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
2.  En el **orígenes de datos** ventana, expanda la `Customers` nodo en el **NorthwindEntities** origen de datos del proyecto.  
  
3.  Haga clic en el **CustomerID** elemento, seleccione **ComboBox** en la lista y arrastre la **CustomerID** de elementos de la **clientes** nodo a la diseñador.  
  
     Con ello se crean los siguientes elementos de objeto en el archivo XAML de la ventana:  
  
    -   Un elemento <xref:System.Windows.Data.CollectionViewSource> denominado `customersViewSource`. La propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> del elemento de objeto <xref:System.Windows.Controls.Grid> de nivel superior se establece en este nuevo elemento <xref:System.Windows.Data.CollectionViewSource>.  
  
    -   Un control <xref:System.Windows.Controls.ComboBox> enlazado a datos denominado `CustomerID`.  
  
    -   Objeto <xref:System.Windows.Controls.Label>.  
  
4.  Arrastre el **pedidos** propiedad de navegación para el diseñador.  
  
     Con ello se crean los siguientes elementos de objeto adicionales en el archivo XAML de la ventana:  
  
    -   Un segundo elemento <xref:System.Windows.Data.CollectionViewSource> denominado `customersOrdersViewSource`, cuyo origen es `customerViewSource`.  
  
    -   Un control <xref:System.Windows.Controls.DataGrid> enlazado a datos denominado `ordersDataGrid`.  
  
5.  (Opcional) Arrastre elementos adicionales desde la **clientes** nodo hasta el diseñador.  
  
6.  Abra la página de códigos del formulario y agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]  
  
7.  En la clase parcial que define el formulario, agregue el código siguiente que crea una instancia de <xref:System.Data.Objects.ObjectContext> y define la constante `customerID`.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]  
  
8.  En el diseñador, seleccione la ventana.  
  
    > [!NOTE]
    >  Asegúrese de que selecciona la ventana, y no el contenido situado dentro de ella. Si la ventana está activada, el **nombre** cuadro de texto situado cerca de la parte superior de la **propiedades** ventana debe contener el nombre de la ventana.  
  
9. En el **propiedades** ventana, seleccione la **eventos** botón.  
  
10. Buscar el **Loaded** eventos y, a continuación, haga doble clic en la lista desplegable lista situada junto a este evento.  
  
     Visual Studio abre el archivo de código subyacente para la ventana y genera un controlador de eventos <xref:System.Windows.FrameworkElement.Loaded>.  
  
11. En el controlador de eventos <xref:System.Windows.FrameworkElement.Loaded> que se acaba de crear, copie y pegue el código siguiente.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]  
  
12. Este código crea una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> para el tipo `Customers` basándose en la ejecución de una consulta LINQ que devuelve una interfaz <xref:System.Collections.Generic.IEnumerable%601> de `Customers` junto con los objetos `Orders` relacionados desde el servicio de datos de Northwind y la enlaza con el elemento `customersViewSource`.  
  
### <a name="to-use-a-project-data-source-in-a-windows-form"></a>Para usar un origen de datos del proyecto en un formulario de Windows  
  
1.  En el **orígenes de datos** ventana, expanda la **clientes** nodo en el **NorthwindEntities** origen de datos del proyecto.  
  
2.  Haga clic en el **CustomerID** elemento, seleccione **ComboBox** en la lista y arrastre la **CustomerID** de elementos de la **clientes** nodo a la diseñador.  
  
     De esta forma se crean los controles siguientes en el formulario:  
  
    -   Una instancia de <xref:System.Windows.Forms.BindingSource> denominada `customersBindingSource`.  
  
    -   Una instancia de <xref:System.Windows.Forms.BindingNavigator> denominada `customersBindingNavigator`. Puede eliminar este control, dado que no será necesario.  
  
    -   Un control <xref:System.Windows.Forms.ComboBox> enlazado a datos denominado `CustomerID`.  
  
    -   Objeto <xref:System.Windows.Forms.Label>.  
  
3.  Arrastre el **pedidos** propiedad de navegación al formulario.  
  
4.  De esta forma se crea el control `ordersBindingSource` con la propiedad <xref:System.Windows.Forms.BindingSource.DataSource%2A> del control establecida en `customersBindingSource` y la propiedad <xref:System.Windows.Forms.BindingSource.DataMember%2A> establecida en `Customers`. También se crea el control enlazado a datos `ordersDataGridView` en el formulario, acompañado de un control de etiqueta con el título apropiado.  
  
5.  (Opcional) Arrastre elementos adicionales desde la **clientes** nodo hasta el diseñador.  
  
6.  Abra la página de códigos del formulario y agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):  
  
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
  
## <a name="see-also"></a>Vea también  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Cómo: enlazar datos a elementos de Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)
