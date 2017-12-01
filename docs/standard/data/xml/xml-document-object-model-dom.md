---
title: Modelo de objetos de documento (DOM) XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5e52844-4820-47c0-a61d-de2da33e9f54
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ff91e929876ceec8512e962b88795b6a8a29f3d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-document-object-model-dom"></a>Modelo de objetos de documento (DOM) XML
La clase Modelo de objetos de documento XML (DOM) es una representación en la memoria de un documento XML. DOM permite leer, manipular y modificar un documento XML mediante programación. El **XmlReader** clase también lee XML; sin embargo, proporciona acceso sin almacenamiento en caché, solo hacia delante, de sólo lectura. Esto significa que no hay funciones para editar los valores de un atributo o el contenido de un elemento o la capacidad para insertar y quitar nodos con el **XmlReader**. La edición es la función principal de DOM. Es la forma común y estructurada mediante la que se representan datos XML en la memoria, aunque los datos XML reales se almacenan de forma lineal cuando se encuentran en un archivo o proceden de otro objeto. A continuación se muestran datos XML:  
  
## <a name="input"></a>Entrada  
  
```xml  
<?xml version="1.0"?>  
  <books>  
    <book>  
        <author>Carson</author>  
        <price format="dollar">31.95</price>  
        <pubdate>05/01/2001</pubdate>  
    </book>  
    <pubinfo>  
        <publisher>MSPress</publisher>  
        <state>WA</state>  
    </pubinfo>  
  </books>   
```  
  
 En la ilustración siguiente se muestra cómo se estructura la memoria cuando se leen estos datos XML en la estructura DOM.  
  
 ![Estructura del documento XML](../../../../docs/standard/data/xml/media/xml-to-domtree.gif "XML_To_DOMTree")  
Estructura de documentos XML  
  
 Dentro de la estructura del documento XML, cada círculo de esta ilustración representa un nodo, que se denomina un **XmlNode** objeto. El **XmlNode** objeto es el objeto básico en el árbol DOM. El **XmlDocument** (clase), que amplía **XmlNode**, admite métodos para realizar operaciones en el documento como un todo (por ejemplo, si se cargan en la memoria o guardar el código XML en un archivo. Además, **XmlDocument** proporciona un medio para ver y manipular los nodos de todo el documento XML. Ambos **XmlNode** y **XmlDocument** incluyen mejoras de rendimiento y facilidad de uso y disponen de métodos y propiedades para:  
  
-   Obtener acceso y modificar nodos específicos de DOM, como nodos de elemento, de referencia de entidad, etc.  
  
-   Recuperar nodos completos, además de la información que contiene el nodo, como el texto de un nodo de elemento.  
  
    > [!NOTE]
    >  Si una aplicación no requiere la estructura o funciones de edición proporcionadas por DOM, el **XmlReader** y **XmlWriter** clases proporcionan acceso de secuencia sin almacenamiento en caché, solo hacia delante a XML. Para obtener más información, consulte <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>.  
  
 **Nodo** objetos tienen un conjunto de métodos y propiedades, así como características básicas y bien definidas. Algunas de estas características son:  
  
-   Un nodo tiene un único nodo primario, que se encuentra directamente encima de él. Los únicos nodos que no tienen un nodo primario son la raíz del documento, puesto que éste es el nodo de nivel superior y contiene el propio documento y fragmentos de documento.  
  
-   La mayor parte de los nodos pueden tener varios nodos secundarios, que son los que están situados inmediatamente debajo de ellos. A continuación se muestra una lista de tipos de nodo que pueden tener nodos secundarios.  
  
    -   **Documento**  
  
    -   **DocumentFragment**  
  
    -   **EntityReference**  
  
    -   **Element**  
  
    -   **Attribute**  
  
     El **XmlDeclaration**, **notación**, **entidad**, **CDATASection**, **texto**,  **Comentario**, **ProcessingInstruction**, y **DocumentType** nodos no tienen nodos secundarios.  
  
-   Nodos que se encuentran en el mismo nivel, representados en el diagrama por la **libreta** y **pubinfo** nodos, son del mismo nivel.  
  
 La forma de controlar los atributos es una característica de DOM. Los atributos no son nodos que forman parte de las relaciones entre los nodos primarios y secundarios y entre nodos relacionados. Los atributos se consideran una propiedad del nodo de elemento y están formados por un par nombre-valor. Por ejemplo, si tiene datos XML formados por `format="dollar`" asociados con el elemento `price`, la palabra `format` es el nombre, y el valor del atributo `format` es `dollar`. Para recuperar el `format="dollar"` atributo de la **precio** nodo, se llama a la **GetAttribute** método cuando el cursor se encuentra en la `price` nodo de elemento. Para obtener más información, consulte [acceso a atributos en DOM](../../../../docs/standard/data/xml/accessing-attributes-in-the-dom.md).  
  
 Los nodos se crean al leer XML en la memoria. Sin embargo, no todos los nodos son del mismo tipo. Un elemento, en XML, tiene reglas y sintaxis diferentes a las de una instrucción de procesamiento. Por tanto, cuando se leen varios datos, se asigna a cada nodo un tipo. Este tipo determina las características y funcionalidad del nodo.  
  
 Para obtener más información sobre los tipos de nodo generados en la memoria, vea [tipos de nodos XML](../../../../docs/standard/data/xml/types-of-xml-nodes.md). Para obtener más información sobre los objetos creados en el árbol de nodos, vea [asignar la jerarquía de objetos a datos XML](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
 Microsoft ha extendido las API (Interfaz de programación de aplicaciones) que están disponibles en el nivel 1 y nivel 2 de DOM del W3C (World Wide Web Consortium) para facilitar el trabajo con documentos XML. Aunque son totalmente compatibles con las normas del W3C, las clases, métodos y propiedades adicionales añaden funcionalidades que sobrepasan lo que puede realizarse mediante el XML DOM de W3C. Las nuevas clases permiten tener acceso a datos relacionales, proporcionan métodos para sincronizar con datos de ADO.NET y exponen simultáneamente datos como XML. Para obtener más información, consulte [sincronizar DataSet con XmlDataDocument](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md).  
  
 DOM resulta más útil para leer datos XML en la memoria y cambiar su estructura, agregar o quitar nodos, o modificar los datos mantenidos en un nodo como en el texto contenido en un elemento. No obstante, hay otras clases disponibles que son más rápidas que DOM en otros escenarios. Para tener acceso de flujo rápido, sin almacenamiento en caché, solo hacia delante a XML, utilice el **XmlReader** y **XmlWriter**. Si necesita acceso aleatorio con un modelo de cursor y **XPath**, use la **XPathNavigator** clase.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de nodos XML](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
 [Asignar la jerarquía de objetos a datos XML](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)
