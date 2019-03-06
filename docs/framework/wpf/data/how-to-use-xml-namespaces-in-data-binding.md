---
title: Filtrar Usar espacios de nombres XML en el enlace de datos
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 190bf22544bd17cb215870728333211795040294
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377337"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Filtrar Usar espacios de nombres XML en el enlace de datos
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo controlar espacios de nombres especificados en el origen de enlace de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tienen la definición de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] siguiente:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Puede usar el <xref:System.Windows.Data.XmlNamespaceMapping> elemento para asignar el espacio de nombres para un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente. A continuación, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia a la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] espacio de nombres. El <xref:System.Windows.Controls.ListBox> en este ejemplo muestra el *título* y *DC: Date* de cada *elemento*.  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 Tenga en cuenta que el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> especificar no tiene que coincidir con la utilizada en el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de origen; si el prefijo cambia en el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] origen de la asignación sigue funcionando.  
  
 En este ejemplo concreto, el [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos proceden de un servicio web, pero la <xref:System.Windows.Data.XmlNamespaceMapping> elemento también funciona con inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] o [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] datos en un archivo incrustado.  
  
## <a name="see-also"></a>Vea también
- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
