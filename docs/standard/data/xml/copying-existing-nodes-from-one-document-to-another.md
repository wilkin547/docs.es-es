---
title: "Copia de nodos existentes de un documento a otro | Microsoft Docs"
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
ms.assetid: 3caa78c1-3448-4b7b-b83c-228ee857635e
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Copia de nodos existentes de un documento a otro
El método **ImportNode** es el mecanismo por el que un nodo o todo el subárbol de nodos se copia de un **XmlDocument** a otro.  El nodo que devuelve la llamada es una copia del nodo del documento de origen, incluidos los valores de atributo, el nombre del nodo, el tipo de nodo y todos los atributos relacionados con el espacio de nombres como el prefijo, el nombre local y el identificador de recursos uniformes \(URI\) del espacio de nombres.  El documento de origen no cambia.  Una vez importado el nodo, todavía tiene que agregarlo al árbol utilizando uno de los métodos usados para insertar nodos.  
  
 Cuando el nodo se adjunta a su nuevo documento, éste se convierte en poseedor del nodo.  La razón es que cada nodo, cuando se crea, tiene un documento en propiedad, aunque los nodos se creen en distintos fragmentos del documento.  Se trata de un requisito del modelo de objetos \(DOM\) de documentos XML que exige el diseño de creación Factory en la clase **XmlDocument**.  Por ejemplo, **CreateElement**, es la única manera de crear nodos nuevos.  
  
 En función del tipo del nodo importado y del valor del parámetro *deep*, se copiará información adicional, según sea conveniente.  Este método intenta reflejar el comportamiento esperado si un fragmento de origen XML o HTML se ha copiado de un documento a otro, teniendo en cuenta del hecho de que en XML, los dos documentos podrían tener definiciones de tipos de documento \(DTD\) distintas.  
  
 En la sigueinte tabla se describe el comportamiento específico de cada tipo de nodo que se puede importar.  
  
|Tipo de nodo|El parámetro *deep* es true|El parámetro *deep* es false|  
|------------------|---------------------------------|----------------------------------|  
|XmlAttribute|La [XmlAttribute.Specified Property](frlrfSystemXmlXmlAttributeClassSpecifiedTopic) está establecida en **true** en el XmlAttribute.  Los descendientes del **XmlAttribute** de origen se importan de forma recursiva y los nodos resultantes se reensamblan para crear el subárbol correspondiente.|El parámetro *deep* no se aplica a los nodos **XmlAttribute**, dado que siempre incluyen sus nodos secundarios cuando se importan.|  
|XmlCDataSection|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlComment|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlDocumentFragment|Los descendientes del nodo de origen se importan de forma recursiva y los nodos resultantes se reensamblan para crear el subárbol correspondiente.|Se crea un **XmlDocumentFragment** vacío.|  
|XmlDocumentType|Copia el nodo, junto con sus datos.\*|Copia el nodo, junto con sus datos.\*|  
|XmlElement|Los descendientes del elemento de origen se importan de forma recursiva y los nodos resultantes se reensamblan para crear el subárbol correspondiente. **Note:**  Los atributos predeterminados no se copian.  Si el documento que se va a importar define atributos predeterminados para este nombre de elemento, dichos atributos se asignan.|Los nodos del atributo especificado del elemento de origen se importan y los nodos **XmlAttribute** se adjuntan al nuevo elemento.  Los nodos descendientes no se copian. **Note:**  Los atributos predeterminados no se copian.  Si el documento que se va a importar define atributos predeterminados para este nombre de elemento, dichos atributos se asignan.|  
|XmlEntityReference|Como los documentos de origen y de destino podrían tener definidas las entidades de forma diferente, este método solo copia el nodo **XmlEntityReference**.  El texto de sustitución no se incluye.  Si el documento de destino tiene definida la entidad, se asigna su valor.|Como los documentos de origen y de destino podrían tener definidas las entidades de forma diferente, este método solo copia el nodo **XmlEntityReference**.  El texto de sustitución no se incluye.  Si el documento de destino tiene definida la entidad, se asigna su valor.|  
|XmlProcessingInstruction|Copia el valor de destino y de datos del nodo importado.|Copia el valor de destino y de datos del nodo importado.|  
|XmlText|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlSignificantWhitespace|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlWhitespace|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlDeclaration|Copia el valor de destino y de datos del nodo importado.|Copia el valor de destino y de datos del nodo importado.|  
|Todos los demás tipos de nodos|Estos tipos de nodos no se pueden importar.|Estos tipos de nodos no se pueden importar.|  
  
> [!NOTE]
>  Aunque es posible importar los tipos de nodos DocumentType, un documento solo puede tener un DocumentType.  De modo que, una vez importado el tipo de documento, antes de insertarlo en el árbol tiene que asegurarse de que no hay ningún tipo de documento en el documento.  Para obtener información acerca de cómo quitar nodos, consulte [Cómo quitar nodos, contenido y valores de un documento XML](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)