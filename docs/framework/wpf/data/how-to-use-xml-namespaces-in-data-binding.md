---
title: "Cómo: Usar espacios de nombres XML en el enlace de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f23e041a1e6b283cfe5308d6aef861f1fc757a7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Cómo: Usar espacios de nombres XML en el enlace de datos
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo controlar espacios de nombres especificados en el origen de enlace de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tienen la definición de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] siguiente:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Puede usar el <xref:System.Windows.Data.XmlNamespaceMapping> elemento para asignar el espacio de nombres a un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente. A continuación, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia a la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] espacio de nombres. El <xref:System.Windows.Controls.ListBox> en este ejemplo se muestra la *título* y *DC: Date* de cada *elemento*.  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 Tenga en cuenta que la <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> especificar no tiene que coincidir con la utilizada en el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de origen; si cambia el prefijo en los [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] todavía funciona la asignación de origen.  
  
 En este ejemplo concreto, la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos proceden de un servicio web, pero la <xref:System.Windows.Data.XmlNamespaceMapping> elemento también funciona con en línea [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] o [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos en un archivo incrustado.  
  
## <a name="see-also"></a>Vea también  
 [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
