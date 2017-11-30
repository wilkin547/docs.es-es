---
title: "Cómo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b39c45a7c85155a0fb46e8e176da5979e52e6e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Cómo: Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement
En este ejemplo se muestra cómo enlazar datos XML a un <xref:System.Windows.Controls.ItemsControl> con <xref:System.Xml.Linq.XDocument>.  
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente define un <xref:System.Windows.Controls.ItemsControl> e incluye una plantilla de datos para datos de tipo `Planet` en el `http://planetsNS` espacio de nombres XML. Un tipo de datos XML que ocupa un espacio de nombres debe incluir el espacio de nombres entre llaves y, si aparece donde podría aparecer una extensión de marcado XAML, debe preceder al espacio de nombres con una secuencia de escape de llaves. Este código enlaza a las propiedades dinámicas que corresponden a la <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> métodos de la <xref:System.Xml.Linq.XElement> clase. Las propiedades dinámicas permiten a XAML enlazar a las propiedades dinámicas que comparten los nombres de los métodos. Para más información, consulte [Propiedades dinámicas de LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties). Tenga en cuenta cómo la declaración de espacio de nombres predeterminada para XML no se aplica a los nombres de atributo.  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 Las llamadas de código de C# siguientes <xref:System.Xml.Linq.XDocument.Load%2A> y establece el contexto de datos del panel de pila en todos los subelementos del elemento denominado `SolarSystemPlanets` en el `http://planetsNS` espacio de nombres XML.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 Se pueden almacenar datos XML como un recurso de XAML utilizando <xref:System.Windows.Data.ObjectDataProvider>. Para obtener un ejemplo completo, vea [Código de origen de L2DBForm.xaml](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e). En el ejemplo siguiente se muestra cómo el código puede establecer el contexto de datos en un recurso de objetos.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Las propiedades dinámicas que se asignan a <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> proporcionan flexibilidad dentro de XAML. El código también puede enlazar a los resultados de una consulta LINQ to XML. Este ejemplo enlaza a los resultados de la consulta ordenados por un valor de elemento.  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Información general de enlace de datos WPF con LINQ to XML](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [Ejemplo de enlace de datos WPF mediante LINQ to XML](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)  
 [Propiedades dinámicas de LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties)
