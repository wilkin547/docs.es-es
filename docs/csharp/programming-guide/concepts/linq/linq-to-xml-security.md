---
title: Seguridad de LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: ef2c0dc9-ecf9-4c17-b24e-144184ab725f
ms.openlocfilehash: 5b7eb815b058cba008f1db2cf683c8934c19b743
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73423369"
---
# <a name="linq-to-xml-security-c"></a>Seguridad de LINQ to XML (C#)
Este tema describe los problemas de seguridad asociados a LINQ to XML. Además, proporciona algunas indicaciones para reducir la exposición a esos problemas de seguridad.  
  
## <a name="linq-to-xml-security-overview"></a>Información general de seguridad de LINQ to XML  
 LINQ to XML se ha diseñado más para la comodidad de programación que para aplicaciones de servidor con estrictos requisitos de seguridad. La mayoría de escenarios XML consisten en el procesamiento de documentos XML de confianza en lugar del procesamiento de documentos XML que no son de confianza que se suben a un servidor. LINQ to XML está optimizado para esos escenarios.  
  
 Si debe procesar datos que no son de confianza de orígenes desconocidos, Microsoft recomienda usar una instancia de la clase <xref:System.Xml.XmlReader> que se ha configurado para filtrar ataques de denegación de servicio (DoS) XML.  
  
 Si ha configurado <xref:System.Xml.XmlReader> para mitigar los ataques de denegación de servicio, puede usar ese lector para rellenar un árbol de LINQ to XML y seguir sacando provecho de las mejoras de productividad del programador de LINQ to XML. Muchas técnicas de mitigación del riesgo implican crear lectores configurados para mitigar el problema de seguridad y crear a continuación instancias de un árbol XML mediante el lector configurado.  
  
 XML es intrínsecamente vulnerable a ataques de denegación de servicio porque los documentos no tienen límite en el tamaño, la profundidad, el tamaño de nombre de elemento, etc. Independientemente del componente que use para procesar XML, siempre debería estar preparado para reciclar el dominio de la aplicación si utiliza demasiados recursos.  
  
## <a name="mitigation-of-xml-xsd-xpath-and-xslt-attacks"></a>Reducción del riesgo de ataques de XML, XSD, XPath y XSLT  
 LINQ to XML se compila sobre <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>. LINQ to XML admite XSD y XPath mediante métodos de extensión en los espacios de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> y <xref:System.Xml.XPath?displayProperty=nameWithType>. El uso de las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XPath.XPathNavigator> y <xref:System.Xml.XmlWriter> combinado con LINQ to XML, puede invocar XSLT para transformar árboles XML.  
  
 Cuando trabaja en un entorno menos seguro, existen varios problemas de seguridad asociados con XML y con el uso de clases en <xref:System.Xml?displayProperty=nameWithType>, <xref:System.Xml.Schema?displayProperty=nameWithType>, <xref:System.Xml.XPath?displayProperty=nameWithType> y <xref:System.Xml.Xsl?displayProperty=nameWithType>. Algunos de los problemas son:  
  
- XSD, XPath y XSLT son lenguajes basados en cadenas en los que puede especificar operaciones que consumen mucho tiempo o memoria. Es responsabilidad de los programadores que toman cadenas XSD, XPath o XSLT de orígenes que no son de confianza validar que dichas cadenas no son malintencionadas o supervisar y reducir la posibilidad de que la evaluación de esas cadenas provoque un consumo excesivo de recursos del sistema.  
  
- Los esquemas XSD (incluyendo los esquemas alineadas) son intrínsecamente vulnerables a ataques de denegación de servicio. No se deben aceptar esquemas de orígenes que no sean de confianza.  
  
- XSD y XSLT pueden incluir referencias a otros archivos y esas referencias pueden producir ataques entre dominios y zonas.  
  
- Las entidades externas de DTD pueden tener como resultado ataques entre dominios y zonas.  
  
- Las DTD son vulnerables a ataques de denegación de servicio.  
  
- Los documentos XML con una profundidad excepcional pueden plantear problemas de denegación de servicio. Es posible que desee limitar la profundidad de documentos XML.  
  
- No se admiten componentes como, por ejemplo, objetos <xref:System.Xml.NameTable>, <xref:System.Xml.XmlNamespaceManager> y <xref:System.Xml.XmlResolver>, de ensamblados que no sean de confianza.  
  
