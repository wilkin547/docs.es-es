---
title: Reglas para deducir los tipos de nodo de esquema y estructura
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
ms.openlocfilehash: 381c5fbd3823514de98b38840b8259a417e48fb8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289088"
---
# <a name="rules-for-inferring-schema-node-types-and-structure"></a>Reglas para deducir los tipos de nodo de esquema y estructura
Este tema describe cómo el proceso de deducción del esquema traduce los tipos de nodo de un documento XML a una estructura de lenguaje de definición de esquema XML (XSD).  
  
## <a name="element-inference-rules"></a>Reglas de deducción de elemento  
 Esta sección describe las reglas de interferencia para las declaraciones de elemento. Existen ocho estructuras de declaraciones de elementos que serán deducidas:  
  
1. Elemento de tipo simple  
  
2. Elemento vacío  
  
3. Elemento vacío con atributos  
  
4. Elemento con atributos y contenido simple  
  
5. Elemento con una secuencia de elementos secundarios  
  
6. Elemento con una secuencia de elementos secundarios y atributos  
  
7. Elemento con una secuencia de opciones de elementos secundarios  
  
8. Elemento con una secuencia de opciones de elementos secundarios y atributos  
  
> [!NOTE]
> Todas las declaraciones `complexType` se deducen como tipos anónimos. El único elemento global deducido es el elemento raíz; todos los demás elementos son locales.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
### <a name="simple-typed-element"></a>Elemento con establecimiento de tipos simple  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. El elemento en negrita muestra el esquema deducido para el elemento de tipo simple.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root" type="xs:string" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element"></a>Elemento vacío  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. El elemento en negrita muestra el esquema deducido para el elemento vacío.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element-with-attributes"></a>Elemento vacío con atributos  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. Los elementos en negrita muestra el esquema deducido para el elemento vacío con atributos.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-attributes-and-simple-content"></a>Elemento con atributos y contenido simple  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. Los elementos en negrita muestran el esquema para un elemento con atributos y contenido simple.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:simpleContent>`<br /><br /> `<xs:extension base="xs:string">`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:extension>`<br /><br /> `</xs:simpleContent>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements"></a>Elemento con una secuencia de elementos secundarios  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. Los elementos en negrita muestran el esquema deducido para un elemento con una secuencia de elementos secundarios.  
  
> [!NOTE]
> Incluso si un elemento solo tiene un elemento secundario, se trata todavía como secuencia.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement" />`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements-and-attributes"></a>Elemento con una secuencia de elementos secundarios y atributos  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. Los elementos en negrita muestran el esquema deducido para un elemento con una secuencia de elementos secundarios y atributos.  
  
> [!NOTE]
> Incluso si un elemento solo tiene un elemento secundario, se trata todavía como secuencia.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choices-of-child-elements"></a>Elemento con una secuencia y opciones de elementos secundarios  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. Los elementos en negrita muestran el esquema deducido para un elemento con una secuencia y opción de elementos secundarios.  
  
> [!NOTE]
> El atributo `maxOccurs` del elemento `xs:choice` se establece en `"unbounded"` en el esquema deducido.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choice-of-child-elements-and-attributes"></a>Elemento con una secuencia y opción de elementos secundarios y atributos  
 La siguiente tabla muestra la entrada XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> y el esquema XML generado. Los elementos en negrita muestran el esquema deducido para un elemento con una secuencia y opción de elementos secundarios y atributos.  
  
> [!NOTE]
> El atributo `maxOccurs` del elemento `xs:choice` se establece en `"unbounded"` en el esquema deducido.  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
|XML|Schema|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="attribute-processing"></a>Procesamiento de atributos  
 Siempre que se encuentre un nuevo atributo dentro de un nodo, se añade a la definición de nodo con `use="required"`. La próxima vez que se encuentre el mismo nodo en la instancia, el proceso de deducción comparará los atributos de la instancia actual con los ya deducidos. Si alguno de los ya deducidos falta en la instancia, `use="optional"` se añade a la definición de atributo. Se añaden nuevos atributos a declaraciones existentes con `use="optional"`.  
  
### <a name="occurrence-constraints"></a>Restricciones de ocurrencias  
 Durante el proceso de deducción de esquema, los atributos `minOccurs` y `maxOccurs` se generan, para componentes deducidos de un esquema, con los valores `"0"` o `"1"` y `"1"` o `"unbounded"`. Los valores `"1"` y `"unbounded"` se utilizan solo cuando los valores `"0"` y `"1"` no pueden validar el documento XML (por ejemplo, si `MinOccurs="0"` no describe con precisión un elemento, se utiliza `minOccurs="1"`).  
  
### <a name="mixed-content"></a>Contenido mixto  
 Si un elemento contiene contenido mixto (por ejemplo, texto intercalado con elementos), el atributo `mixed="true"` se genera para la definición de tipo complejo deducida.  
  
## <a name="other-node-type-inference-rules"></a>Otras reglas de deducción de tipo de nodo  
 La tabla siguiente describe las reglas de deducción para la instrucción de procesamiento, comentario, referencia de entidad, CDATA, tipo de documento y nodos de espacio de nombres.  
  
|Tipo de nodo|Conversión|  
|---------------|-----------------|  
|Instrucción de procesamiento|ignorado.|  
|Comentario|ignorado.|  
|Referencia de entidad|La clase <xref:System.Xml.Schema.XmlSchemaInference> no controla las referencias de entidad. Si un documento XML contiene referencias de entidad, es necesario utilizar un lector que expanda las entidades. Por ejemplo, se puede pasar un <xref:System.Xml.XmlTextReader> con la <xref:System.Xml.XmlTextReader.EntityHandling%2A> propiedad establecida en <xref:System.Xml.EntityHandling.ExpandEntities> como parámetro. Si se encuentran referencias de entidad y el lector no expande entidades, se lanza una excepción.|  
|CDATA|Cualquier sección `<![CDATA[ … ]]` en un documento XML será deducida como `xs:string`.|  
|Tipo de documento|ignorado.|  
|Espacios de nombres|ignorado.|  
  
 Para más información sobre el proceso de deducción de esquema, vea [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Schema.XmlSchemaInference>
- [Modelo de objetos de esquema XML (SOM)](xml-schema-object-model-som.md)
- [Deducción de esquema XML](inferring-an-xml-schema.md)
- [Deducción de esquemas a partir de documentos XML](inferring-schemas-from-xml-documents.md)
- [Reglas para deducir tipos simples](rules-for-inferring-simple-types.md)
