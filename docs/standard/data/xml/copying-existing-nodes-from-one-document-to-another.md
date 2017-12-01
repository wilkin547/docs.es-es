---
title: Copia de nodos existentes de un documento a otro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3caa78c1-3448-4b7b-b83c-228ee857635e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f20e5bd595c8eb49360e58f281a8cf6eda89acf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="copying-existing-nodes-from-one-document-to-another"></a>Copia de nodos existentes de un documento a otro
El **ImportNode** método es el mecanismo por el que un nodo o un subárbol completo de nodos se copia de una **XmlDocument** a otro. El nodo que devuelve la llamada es una copia del nodo del documento de origen, incluidos los valores de atributo, el nombre del nodo, el tipo de nodo y todos los atributos relacionados con el espacio de nombres como el prefijo, el nombre local y el identificador de recursos uniformes (URI) del espacio de nombres. El documento de origen no cambia. Una vez importado el nodo, todavía tiene que agregarlo al árbol utilizando uno de los métodos usados para insertar nodos.  
  
 Cuando el nodo se adjunta a su nuevo documento, éste se convierte en poseedor del nodo. La razón es que cada nodo, cuando se crea, tiene un documento en propiedad, aunque los nodos se creen en distintos fragmentos del documento. Esto es un requisito de Document Object Model (DOM) XML y se aplica el diseño de creación factory en la **XmlDocument** clase. Por ejemplo, **CreateElement**, es la única manera de crear nodos nuevos.  
  
 Según el tipo de nodo del nodo importado y el valor de la *profundo* parámetro, información adicional se copia según corresponda. Este método intenta reflejar el comportamiento esperado si un fragmento de origen XML o HTML se ha copiado de un documento a otro, teniendo en cuenta del hecho de que en XML, los dos documentos podrían tener definiciones de tipos de documento (DTD) distintas.  
  
 En la sigueinte tabla se describe el comportamiento específico de cada tipo de nodo que se puede importar.  
  
|Tipo de nodo|*profundidad* parámetro es true|*profundidad* parámetro es false|  
|---------------|------------------------------|-------------------------------|  
|XmlAttribute|El <xref:System.Xml.XmlAttribute.Specified%2A> está establecido en **true** en el XmlAttribute. Los descendientes del origen de **XmlAttribute** se importan de forma recursiva y los nodos resultantes se reensamblan para crear el subárbol correspondiente.|El *profundo* parámetro no se aplica a **XmlAttribute** nodos, dado que siempre incluyen sus nodos secundarios cuando se importan.|  
|XmlCDataSection|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlComment|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlDocumentFragment|Los descendientes del nodo de origen se importan de forma recursiva y los nodos resultantes se reensamblan para crear el subárbol correspondiente.|Vacío **XmlDocumentFragment** se crea.|  
|XmlDocumentType|Copia el nodo, junto con sus datos.*|Copia el nodo, junto con sus datos.*|  
|XmlElement|Los descendientes del elemento de origen se importan de forma recursiva y los nodos resultantes se reensamblan para crear el subárbol correspondiente. **Nota:** atributos predeterminados no se copian. Si el documento que se va a importar define atributos predeterminados para este nombre de elemento, dichos atributos se asignan.|Especifica el atributo se importan los nodos del elemento de origen y el generado **XmlAttribute** nodos se adjuntan al nuevo elemento. Los nodos descendientes no se copian. **Nota:** atributos predeterminados no se copian. Si el documento que se va a importar define atributos predeterminados para este nombre de elemento, dichos atributos se asignan.|  
|XmlEntityReference|Dado que los documentos de origen y de destino podrían tener las entidades definidas de forma diferente, este método solo copia el **XmlEntityReference** nodo. El texto de sustitución no se incluye. Si el documento de destino tiene definida la entidad, se asigna su valor.|Dado que los documentos de origen y de destino podrían tener las entidades definidas de forma diferente, este método solo copia el **XmlEntityReference** nodo. El texto de sustitución no se incluye. Si el documento de destino tiene definida la entidad, se asigna su valor.|  
|XmlProcessingInstruction|Copia el valor de destino y de datos del nodo importado.|Copia el valor de destino y de datos del nodo importado.|  
|XmlText|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlSignificantWhitespace|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlWhitespace|Copia el nodo, junto con sus datos.|Copia el nodo, junto con sus datos.|  
|XmlDeclaration|Copia el valor de destino y de datos del nodo importado.|Copia el valor de destino y de datos del nodo importado.|  
|Todos los demás tipos de nodos|Estos tipos de nodos no se pueden importar.|Estos tipos de nodos no se pueden importar.|  
  
> [!NOTE]
>  Aunque es posible importar los tipos de nodos DocumentType, un documento solo puede tener un DocumentType. De modo que, una vez importado el tipo de documento, antes de insertarlo en el árbol tiene que asegurarse de que no hay ningún tipo de documento en el documento. Para obtener información acerca de cómo quitar nodos, consulte [cómo quitar nodos, contenido y valores de un documento XML](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
