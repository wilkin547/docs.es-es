---
title: Carga de datos desde un sistema de lectura
ms.date: 03/30/2017
ms.assetid: 7e74918c-bc72-4977-a49b-e1520a6d8f60
ms.openlocfilehash: 345b6e35c84fe531e131d27bd09fbd8a87b4521a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720144"
---
# <a name="load-data-from-a-reader"></a>Carga de datos desde un sistema de lectura

Si se carga un documento XML utilizando el método <xref:System.Xml.XmlDocument.Load%2A> y un parámetro de <xref:System.Xml.XmlReader>, existen diferencias en el comportamiento que se produce cuando se compara con el comportamiento derivado de la carga de datos desde otros formatos. Si el sistema de lectura está en su estado inicial, <xref:System.Xml.XmlDocument.Load%2A> consume todo el contenido del sistema de lectura y compila el Modelo de objetos de documento (DOM) XML a partir de todos los datos del sistema de lectura.  
  
 Si el sistema de lectura ya se encuentra situado en un nodo en algún lugar del documento y, a continuación, se pasa al método <xref:System.Xml.XmlDocument.Load%2A>, <xref:System.Xml.XmlDocument.Load%2A> intenta leer el nodo actual y todos sus nodos relacionados hasta la etiqueta final que cierra el nivel de profundidad actual en la memoria. El resultado correcto del intento de <xref:System.Xml.XmlDocument.Load%2A> depende del nodo en el que se encuentre el sistema de lectura cuando se intente realizar la carga, ya que <xref:System.Xml.XmlDocument.Load%2A> comprueba que el XML del sistema de lectura es correcto. Si el XML no es correcto, <xref:System.Xml.XmlDocument.Load%2A> inicia una excepción. Por ejemplo, el siguiente conjunto de nodos contiene dos elementos a nivel raíz, el XML no es correcto y <xref:System.Xml.XmlDocument.Load%2A> inicia una excepción.  
  
- Nodo Comment, seguido de un nodo Element, seguido de otro nodo Element, seguido de un nodo EndElement.  
  
 El siguiente conjunto de nodos crea un DOM incompleto porque no hay ningún elemento a nivel raíz.  
  
- Nodo Comment seguido de un nodo ProcessingInstruction, seguido de un nodo Comment, seguido de un nodo EndElement.  
  
 Esto no inicia una excepción y los datos se cargan. Puede agregar un elemento raíz por encima de estos nodos y crear XML correcto que se pueda guardar sin errores.  
  
 Si el sistema de lectura se encuentra situado en un nodo hoja que no es válido para el nivel raíz de un documento (por ejemplo, un nodo de atributos o espacios en blanco), el sistema de lectura continúa leyendo hasta estar situado en un nodo que se pueda utilizar para el nivel raíz. El documento comienza a cargarse en este punto.  
  
 De manera predeterminada, <xref:System.Xml.XmlDocument.Load%2A> no comprueba si el XML es válido utilizando la definición de tipo de documento (DTD) o la validación de esquemas. Sólo comprueba si el XML es correcto. Para que se produzca la validación, tiene que crear un <xref:System.Xml.XmlReader> utilizando la clase <xref:System.Xml.XmlReaderSettings>. La clase <xref:System.Xml.XmlReader> puede exigir la validación con una DTD o un esquema del lenguaje de definición de esquemas (XSD). La propiedad <xref:System.Xml.ValidationType> de la clase <xref:System.Xml.XmlReaderSettings> determina si la instancia de <xref:System.Xml.XmlReader> exige la validación. Para obtener más información acerca de la validación de datos XML, vea la sección Comentarios de la página de referencia de <xref:System.Xml.XmlReader>.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