- Lectura de datos en fragmentos para mitigar ataques de documentos de gran tamaño.  
  
- Los bloques de scripts de las hojas de estilos XSLT pueden dar lugar a varios ataques.  
  
- Validar cuidadosamente antes de crear expresiones XPath dinámicas.  
  
## <a name="linq-to-xml-security-issues"></a>Problemas de seguridad de LINQ to XML  
 Los problemas de seguridad de este tema no se presentan en ningún orden específico. Todos los problemas son importantes y deben solucionarse de forma adecuada.  
  
 Un ataque de elevación de privilegios que tiene éxito proporciona a un ensamblado malintencionado más control sobre su entorno. Un ataque de elevación de privilegios que tiene éxito puede tener como resultado una revelación de datos, una denegación de servicio, etc.  
  
 Las aplicaciones no deben revelar datos a los usuarios que no están autorizados a verlos.  
  
 Los ataques de denegación de servicio hacen que el analizador XML o LINQ to XML consuman excesiva memoria o tiempo de CPU. Los ataques de denegación de servicio se consideran menos graves que los ataques de elevación de privilegios o los ataques de revelación de datos. No obstante, son importantes en un escenario en el que un servidor debe procesar documentos XML de orígenes que no sean de confianza.  
  
### <a name="exceptions-and-error-messages-might-reveal-data"></a>Las excepciones y los mensajes de error pueden revelar datos  
 La descripción de un error puede revelar datos como la transformación de datos, los nombres de archivos o los detalles de implementación. Los mensajes de error no se deben mostrar a los autores de la llamada que no son de confianza. Debe detectar todos los errores e notificarlos con sus propios mensajes de error.  
  
### <a name="do-not-call-codeaccesspermissionsassert-in-an-event-handler"></a>No llamar a CodeAccessPermissions.Assert en un controlador de eventos  
 Un ensamblado puede tener más o menos permisos. Un ensamblado con más permisos cuenta con un mayor control sobre el equipo y sus entornos.  
  
 Si el código de un ensamblado con más permisos llama a <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=nameWithType> en un controlador de eventos y, a continuación, el árbol XML se pasa a un ensamblado malintencionado que tiene permisos restringidos, el ensamblado malintencionado puede hacer que se genere un evento. Como el evento ejecuta código que está en el ensamblado con más permisos, el ensamblado malintencionado funcionará con privilegios elevados.  
  
 Microsoft recomienda no llamar nunca a <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=nameWithType> en un controlador de eventos.  
  
### <a name="dtds-are-not-secure"></a>Las DTD no son seguras  
 Las entidades de DTD son inseguras intrínsecamente. Un documento XML malintencionado que contiene DTD puede hacer que el analizador use toda la memoria y todo el tiempo de CPU, lo que provocaría un ataque de denegación de servicio. Por lo tanto, en LINQ to XML, el procesamiento de DTD está desactivado de forma predeterminada. No debe aceptar DTD de orígenes que no sean de confianza.  
  
 Un ejemplo de DTD aceptadas de orígenes que no son de confianza es una aplicación web que permite a los usuarios cargar un archivo XML que hace referencia a una DTD y un archivo de DTD. Al validar el archivo, una DTD malintencionada puede ejecutar un ataque de denegación de servicio en el servidor. Otro ejemplo de DTD aceptadas de orígenes que no son de confianza es hacer referencia a una DTD en un recurso compartido de red que también permite el acceso FTP anónimo.  
  
### <a name="avoid-excessive-buffer-allocation"></a>Evitar la asignación excesiva de búfer  
 Los desarrolladores de aplicaciones deben tener en cuenta que orígenes de datos extremadamente grandes pueden provocar un agotamiento de los recursos y ataques de denegación de servicio.  
  
 Si un usuario malintencionado envía o carga un documento XML de gran tamaño, puede hacer que LINQ to XML consuma demasiados recursos del sistema. Esto puede representar un ataque de denegación de servicio. Para evitarlo, puede ajustar la propiedad <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=nameWithType> y crear un lector con un límite en el tamaño del documento que puede cargar. El lector se usa a continuación para crear el árbol XML.  
  
 Por ejemplo, si sabe que el tamaño máximo previsto de los documentos XML que provienen de un origen que no es de confianza va a ser inferior a 50 KB, establezca <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=nameWithType> en 100.000. Esto no será un inconveniente para el procesamiento de sus documentos XML y a la vez contrarrestará amenazas de denegación de servicio en las que se podrían cargar documentos que consumirían grandes cantidades de memoria.  
  
