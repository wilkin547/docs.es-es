---
title: "C&#243;mo: Enlazar a un servicio web | Microsoft Docs"
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
  - "enlazar datos, servicio Web"
  - "enlace de datos, servicio Web"
  - "enlace a servicios web"
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Enlazar a un servicio web
En este ejemplo se muestra cómo enlazar a objetos devueltos por llamadas a métodos del servicio Web.  
  
## Ejemplo  
 En este ejemplo se utiliza [MSDN\/TechNet Publishing System \(MTPS\) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) para recuperar la lista de idiomas admitidos por un documento concreto.  
  
 Antes de llamar a un servicio Web, es preciso crear una referencia a él.  Para crear una referencia web al servicio de MTPS mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], siga estos pasos:  
  
1.  Abra el proyecto en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2.  En el menú **Proyecto**, haga clic en **Agregar referencia Web**.  
  
3.  En el cuadro de diálogo, establezca la **Dirección URL** en [http:\/\/services.msdn.microsoft.com\/contentservices\/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Haga clic en **Ir** y, a continuación, en **Agregar referencia**.  
  
 Luego, llame al método del servicio Web y establezca la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> del control o la ventana de que se trate en el objeto devuelto.  El método **GetContent** del servicio MTPS toma una referencia al objeto **getContentRequest**.  Por consiguiente, en el ejemplo siguiente se configura primero un objeto de solicitud:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Una vez establecido <xref:System.Windows.FrameworkElement.DataContext%2A>, puede crear enlaces a las propiedades del objeto en que se ha establecido <xref:System.Windows.FrameworkElement.DataContext%2A>.  En este ejemplo, <xref:System.Windows.FrameworkElement.DataContext%2A> se ha establecido en el objeto **getContentResponse** devuelto por el método **GetContent**.  En el ejemplo siguiente, <xref:System.Windows.Controls.ItemsControl> muestra los valores de **locale** de **availableVersionsAndLocales** de **getContentResponse**, y se enlaza a esta propiedad.  
  
 [!code-xml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Para obtener información sobre la estructura de **getContentResponse**, consulte [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Hacer que los datos estén disponibles para el enlace en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)