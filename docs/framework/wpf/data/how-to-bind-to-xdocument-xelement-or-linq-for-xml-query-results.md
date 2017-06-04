---
title: "C&#243;mo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement | Microsoft Docs"
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
  - "enlace de datos [WPF], enlazar a XDocument"
  - "enlace de datos [WPF], enlazar a XElement"
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# C&#243;mo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement
En este ejemplo se muestra cómo enlazar datos XML a un elemento <xref:System.Windows.Controls.ItemsControl> mediante <xref:System.Xml.Linq.XDocument>.  
  
## Ejemplo  
 El código XAML siguiente define un elemento <xref:System.Windows.Controls.ItemsControl> e incluye una plantilla de datos para los datos de tipo `Planet` en el espacio de nombres XML `http://planetsNS`.  Un tipo de datos XML que ocupa un espacio de nombres debe incluir el espacio de nombres entre llaves y, si aparece donde podría aparecer una extensión de marcado XAML, debe preceder al espacio de nombres con una secuencia de escape de llaves.  Este código enlaza a las propiedades dinámicas que corresponden a los métodos <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> de la clase <xref:System.Xml.Linq.XElement>.  Las propiedades dinámicas permiten a XAML enlazar a las propiedades dinámicas que comparten los nombres de los métodos.  Para obtener más información, vea [Propiedades dinámicas de LINQ to XML](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md).  Tenga en cuenta cómo la declaración de espacio de nombres predeterminada para XML no se aplica a los nombres de atributo.  
  
 [!code-xml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 El código de C\# siguiente llama a <xref:System.Xml.Linq.XDocument.Load%2A> y establece el contexto de datos del panel de pila en todos los subelementos del elemento denominado `SolarSystemPlanets` en el espacio de nombres XML `http://planetsNS`.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 Los datos XML pueden almacenarse como recurso XAML mediante <xref:System.Windows.Data.ObjectDataProvider>.  Para obtener un ejemplo completo, vea [Código de origen de L2DBForm.xaml](../Topic/L2DBForm.xaml%20Source%20Code.md).  En el ejemplo siguiente se muestra cómo el código puede establecer el contexto de datos en un recurso de objetos.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Las propiedades dinámicas que se asignan a <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> proporcionan flexibilidad dentro de XAML.  Su código también puede enlazar a los resultados de una consulta LINQ for XML.  Este ejemplo enlaza a los resultados de la consulta ordenados por un valor de elemento.  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## Vea también  
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [Información general sobre el enlace de datos de WPF con LINQ to XML](../Topic/WPF%20Data%20Binding%20with%20LINQ%20to%20XML%20Overview.md)   
 [Ejemplo de enlace de datos de WPF con LINQ to XML](../Topic/WPF%20Data%20Binding%20Using%20LINQ%20to%20XML%20Example.md)   
 [Propiedades dinámicas de LINQ to XML](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md)