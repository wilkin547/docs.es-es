---
title: Errores XSLT recuperables
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 484929b0-fefb-4629-87ee-ebdde70ff1f8
ms.openlocfilehash: e3ff86cc80887d14fdffe50f256409cb70ff2d88
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710380"
---
# <a name="recoverable-xslt-errors"></a>Errores XSLT recuperables
La recomendación de la versión 1.0 de las transformaciones XLT (XSLT) del W3C incluye áreas en las que el proveedor de las implementaciones puede decidir cómo controlar una situación. Estas áreas se consideran comportamientos discrecionales. Por ejemplo, en la sección 7.3 Creación de instrucciones de procesamiento, la recomendación 1.0 de XSLT dice que el hecho de que al crear instancias del contenido de `xsl:processing-instruction` se creen nodos que no sean de texto, es un error. Para algunos problemas, la recomendación 1.0 de XSLT indica qué decisión tomar si el procesador decide recuperarse del error. En el caso del problema en particular de la sección 7.3, W3C indica que la implementación puede recuperarse del error pasando por alto los nodos y su contenido.  
  
## <a name="discretionary-behaviors"></a>Comportamientos discrecionales  
 En la siguiente tabla se enumeran cada uno de los comportamientos discrecionales que permite la recomendación 1.0 de XSLT y cómo controla estos comportamientos la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
- "Recuperar" indica que la clase <xref:System.Xml.Xsl.XslCompiledTransform> se recuperará de este error. El evento <xref:System.Xml.Xsl.XsltArgumentList.XsltMessageEncountered?displayProperty=nameWithType> se puede utilizar para notificar cualquier evento desde el procesador XSLT.  
  
- El error indica que se inicia una excepción para esta situación.  
  
- Puede encontrar las referencias de la sección en la [recomendación de transformaciones XSL (XSLT) versión 1.0 del W3C](https://www.w3.org/TR/xslt) y en las [erratas de especificaciones de las transformaciones XSL (XSLT) versión 1.0 del W3C](https://www.w3.org/1999/11/REC-xslt-19991116-errata/).  
  
|Condición XSLT|Sección|Comportamiento de XslCompiledTransform|  
|--------------------|-------------|-----------------------------------|  
|Un nodo de texto coincide con `xsl:strip-space` y con `xsl:preserve-space`.|3.4|Recuperar|  
|Un nodo de origen coincide con más de una regla de plantilla.|5.5|Recuperar|  
|Un identificador URI de espacio de nombres se declara como alias de varios identificadores URI de espacio de nombres, teniendo todos la misma prioridad de importación.|7.1.1|Recuperar|  
|El atributo `name` de `xsl:attribute` y `xsl:element` que se genera desde un valor de atributo no es un QName.|7.1.2, 7.1.3|Error*|  
|Dos conjuntos de atributos con la misma importación y nombre expandido tienen un atributo en común y no hay ningún otro conjunto de atributos que contenga el atributo común que tiene el mismo nombre con mayor importancia.|7.1.4|Recuperar|  
|Se agrega un atributo a un elemento después de que se le hayan agregado elementos secundarios.|7.1.3|Error*|  
|Se crea un atributo con el nombre 'xmlns'|7.1.3|Error*|  
|Se agrega un atributo a un nodo que no es un elemento.|7.1.3|Error*|  
|Se crean nodos que no son nodos de texto durante la creación de instancias del contenido del atributo `xsl:attribute`.|7.1.3|Error*|  
|El atributo `name` de un `xsl:processing-instruction` no produce un NCName y un destino de instrucción de procesamiento.|7.3|Error*|  
|Las instancias del contenido de `xsl:processing-instruction` crean nodos que no son de texto.|7.3|Error*|  
|El resultado de la creación de instancias del contenido de `xsl:processing-instruction` contiene la cadena "?>"|7.3|Recuperar|  
|El resultado de la creación de instancias del contenido de `xsl:processing-instruction` contiene la cadena "--" o finaliza con "-".|7.4|Recuperar|  
|El resultado de la creación de instancias del contenido de `xsl:comment` crea nodos que no son de texto.|7.4|Error*|  
|La plantilla de un elemento de enlace de variables devuelve un nodo de atributo o un nodo de espacio de nombres.|11.2|Error*|  
|Se produce un error al recuperar el recurso del identificador URI pasado a la función de documento.|12.1|Error|  
|La referencia de URI de la función de documento contiene un identificador de fragmento y se produce un error al procesarlo.|12.1|Recuperar*|  
|Hay varios atributos con el mismo nombre, aunque con valores diferentes, que no son elementos cdata-section con nombre de `xsl:output` con la misma prioridad de importación.|16|Recuperar|  
|El procesador no es compatible con la codificación del atributo de codificación `xsl:output`.|16.1|Recuperar|  
|Se deshabilita el establecimiento de secuencias de escape para un nodo de texto que se utiliza para algo que no sea un nodo de texto en el árbol de resultados.|16.4|Recuperar*|  
|Se convierte un fragmento del árbol de resultados en un número o una cadena si el fragmento contiene un nodo de texto con el establecimiento de secuencias de escape de la salida habilitado.|16.4|Recuperar*|  
|El establecimiento de secuencias de escape de la salida está deshabilitado para un carácter que no se puede representar en la codificación que el procesador XSLT utiliza para la salida.|16.4|Recuperar*|  
|Se agrega un nodo de espacio de nombres a un elemento después de haber agregado elementos secundarios o atributos al mismo.|errata 25|Error*|  
|El atributo `value` de un `xsl:number` es NAN, infinito o menor que 0,5.|errata 24|Recuperar|  
|El segundo conjunto de nodos de argumentos de la función de documento está vacío y la referencia de identificador URI es relativa.|errata 14|Recuperar|  
  
 <sup>*</sup> Este comportamiento es diferente al de la clase <xref:System.Xml.Xsl.XslTransform>. Para más información, vea [Implementación de comportamientos discrecionales en la clase XslTransform](../../../../docs/standard/data/xml/implementation-of-discretionary-behaviors-in-the-xsltransform-class.md).  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
