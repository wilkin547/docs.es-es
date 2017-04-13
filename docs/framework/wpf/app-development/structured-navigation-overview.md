---
title: "Informaci&#243;n general sobre la navegaci&#243;n estructurada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "navegación estructurada [WPF]"
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
caps.latest.revision: 43
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# Informaci&#243;n general sobre la navegaci&#243;n estructurada
El contenido que puede ser hospedado por [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], un objeto <xref:System.Windows.Controls.Frame> o un objeto <xref:System.Windows.Navigation.NavigationWindow> se compone de páginas que pueden ser identificadas por [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] paquete y a las que se puede navegar mediante hipervínculos.  La estructura de las páginas y las maneras en las que se pueden navegar, tal como las definen los hipervínculos, se conocen como la topología de navegación.  Este tipo de topología satisface diversos tipos de aplicación, particularmente aquéllas que navegan por documentos.  Para tales aplicaciones, el usuario puede navegar de una página a otra sin que ninguna de ellas necesite saber nada sobre la otra.  
  
 Sin embargo, otros tipos de aplicaciones tienen páginas que necesitan saber cuándo se ha navegado entre ellas.  Por ejemplo, considere una aplicación de recursos humanos que tenga una página con la lista de todos los empleados de la organización, la página "Lista de empleados".  Esta página también podría permitir a los usuarios agregar un nuevo empleado haciendo clic en un hipervínculo.  Cuando se hace clic, la página navega a una página "Agregar un empleado", para recopilar los detalles del nuevo empleado y devolverlos a la página "Lista de empleados", para crear el nuevo empleado y actualizar la lista.  Este estilo de navegación es similar a llamar a un método para realizar algún procesamiento y devolver un valor, lo que se considera programación estructurada.  Como tal, este estilo de navegación se conoce como *navegación estructurada*.  
  
 La clase <xref:System.Windows.Controls.Page> no implementa compatibilidad con la navegación estructurada.  En su lugar, la clase <xref:System.Windows.Navigation.PageFunction%601> deriva de <xref:System.Windows.Controls.Page> y la amplía extiende con las estructuras básicas requeridas para la navegación estructurada.  En este tema se muestra cómo establecer navegación estructurada mediante <xref:System.Windows.Navigation.PageFunction%601>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Structured_Navigation"></a>   
## Navegación estructurada  
 Cuando una página llama a otra página en una navegación estructurada, se requieren algunos o todos los comportamientos siguientes:  
  
-   La página que llama navega a la página llamada, con la opción de pasar parámetros requeridos por la página llamada.  
  
-   La página llamada, cuando un usuario ha terminado de usar la página que llama, puede devolver específicamente a la página de llamada lo siguiente:  
  
    -   Devolución de información de estado, que describe cómo se completó la página que llama \(por ejemplo, si un usuario presionó un botón Aceptar o un botón Cancelar\).  
  
    -   Devolución de los datos recopilados del usuario \(por ejemplo, los detalles del nuevo empleado\).  
  
-   Cuando la página que llama vuelve a la página llamada, la página llamada se quita del historial de navegación, para aislar cada instancia de la página llamada.  
  
 En la figura siguiente se muestran estos comportamientos.  
  
 ![Flujo entre página que llama y página a la que se llama](../../../../docs/framework/wpf/app-development/media/structurednavigationoverviewfigure1.png "StructuredNavigationOverviewFigure1")  
  
 Puede implementar estos comportamientos utilizando un objeto <xref:System.Windows.Navigation.PageFunction%601> como página llamada.  
  
<a name="Structured_Navigation_with_PageFunction"></a>   
## Navegación estructurada con PageFunction  
 En este tema se muestra cómo implementar los mecanismos básicos de navegación estructurada que implica un objeto <xref:System.Windows.Navigation.PageFunction%601>único.  En este ejemplo, un objeto <xref:System.Windows.Controls.Page> llama a un objeto <xref:System.Windows.Navigation.PageFunction%601> para recibir un valor <xref:System.String> del usuario y devolverlo.  
  
