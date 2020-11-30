---
title: Modificación de nodos, contenido y valores en un documento XML
ms.date: 03/30/2017
ms.assetid: 761773e0-db72-4986-b9f5-a522213d8397
ms.openlocfilehash: c3f3f4a279f3bcb967e018abafbd2e1f7a0af473
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714476"
---
# <a name="modifying-nodes-content-and-values-in-an-xml-document"></a>Modificación de nodos, contenido y valores en un documento XML

Existen muchas formas de modificar los nodos y el contenido de un documento. Puede realizar lo siguiente:  
  
- Cambiar el valor de los nodos utilizando la propiedad <xref:System.Xml.XmlNode.Value%2A>.  
  
- Modificar un conjunto completo de nodos reemplazando los nodos por nodos nuevos. Para ello, utilice la propiedad <xref:System.Xml.XmlNode.InnerXml%2A>.  
  
- Reemplazar los nodos existentes por nuevos nodos utilizando el método <xref:System.Xml.XmlNode.RemoveChild%2A>.  
  
- Agregar caracteres adicionales a los nodos que heredan de la clase <xref:System.Xml.XmlCharacterData> utilizando los métodos <xref:System.Xml.XmlCharacterData.AppendData%2A>, <xref:System.Xml.XmlCharacterData.InsertData%2A> o <xref:System.Xml.XmlCharacterData.ReplaceData%2A>.  
  
- Modificar el contenido quitando un intervalo de caracteres utilizando el método <xref:System.Xml.XmlCharacterData.DeleteData%2A> en los tipos de nodos que heredan de <xref:System.Xml.XmlCharacterData>.  
  
 Una técnica muy sencilla para cambiar el valor de un nodo consiste en utilizar `node.Value = "new value";`. En la siguiente tabla se enumeran los tipos de nodos en los que funciona esta línea de código y qué datos se cambian exactamente para ese tipo de nodo.  
  
|Tipo de nodo|Datos cambiados|  
|---------------|------------------|  
|Atributo|El valor del atributo.|  
|CDATASection|El contenido de CDATASection.|  
|Comentario|El contenido del comentario.|  
|ProcessingInstruction|El contenido, sin incluir el destino.|  
|Text|El contenido del texto.|  
|XmlDeclaration|El contenido de la declaración, sin incluir el marcado `<?xml` y `?>`.|  
|Whitespace|El valor del espacio en blanco. Puede establecer este valor en uno de los cuatro caracteres de espacio en blanco XML reconocidos: space, tab, CR o LF.|  
|SignificantWhitespace|El valor del espacio en blanco significativo. Puede establecer este valor en uno de los cuatro caracteres de espacio en blanco XML reconocidos: space, tab, CR o LF.|  
  
 Cualquier tipo de nodo que no se incluya en la tabla no es un tipo de nodo válido para establecer un valor en él. Al establecer un valor en cualquier otro tipo de nodo, se inicia una <xref:System.InvalidOperationException>.  
  
 La propiedad <xref:System.Xml.XmlNode.InnerXml%2A> cambia el marcado de los nodos secundarios del nodo actual. Al establecer esta propiedad, los nodos secundarios se reemplazan por el contenido analizado de la cadena especificada. El análisis se realiza en el contexto del espacio de nombres actual. Además, <xref:System.Xml.XmlNode.InnerXml%2A> quita las declaraciones de espacios de nombres redundantes. Como resultado, las numerosas operaciones de corte y pegado no aumentan el tamaño del documento con declaraciones de espacios de nombres redundantes. Para ver un ejemplo de código que ilustra el efecto de los espacios de nombres en la operación <xref:System.Xml.XmlNode.InnerXml%2A>, vea la propiedad <xref:System.Xml.XmlDocument.InnerXml%2A>.  
  
 Al utilizar los métodos <xref:System.Xml.XmlCharacterData.ReplaceData%2A> y <xref:System.Xml.XmlNode.RemoveChild%2A>, los métodos devuelven el nodo quitado o reemplazado. Luego, este nodo se puede volver a insertar en cualquier lugar del Modelo de objetos de documento (DOM) XML. El método <xref:System.Xml.XmlCharacterData.ReplaceData%2A> realiza dos comprobaciones de validación en el nodo que se va a insertar en el documento. En la primera comprobación se garantiza que el nodo se está convirtiendo en un nodo secundario que puede tener nodos secundarios de su tipo. En la segunda comprobación se garantiza que el nodo que se va a insertar no es un antecesor del nodo del que se va a convertir en secundario. Si se incumplen cualquiera de estas condiciones, se inicia una <xref:System.InvalidOperationException>.  
  
 Es válido agregar o quitar un nodo secundario de solo lectura de un nodo que se puede editar. Sin embargo, cualquier intento de modificar ese nodo de solo lectura inicia una <xref:System.InvalidOperationException>. Pongamos como ejemplo la modificación de los nodos secundarios de un nodo <xref:System.Xml.XmlEntityReference>. Los nodos secundarios son de solo lectura y no se pueden modificar. Cualquier intento de modificarlos inicia una <xref:System.InvalidOperationException>.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
