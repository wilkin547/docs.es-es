---
title: "Navegación por un conjunto de nodos con XPathNavigator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ac0135227599d6a72813bcf57b209705545da66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="node-set-navigation-using-xpathnavigator"></a>Navegación por un conjunto de nodos con XPathNavigator
Para navegar por los nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>, utilice los métodos de navegación por conjuntos de nodos de la clase <xref:System.Xml.XPath.XPathNavigator>. Puede navegar por todos los nodos o por un conjunto seleccionado de nodos que devuelve uno de los métodos de selección de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
## <a name="element-node-set-navigation"></a>Navegación por conjuntos de nodos de elementos  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye varios métodos que sirven para navegar por nodos de elementos. En la siguiente tabla se muestran los métodos de navegación disponibles y una descripción de su forma de moverse; no se incluyen los métodos que sirven para navegar por los nodos de espacios de nombres y atributos.  
  
 Para obtener más información acerca de cómo seleccionar nodos en un <xref:System.Xml.XPath.XPathNavigator> de objetos, consulte [selección, evaluación y coincidencia de datos XML con XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md). Para obtener más información sobre la navegación por nodos de atributo y espacio de nombres, vea [atributo y Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> a la misma posición del <xref:System.Xml.XPath.XPathNavigator> especificado.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> a un nodo secundario del nodo actual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al primer nodo relacionado del nodo actual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al primer nodo secundario del nodo actual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al elemento especificado en el orden del documento.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo que tiene un atributo del tipo `ID` con un valor que coincide con la <xref:System.String> especificada.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al siguiente nodo relacionado del nodo actual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo principal del nodo actual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo relacionado anterior del nodo actual.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo raíz del documento XML.|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a>Navegación por nodos de instrucción de procesamiento y comentarios  
 Los siguientes métodos de la clase <xref:System.Xml.XPath.XPathNavigator> sirven para navegar a comentarios o instrucciones de procesamiento desde otros nodos de un documento XML.  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [Atributo y navegación Namespace nodos con XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 [Extraer datos XML con XPathNavigator](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 [Acceso a fuertemente tipados datos XML con XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