### <a name="avoid-excess-entity-expansion"></a>Evitar la expansión excesiva de entidades  
 Uno de los ataques de denegación de servicio conocidos cuando se usa una DTD es un documento que provoca una expansión excesiva de entidades. Para evitar que esto se produzca, puede establecer la propiedad <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities%2A?displayProperty=nameWithType> y crear un lector que tenga un límite en el número de caracteres producidos por la expansión de la entidad. El lector se usa a continuación para crear el árbol XML.  
  
### <a name="limit-the-depth-of-the-xml-hierarchy"></a>Limitar la profundidad de la jerarquía XML  
 Un posible ataque de denegación de servicio consiste en enviar un documento que tiene una profundidad de jerarquía excesiva. Para evitarlo, puede encapsular <xref:System.Xml.XmlReader> en su propia clase que cuenta la profundidad de los elementos. Si la profundidad supera un nivel razonable predeterminado, puede finalizar el procesamiento del documento malintencionado.  
  
### <a name="protect-against-untrusted-xmlreader-or-xmlwriter-implementations"></a>Protegerse frente a implementaciones de XmlReader o XmlWriter que no son de confianza  
 Los administradores deben comprobar que las implementaciones de <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter> proporcionadas de forma externa tienen nombres seguros y se han registrado en la configuración del equipo. Esto evita que se cargue un código malintencionado que simula ser un lector o escritor.  
  
### <a name="periodically-free-objects-that-reference-xname"></a>Liberar periódicamente objetos que hacen referencia a XName  
 Para protegerse frente a cierto tipo de ataques, los programadores de aplicaciones deben liberar todos los objetos que hacen referencia a un objeto <xref:System.Xml.Linq.XName> en el dominio de la aplicación de forma periódica.  
  
### <a name="protect-against-random-xml-names"></a>Protegerse frente a nombres XML aleatorios  
 Las aplicaciones que toman datos de orígenes que no son de confianza deben plantearse el uso de <xref:System.Xml.XmlReader>, que se incluye en el código personalizado para inspeccionar la posibilidad de nombres y espacios de nombres XML aleatorios. Si se detectan nombres y espacios de nombres XML aleatorios, la aplicación puede finalizar el procesamiento del documento malintencionado.  
  
 Es posible que desee limitar los nombres incluidos en cualquier espacio de nombres dado (incluyendo nombres que no están en ningún espacio de nombres) a una cantidad razonable.  
  
### <a name="annotations-are-accessible-by-software-components-that-share-a-linq-to-xml-tree"></a>Los componentes de software que comparten un árbol de LINQ to XML pueden tener acceso a las anotaciones  
 LINQ to XML se puede usar para compilar canalizaciones de procesamiento en las que diferentes componentes de la aplicación cargan, validan, consultan, transforman, actualizan y guardan datos XML que se pasan entre componentes como árboles XML. Esto puede ayudarle a optimizar el rendimiento, porque la sobrecarga de carga y serialización de objetos a texto XML se realiza únicamente en los extremos de la canalización. Sin embargo, los desarrolladores deben tener en cuenta que otros componentes puedes tener acceso a todas las anotaciones y controladores de eventos creados por un componente. Esto puede crear varias vulnerabilidades cuando los componentes tienen diferentes niveles de confianza. Para compilar canalizaciones seguras en componentes con un nivel de confianza inferior, debe serializar los objetos LINQ to XML a texto XML antes de pasar los datos a un componente que no es de confianza.  
  
 Common Language Runtime (CLR) proporciona cierta seguridad. Por ejemplo, un componente que no incluye una clase privada no puede tener acceso a anotaciones con claves creadas por esa clase. No obstante, las anotaciones pueden ser eliminadas por componentes que no las leen. Esto se podría usar como ataque de manipulación.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación (LINQ to XML) (C#)](linq-to-xml-overview.md)
