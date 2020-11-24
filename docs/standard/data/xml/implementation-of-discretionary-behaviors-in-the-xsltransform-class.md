---
title: Implementación de comportamientos discrecionales en la clase XslTransform
ms.date: 03/30/2017
ms.assetid: d2758ea1-03f6-47bd-88d2-0fb7ccdb2fab
ms.openlocfilehash: 7617970ead6c2d75b7ca9749578ba66efec311bc
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829419"
---
# <a name="implementation-of-discretionary-behaviors-in-the-xsltransform-class"></a>Implementación de comportamientos discrecionales en la clase XslTransform

> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.

Los comportamientos discrecionales se describen en la [recomendación de transformaciones XSL (XSLT) versión 1.0 del World Wide Web Consortium (W3C)](https://www.w3.org/TR/1999/REC-xslt-19991116), en la que el proveedor de implementaciones elige una de las distintas opciones que existen para controlar una situación. Por ejemplo, en la sección 7.3 Crear instrucciones de procesamiento, la recomendación del W3C dice que es un error el hecho de que al crear instancias del contexto de `xsl:processing-instruction` se creen nodos que no sean de texto. En el caso de algunos problemas, W3C indica qué decisión tomar si el procesador decide recuperarse del error. En el caso del problema en particular de la sección 7.3, W3C indica que la implementación puede recuperarse del error pasando por alto los nodos y su contenido.

Por lo tanto, para cada uno de los comportamientos discrecionales permitidos por W3C, la tabla siguiente enumera los comportamientos discrecionales implementados para la implementación de .NET Framework de la clase <xref:System.Xml.Xsl.XslTransform>, y en qué sección de la recomendación W3C XSLT 1.0 se trata este problema.

|Problema|Comportamiento|Sección|
|-------------|--------------|-------------|
|Un nodo de texto coincide con `xsl:strip-space` y con `xsl:preserve-space`.|Recuperar|3.4|
|Un nodo de origen coincide con más de una regla de plantilla.|Recuperar|5.5|
|Un identificador URI de espacio de nombres se declara como alias de varios URI de espacio de nombres, teniendo todos la misma prioridad de importación.|Recuperar|7.1.1|
|El atributo de nombre de `xsl:attribute` y `xsl:element` generado a partir de una plantilla de valores de atributos no es un QName calificado válido.|Se inicia una excepción|7.1.2 y 7.1.3|
|Se agrega un atributo a un elemento después de haber agregado nodos secundarios al nodo de elemento.|Recuperar|7.1.3|
|Se agrega un atributo a cualquier elemento en lugar de a un nodo de elemento.|Recuperar|7.1.3|
|Se crea una instancia del contenido del elemento `xsl:attribute` que no es un nodo de texto.|Recuperar|7.1.3|
|Dos conjuntos de atributos tienen la misma prioridad de importación y nombre expandido. Ambos tienen los mismos atributos y no hay otro conjunto de atributos que contenga el atributo común con el mismo nombre con mayor importancia.|Recuperar|7.1.4|
|El atributo de nombre `xsl:processing-instruction` no genera un nombre sin dos puntos (NCName) y un destino de instrucción de procesamiento.|Recuperar|7.3|
|Las instancias del contenido de `xsl:processing-instruction` crean nodos que no son de texto.|Recuperar|7.3|
|El resultado de la creación de instancias del contenido de `xsl:processing-instruction` contiene la cadena "`?>`".|Recuperar|7.3|
|El resultado de la creación de instancias del contenido de `xsl:comment` contiene la cadena "--" o finaliza con "-".|Recuperar|7.4|
|El resultado de la creación de instancias del contenido de `xsl:comment` crea nodos que no son de texto.|Recuperar|7.4|
|La plantilla de un elemento de enlace de variables devuelve un nodo de atributo o un nodo de espacio de nombres.|Recuperar|11.2|
|Se produce un error al recuperar el recurso del identificador URI pasado a la función de documento.|Se inicia una excepción|12.1|
|La referencia de identificador URI de la función de documento contiene un identificador de fragmento y se produce un error al procesarlo.|Se inicia una excepción|12.1|
|Hay varios atributos con el mismo nombre que no se denominan `cdata-section-elements` en `xls:output` y tienen la misma prioridad de importación.|Recuperar|16|
|El procesador no admite el valor de codificación de caracteres proporcionado en el atributo `encoding` del elemento `xsl:output`.|Recuperar|16.1|
|`disable-output-escaping` se utiliza para un nodo de texto y este nodo se utiliza para crear un elemento que no es un nodo de texto en el árbol de resultados.|Pasar por alto el atributo `disable-output-escaping`|16.4|
|Se convierte un fragmento del árbol de resultados en un número o una cadena si el fragmento contiene un nodo de texto con el establecimiento de secuencias de escape de la salida habilitado.|Se ignora.|16.4|
|El establecimiento de secuencias de escape de la salida está deshabilitado para los caracteres que no se pueden representar en la codificación que el procesador XSLT utiliza para la salida.|Se ignora.|16.4|
|Se agrega un nodo de espacio de nombres a un elemento después de haber agregado elementos secundarios o atributos al mismo.|Recuperar|Errata e25|
|`xsl:number` es NaN, infinito o menor que 0,5.|Recuperar|Errata e24|
|El segundo conjunto de nodos de argumentos de la función de documento está vacío y la referencia de identificador URI es relativa|Recuperar|Errata e14|

Las secciones de las erratas pueden encontrarse en [XSL Transformations (XSLT) Version 1.0 Specification Errata](https://www.w3.org/1999/11/REC-xslt-19991116-errata/) (Erratas de la especificación Transformación XSL (XSLT) versión 1.0) del W3C.

## <a name="custom-defined-implementation-behaviors"></a>Comportamientos de implementación definidos por el usuario

Algunos comportamientos son únicos de la implementación de la clase <xref:System.Xml.Xsl.XslTransform>XslTransform. Esta sección analiza la implementación específica del proveedor de `xsl:sort` y las características opcionales que la clase <xref:System.Xml.Xsl.XslTransform> admite.

## <a name="xslsort"></a>xsl:sort

Al utilizar una transformación para ordenar, en la recomendación de XSLT versión 1.0 de W3C se realizan algunas observaciones, Son estos:

- Aunque dos procesadores XSLT pueden ser compatibles, pueden ordenar de forma diferente.

- No todos los procesadores XSLT admiten los mismos lenguajes.

- Con respecto a los lenguajes, diferentes procesadores pueden variar su forma de ordenar en un lenguaje determinado que no está especificado en `xsl:sort.`

En la siguiente tabla se muestra el comportamiento de ordenación implementado por cada tipo de datos en la implementación de .NET Framework de una transformación realizada usando <xref:System.Xml.Xsl.XslTransform>:

|Tipo de datos|Comportamiento de ordenación|
|---------------|----------------------|
|Text|Los datos se ordenan con el método String.Compare de Common Language Runtime (CLR) y la referencia cultural local. Cuando el tipo de datos es "text", la ordenación en la clase <xref:System.Xml.Xsl.XslTransform> se comporta de forma idéntica a la comparación de cadenas de CLR.|
|número|Los valores numéricos se tratan como números XPath y se ordenan según los detalles descritos en la [sección 3.5 de la recomendación de XML Path Language (XPath) Version 1.0](https://www.w3.org/TR/1999/REC-xpath-19991116/#numbers) del W3C.|

## <a name="optional-features-supported"></a>Características opcionales admitidas

En la tabla siguiente se muestran las características opcionales para implementar un procesador XSLT que se implementan en la clase <xref:System.Xml.Xsl.XslTransform>.

|Característica|Ubicación de referencia|Notas|
|-------------|------------------------|-----------|
|Atributo `disable-output-escaping` en las etiquetas `<xsl:text...>` y `<xsl:value-of...>`.|Recomendación W3C XSLT 1.0,<br /><br /> Sección 16.4|El atributo `disable-output-escaping` se omite si se usan los elementos `xsl:text` o `xsl:value-of` en un elemento `xsl:comment`, `xsl:processing-instruction` o `xsl:attribute`.<br /><br /> No se permite que los fragmentos del árbol de resultados contengan texto y se hayan establecido secuencias de escape para la salida de texto.<br /><br /> El atributo disable-output-escaping se pasa por alto al realizar una transformación a un objeto <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter>.|

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Xsl.XslTransform>
- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
- [Transformaciones XSLT con la clase XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [XPathNavigator en transformaciones](xpathnavigator-in-transformations.md)
- [XPathNodeIterator en transformaciones](xpathnodeiterator-in-transformations.md)
- [Entrada XPathDocument en XslTransform](xpathdocument-input-to-xsltransform.md)
- [Entrada de XmlDataDocument en XslTransform](xmldatadocument-input-to-xsltransform.md)
- [Entrada de XmlDocument en XslTransform](xmldocument-input-to-xsltransform.md)
