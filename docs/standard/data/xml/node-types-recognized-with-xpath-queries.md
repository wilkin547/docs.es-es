---
title: "Tipos de nodos reconocidos con consultas XPath | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Tipos de nodos reconocidos con consultas XPath
Los tipos de nodos que se reconocen en una consulta XPath no son los mismos que se encuentran en el Modelo de objetos de documento \(DOM\).  
  
## Tipos de nodos XPath del W3C  
 Los tipos de nodos que se reconocen en una consulta XPath no son los tipos de nodos que se encuentran en el Modelo de objetos de documento \(DOM\).  A continuación se enumeran los tipos de nodos XPath representados por la enumeración <xref:System.Xml.XPath.XPathNodeType>.  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
 Estos tipos de nodos se basan en el modelo de datos XPath, donde los nodos se derivan del conjunto de información XML.  Los tipos de nodos <xref:System.Xml.XPath.XPathNodeType> y <xref:System.Xml.XPath.XPathNodeType> son extensiones de Microsoft .NET Framework para los tipos de nodos básicos que se describen en el modelo de datos XPath.  
  
 El tipo de nodo de atributos se utiliza de manera diferente en el modelo de datos XPath y en el DOM.  En el modelo de datos XPath, el nodo de elementos tiene un conjunto de nodos de atributos relacionados con él y el nodo de elementos es el nodo principal de cada nodo de atributos.  Sin embargo, en el DOM, el nodo de elementos es el propietario y no el nodo principal.  En ambos modelos, los nodos de espacios de nombres y atributos no se consideran nodos secundarios del nodo de elementos.  
  
 El tipo de nodo de espacios de nombres es una adición al modelo de datos XPath y no es un tipo de nodo DOM reconocido.  
  
 Para obtener más información sobre la navegación por nodos de espacios de nombres, atributos y elementos, vea los temas [Navegación por un conjunto de nodos con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) y [Navegación por nodos de espacios de nombres y atributos con XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
## Vea también  
 <xref:System.Xml.XmlDocument>   
 <xref:System.Xml.XPath.XPathDocument>   
 <xref:System.Xml.XPath.XPathNavigator>   
 [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [Seleccionar datos XML con XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)   
 [Evaluación de expresiones XPath con XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)   
 [Coincidencia de nodos con XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)   
 [Espacios de nombres y consultas XPath](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)   
 [Expresiones XPath compiladas](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)