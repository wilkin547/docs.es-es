---
title: 'Cómo: Usar espacios de nombres XML en el enlace de datos'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 47ce0d951df39c7b60aa2a543baf845f5471de6c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460306"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Cómo: Usar espacios de nombres XML en el enlace de datos
## <a name="example"></a>Ejemplo
 En este ejemplo se muestra cómo controlar espacios de nombres especificados en el origen de enlace de [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].

 Si los datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] tienen la definición de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] siguiente:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 Puede usar el elemento <xref:System.Windows.Data.XmlNamespaceMapping> para asignar el espacio de nombres a un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, como en el ejemplo siguiente. Después, puede usar el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> para hacer referencia al espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. En el <xref:System.Windows.Controls.ListBox> de este ejemplo se muestra el *título* y el *DC: fecha* de cada *elemento*.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Tenga en cuenta que el <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> que especifique no tiene que coincidir con el usado en el origen de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]; Si el prefijo cambia en el origen de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] la asignación sigue funcionando.

 En este ejemplo concreto, los datos de la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] proceden de un servicio Web, pero el elemento <xref:System.Windows.Data.XmlNamespaceMapping> también funciona con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en línea o datos de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en un archivo incrustado.

## <a name="see-also"></a>Vea también

- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