### Crear una página que llama  
 La página que llama a <xref:System.Windows.Navigation.PageFunction%601> puede ser un objeto <xref:System.Windows.Controls.Page> o un objeto <xref:System.Windows.Navigation.PageFunction%601>.  En este ejemplo, es un objeto <xref:System.Windows.Controls.Page>, como se muestra en el código siguiente.  
  
 [!code-xml[StructuredNavigationSample#CallingPageDefaultMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]  
[!code-xml[StructuredNavigationSample#CallingPageDefaultMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]  
  
 [!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
 [!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]  
  
### Crear una función de la página para la llamada  
 Dado que la página que llama puede utilizar la página llamada para recopilar y devolver datos del usuario, <xref:System.Windows.Navigation.PageFunction%601> se implementa como una clase genérica cuyo argumento de tipo especifica el tipo del valor que devolverá la página llamada.  En el código siguiente se muestra la implementación inicial de la página llamada, utilizando un objeto <xref:System.Windows.Navigation.PageFunction%601>, que devuelve un objeto <xref:System.String>.  
  
 [!code-xml[StructuredNavigationSample#CalledPageFunctionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]  
  
 [!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
 [!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]  
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]  
  
 La declaración de un objeto <xref:System.Windows.Navigation.PageFunction%601> es similar a la declaración de un objeto <xref:System.Windows.Controls.Page> con la adición de los argumentos de tipo.  Como puede ver en código de ejemplo, los argumentos de tipo se especifican tanto en el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilizando el atributo `x:TypeArguments`, como en el código subyacente, utilizando la sintaxis de argumento de tipo genérico estándar.  
  
 No tiene que utilizar solamente clases [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] como argumentos de tipo.  Se podría llamar a un objeto <xref:System.Windows.Navigation.PageFunction%601> para recopilar datos específicos de dominio que se resuman como un tipo personalizado.  El código siguiente muestra cómo utilizar un tipo personalizado como argumento de tipo para un objeto <xref:System.Windows.Navigation.PageFunction%601>.  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]  
  
 [!code-xml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]  
[!code-xml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]  
  
  
 Los argumentos de tipo para el objeto <xref:System.Windows.Navigation.PageFunction%601> proporcionan la base para la comunicación entre una página que llama y la página llamada, que se explican en las secciones siguientes.  
  
 Como verá, el tipo que se identifica con la declaración de un objeto <xref:System.Windows.Navigation.PageFunction%601> desempeña un rol importante en la devolución de datos de un objeto <xref:System.Windows.Navigation.PageFunction%601> a la página que llama.  
  
### Llamar a PageFunction y pasar parámetros  
 Para llamar a una página, la página que llama debe crear instancias de la página llamada y navegar a ellas utilizando el método <xref:System.Windows.Navigation.NavigationService.Navigate%2A>.  Esto permite que la página que llama pase datos iniciales a la página llamada, tales como valores predeterminados para los datos recopilados por la página llamada.  
  
 El código siguiente muestra la página a la que se llama con un constructor no predeterminado para aceptar parámetros de la página que llama.  
  
 [!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
 [!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]  
  
 En el código siguiente e muestra la página que llama administrando el evento <xref:System.Windows.Documents.Hyperlink.Click> del objeto <xref:System.Windows.Documents.Hyperlink> para crear instancias de la página llamada y pasarle un valor de cadena inicial.  
  
 [!code-xml[StructuredNavigationSample#PassingDataMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]  
  
 No es obligatorio pasar parámetros a la página llamada.  En su lugar, podría hacer lo siguiente:  
  
-   En la página que llama:  
  
    1.  Cree una instancia de la clase <xref:System.Windows.Navigation.PageFunction%601> llamada utilizando el constructor predeterminado.  
  
    2.  Almacene los parámetros en <xref:System.Windows.Application.Properties%2A>.  
  
    3.  Navegue al objeto <xref:System.Windows.Navigation.PageFunction%601> llamado.  
  
-   En el objeto <xref:System.Windows.Navigation.PageFunction%601> llamado:  
  
    -   Recupere y utilice los parámetros almacenados en <xref:System.Windows.Application.Properties%2A>.  
  
 Sin embargo, como verá pronto, todavía necesitará utilizar código para crear instancias y navegar a la página llamada para recopilar los datos devueltos por la página llamada.  Por esta razón, <xref:System.Windows.Navigation.PageFunction%601> necesita mantenerse vivo; de lo contrario, la próxima vez que navegue al objeto <xref:System.Windows.Navigation.PageFunction%601>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] creará una instancia de <xref:System.Windows.Navigation.PageFunction%601> utilizando el constructor predeterminado.  
  
 Para que la página llamada puede volver, sin embargo, necesita devolver datos que puedan ser recuperados por la página que llama.  
  
### Devolver el resultado y los datos de una tarea a una página que llama  
 Cuando el usuario ha terminado de utilizar la página llamada, lo que sucede en este ejemplo al presionar los botones Aceptar o Cancelar, la página llamada debe volver.  Puesto que la página que llama utilizó la página llamada para recopilar los datos del usuario, la página que llama requiere dos tipos de información:  
  
1.  Si el usuario canceló la página llamada \(presionando el botón Aceptar o el botón Cancelar en este ejemplo\).  Esto permite decidir a la página que llama si debe procesar los datos que la página de llamada recopiló del usuario.  
  
2.  Los datos que proporcionó el usuario.  
  
 Para devolver información, <xref:System.Windows.Navigation.PageFunction%601> implementa el método <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>.  En el código siguiente se muestra cómo llamarlo.  
  
 [!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
 [!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]  
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]  
  
 En este ejemplo, si un usuario presiona el botón Cancelar, se devuelve un valor de `null` a la página de llamada.  Si en su lugar se presiona el botón Aceptar, se devuelve el valor de cadena proporcionado por el usuario.  <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> es un método `protected` `virtual` al que se llama para devolver los datos a la página que llama.  Los datos deben empaquetarse en una instancia del tipo <xref:System.Windows.Navigation.ReturnEventArgs%601> genérico, cuyo argumento de tipo especifica el tipo de valor que devuelve <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A>.  De esta manera, al declarar <xref:System.Windows.Navigation.PageFunction%601> con un argumento de tipo determinado, se está indicando que <xref:System.Windows.Navigation.PageFunction%601> devolverá una instancia del tipo que especificado por el argumento de tipo.  En este ejemplo, el argumento de tipo y, por consiguiente, el valor devuelto son del tipo <xref:System.String>.  
  
 Cuando se llama a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, la página que llama necesita alguna manera de recibir el valor devuelto de l objeto <xref:System.Windows.Navigation.PageFunction%601>.  Por esta razón, <xref:System.Windows.Navigation.PageFunction%601> implementa el evento <xref:System.Windows.Navigation.PageFunction%601.Return> para llamar páginas para administrar.  Cuando se llama a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, de produce <xref:System.Windows.Navigation.PageFunction%601.Return>, de modo que la página que llama se puede registrar en <xref:System.Windows.Navigation.PageFunction%601.Return> para recibir la notificación.  
  
 [!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
 [!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]  
  
### Quitar páginas de tarea cuando se completa una tarea  
 Cuando vuelve una página llamada y el usuario no la canceló, la página de llamada procesa los datos proporcionados por el usuario y también los devueltos desde la página llamada.  La adquisición de datos de esta manera suele ser una actividad aislada; cuando vuelve la página llamada, la página que llama debe crear y navegar a una nueva página que llama para capturar más datos.  
  
 Sin embargo, a menos que la página llamada se quite del [diario](GTMT), el usuario podrá volver a una instancia anterior de la página que llama.  Si un objeto <xref:System.Windows.Navigation.PageFunction%601> se retiene en [el diario](GTMT) está determinado por la propiedad <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A>.  De forma predeterminada, una función de página se quita automáticamente cuando se llama a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, porque <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> se establece en `true`.  Para mantener una función de página en el historial de navegación después de llamar a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, establezca <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> en `false`.  
  
<a name="Other_Types_of_Structured_Navigation"></a>   
## Otros tipos de navegación estructurada  
 En este tema se muestra el uso más básico de un objeto <xref:System.Windows.Navigation.PageFunction%601> para permitir la navegación estructurada de llamada\/retorno.  Esta base proporciona la capacidad de crear más tipos complejos de navegación estructurada.  
  
 Por ejemplo, hay ocasiones en las que una página que llama necesita varias páginas para recopilar suficientes datos de un usuario o para realizar una tarea.  El uso de varias páginas se conoce como un "asistente".  
  
 En otros casos, las aplicaciones pueden tener topologías de navegación complejas que dependen de la navegación estructurada para funcionar eficazmente.  Para obtener más información, consulte [Información general sobre topologías de navegación](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md).  
  
## Vea también  
 <xref:System.Windows.Navigation.PageFunction%601>   
 <xref:System.Windows.Navigation.NavigationService>   
 [Información general sobre topologías de navegación](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)