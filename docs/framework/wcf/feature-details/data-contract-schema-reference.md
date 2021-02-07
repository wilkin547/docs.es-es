---
description: 'Más información acerca de: referencia de esquema de contrato de datos'
title: Referencia de esquema de contrato de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: 3449340600ea5c55ef46433031e53266a218bd6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756648"
---
# <a name="data-contract-schema-reference"></a>Referencia de esquema de contrato de datos

En este tema se describe el subconjunto del esquema XML (XSD) que <xref:System.Runtime.Serialization.DataContractSerializer> usa para describir los tipos de Common Language Runtime (CLR) para la serialización XML.

## <a name="datacontractserializer-mappings"></a>Asignaciones de DataContractSerializer

`DataContractSerializer`Asigna los tipos CLR a XSD cuando los metadatos se exportan desde un servicio de Windows Communication Foundation (WCF) mediante un punto de conexión de metadatos o la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Para obtener más información, vea [serializador de contrato de datos](data-contract-serializer.md).

El `DataContractSerializer` también asigna XSD a tipos de CLR cuando Svcutil.exe se utiliza para tener acceso al lenguaje de descripción de servicios Web (WSDL) o documentos XSD y para generar contratos de datos para servicios o clientes.

Solo las instancias de esquema XML que cumplen los requisitos mencionados en este documento pueden asignarse a tipos de CLR utilizando `DataContractSerializer`.

### <a name="support-levels"></a>Niveles de compatibilidad

El `DataContractSerializer` proporciona los niveles siguientes de compatibilidad para una característica de esquema XML determinada:

- **Admitido**. Hay asignación explícita desde esta característica a tipos o atributos CLR (o a ambos) mediante `DataContractSerializer`.

- Se **omite**. La característica se permite en esquemas importados por el `DataContractSerializer`, pero no tiene ningún efecto sobre la generación de código.

- **Prohibido**. El `DataContractSerializer` no permite importar un esquema mediante la característica. Por ejemplo, Svcutil.exe, al obtener acceso a un WSDL con un esquema que utiliza esta característica, vuelve a utilizar el <xref:System.Xml.Serialization.XmlSerializer> en su lugar. Esto se aplica de manera predeterminada.

## <a name="general-information"></a>Información general

- El espacio de nombres del esquema se describe en [Esquema XML](https://www.w3.org/2001/XMLSchema). El prefijo "xs" se utiliza en este documento.

- Cualquier atributo con un espacio de nombres que no sea del esquema Se ignora.

- Se omite cualquier anotación (excepto aquellas descritas en este documento).

### <a name="xsschema-attributes"></a>\<xs:schema>: atributos

|Atributo|DataContract|
|---------------|------------------|
|`attributeFormDefault`|ignorado.|
|`blockDefault`|ignorado.|
|`elementFormDefault`|Se debe calificar. Todos los elementos se deben calificar para un esquema para que `DataContractSerializer`los admita. Esto puede realizarse si se establece en xs:schema/@elementFormDefault "Qualified" o se establece xs:element/@form en "Qualified" en cada declaración de elemento individual.|
|`finalDefault`|ignorado.|
|`Id`|ignorado.|
|`targetNamespace`|Admitido y asignado al espacio de nombres del contrato de datos. Si no se especifica este atributo, se utiliza el espacio de nombres en blanco. No puede ser el espacio de nombres reservado `http://schemas.microsoft.com/2003/10/Serialization/` .|
|`version`|ignorado.|

### <a name="xsschema-contents"></a>\<xs:schema>: contenido

|Contenido|Schema|
|--------------|------------|
|`include`|Compatible. `DataContractSerializer` admite xs:include y xs:import. Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local. La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.|
|`redefine`|Prohibido. El uso de `xs:redefine` se prohíbe por parte de `DataContractSerializer` por razones de seguridad: `x:redefine` requiere que se siga `schemaLocation` . En ciertas circunstancias, el uso de DataContract por parte de Svcutil.exe restringe el uso de `schemaLocation`.|
|`import`|Compatible. `DataContractSerializer` admite `xs:include` y `xs:import`. Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local. La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.|
|`simpleType`|Compatible. Vea la sección `xs:simpleType` .|
|`complexType`|Admitido, se asigna a contratos de datos. Vea la sección `xs:complexType` .|
|`group`|ignorado. `DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`. Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.|
|`attributeGroup`|ignorado. `DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`. Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.|
|`element`|Compatible. Vea la declaración de elemento global (GED).|
|`attribute`|ignorado. `DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`. Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.|
|`notation`|ignorado.|

## <a name="complex-types--xscomplextype"></a>Tipos complejos: \<xs:complexType>

### <a name="general-information"></a>Información general

Cada tipo complejo \<xs:complexType> se asigna a un contrato de datos.

### <a name="xscomplextype-attributes"></a>\<xs:complexType>: atributos

|Atributo|Schema|
|---------------|------------|
|`abstract`|Debe ser false (valor predeterminado).|
|`block`|Prohibido.|
|`final`|ignorado.|
|`id`|ignorado.|
|`mixed`|Debe ser false (valor predeterminado).|
|`name`|Admitido y asignado al nombre del contrato de datos. Si hay puntos en el nombre, se realiza un intento de asignar el tipo a un tipo interno. Por ejemplo, un tipo complejo denominado `A.B` asigna a un tipo de contrato de datos que es un tipo interno de un tipo con el nombre de contrato de datos `A`, pero solo si existe este tipo de contrato de datos. Es posible más de un nivel de anidación: por ejemplo, `A.B.C` puede ser un tipo interno, pero solo si existen `A` y `A.B` .|

### <a name="xscomplextype-contents"></a>\<xs:complexType>: contenido

|Contenido|Schema|
|--------------|------------|
|`simpleContent`|Se prohíben las extensiones.<br /><br /> La restricción solo se permite desde `anySimpleType`.|
|`complexContent`|Compatible. Vea “Herencia”.|
|`group`|Prohibido.|
|`all`|Prohibido.|
|`choice`|Prohibido|
|`sequence`|Admitido, asigna a los miembros de datos de un contrato de datos.|
|`attribute`|Prohibido, aun cuando uso = "prohibido" (con una excepción). Solo se admiten los atributos opcionales del espacio de nombres del esquema de serialización estándar. No asignan a miembros de datos en el modelo de programación del contrato de datos. Actualmente, solo un atributo de este tipo tiene significado y se trata en la sección ISerializable. El resto se pasa por alto.|
|`attributeGroup`|Prohibido. En la versión WCF v1, `DataContractSerializer` omite la presencia de `attributeGroup` dentro de `xs:complexType` .|
|`anyAttribute`|Prohibido.|
|(vacío)|Se asigna a un contrato de datos sin miembros de datos.|

### <a name="xssequence-in-a-complex-type-attributes"></a>\<xs:sequence> en un tipo complejo: atributos

|Atributo|Schema|
|---------------|------------|
|`id`|ignorado.|
|`maxOccurs`|Debe ser 1 (valor predeterminado).|
|`minOccurs`|Debe ser 1 (valor predeterminado).|

### <a name="xssequence-in-a-complex-type-contents"></a>\<xs:sequence> en un tipo complejo: contenido

|Contenido|Schema|
|--------------|------------|
|`element`|Cada instancia asigna a un miembro de datos.|
|`group`|Prohibido.|
|`choice`|Prohibido.|
|`sequence`|Prohibido.|
|`any`|Prohibido.|
|(vacío)|Se asigna a un contrato de datos sin miembros de datos.|

## <a name="elements--xselement"></a>Elemento \<xs:element>

### <a name="general-information"></a>Información general

`<xs:element>` puede aparecer en los contextos siguientes:

- Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos normal (no de una colección). En este caso, el atributo `maxOccurs` debe ser 1. (No se permite un valor de 0).

- Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos de colección. En este caso, el atributo `maxOccurs` debe ser mayor que 1 o "ilimitado".

- Puede ocurrir dentro de `<xs:schema>` como una declaración de elemento global (GED).

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a>\<xs:element> con maxOccurs = 1 dentro de \<xs:sequence> (miembros de datos)

|Atributo|Schema|
|---------------|------------|
|`ref`|Prohibido.|
|`name`|Admitido, asigna al nombre del miembro de datos.|
|`type`|Admitido, asigna al tipo de miembro de datos. Para obtener más información, vea Asignación de tipo/primitivo. Si no se especifica (y el elemento no contiene un tipo anónimo), se supone `xs:anyType` .|
|`block`|ignorado.|
|`default`|Prohibido.|
|`fixed`|Prohibido.|
|`form`|Se debe calificar. Este atributo se puede establecer mediante `elementFormDefault` en `xs:schema`.|
|`id`|ignorado.|
|`maxOccurs`|1|
|`minOccurs`|Se asigna a la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> de un miembro de datos (`IsRequired` es true cuando `minOccurs` es 1).|
|`nillable`|Afecta a la asignación de tipo. Vea Asignación de tipo/primitivo.|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a>\<xs:element> con maxOccurs>1 en \<xs:sequence> (colecciones)

- Asigna a un <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.

- En tipos de colección, solo se permite un xs:element dentro de un xs:sequence.

 Las colecciones pueden ser de los siguientes tipos:

- Colecciones normales (por ejemplo, matrices).

- Colecciones de diccionarios (asignan un valor a otro; por ejemplo, un <xref:System.Collections.Hashtable>).

- La única diferencia entre un diccionario y una matriz de un tipo de par clave-valor está en el modelo de programación generado. Hay un mecanismo de anotación de esquema que se puede utilizar para indicar que un tipo determinado es una colección de diccionarios.

Las reglas para los atributos `ref`, `block`, `default`, `fixed`, `form`e `id` son las mismas que para el caso de que no se trate de una colección. Entre otros atributos se incluyen los de la tabla siguiente.

|Atributo|Schema|
|---------------|------------|
|`name`|Admitido, asigna a la propiedad <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> en el atributo `CollectionDataContractAttribute` .|
|`type`|Admitido, asigna al tipo almacenado en la colección.|
|`maxOccurs`|Mayor que 1 o "ilimitado". El esquema de DC debería utilizar "ilimitado."|
|`minOccurs`|ignorado.|
|`nillable`|Afecta a la asignación de tipo. Este atributo se omite para las colecciones de diccionarios.|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a>\<xs:element> dentro de una \<xs:schema> declaración de elemento global

- Una declaración de elemento global (GED) que tiene el mismo nombre y espacio de nombres que un tipo en esquema o que define un tipo anónimo dentro de sí mismo, se dice que está asociado al tipo.

- Exportación del esquema: las GED asociadas se generan para cada tipo generado, tanto simple como complejo.

- Deserialización/serialización: las GED asociadas se utilizan como elementos raíz para el tipo.

- Importación del esquema: las GED asociadas no se requieren y se omiten si siguen las reglas siguientes (a menos que definan tipos).

|Atributo|Schema|
|---------------|------------|
|`abstract`|Debe ser false para GED asociadas.|
|`block`|Se prohíbe en GED asociadas.|
|`default`|Se prohíbe en GED asociadas.|
|`final`|Debe ser false para GED asociadas.|
|`fixed`|Se prohíbe en GED asociadas.|
|`id`|ignorado.|
|`name`|Compatible. Vea la definición de GED asociadas.|
|`nillable`|Debe ser true para las GED asociadas.|
|`substitutionGroup`|Se prohíbe en GED asociadas.|
|`type`|Admitido y debe coincidir con el tipo asociado para las GED asociadas (a menos que el elemento contenga un tipo anónimo).|

### <a name="xselement-contents"></a>\<xs:element>: contenido

|Contenido|Schema|
|--------------|------------|
|`simpleType`|Admitido.*|
|`complexType`|Admitido.*|
|`unique`|ignorado.|
|`key`|ignorado.|
|`keyref`|ignorado.|
|(en blanco)|Compatible.|

\* Cuando se usa `simpleType` la `complexType,` asignación y para tipos anónimos es igual que para los tipos no anónimos, salvo que no hay ningún contrato de datos anónimos, por lo que se crea un contrato de datos con nombre, con un nombre generado derivado del nombre del elemento. Las reglas para los tipos anónimos están en la lista siguiente:

- Detalle de implementación de WCF: Si el `xs:element` nombre no contiene puntos, el tipo anónimo se asigna a un tipo interno del tipo de contrato de datos externo. Si el nombre contiene puntos, el tipo de contrato de datos resultante es independiente (no un tipo interno).

- El nombre de contrato de datos generado del tipo interno es el nombre de contrato de datos del tipo exterior seguido por un punto, el nombre del elemento, y la cadena “Type”.

- Si un contrato de datos con este tipo de nombre ya existe, el nombre se hace único anexando "1", "2", "3", y así sucesivamente, hasta que se cree un nombre único.

## <a name="simple-types---xssimpletype"></a>Tipos simples: \<xs:simpleType>

### <a name="xssimpletype-attributes"></a>\<xs:simpleType>: atributos

|Atributo|Schema|
|---------------|------------|
|`final`|ignorado.|
|`id`|ignorado.|
|`name`|Admitido, asigna al nombre de contrato de datos.|

### <a name="xssimpletype-contents"></a>\<xs:simpleType>: contenido

|Contenido|Schema|
|--------------|------------|
|`restriction`|Compatible. Asigna a contratos de datos de enumeración. Este atributo se omite si no coincide con el patrón de enumeración. Vea la sección de restricciones de `xs:simpleType` .|
|`list`|Compatible. Asigna a contratos de datos de enumeración de marcas. Vea la sección de listas de `xs:simpleType` .|
|`union`|Prohibido.|

### \<xs:restriction>

- Las restricciones de tipos complejos solo se admiten para base = "`xs:anyType`".

- Las restricciones de tipos simples de `xs:string` que no tienen facetas de restricciones que no sean `xs:enumeration` están asignadas a contratos de datos de enumeración.

- El resto de restricciones de tipos simples se asignan a los tipos que restringen. Por ejemplo, una restricción de `xs:int` se asigna a un entero, como hace `xs:int` . Para obtener más información sobre la asignación de tipos primitivos, vea asignación de tipo/primitivo.

### <a name="xsrestriction-attributes"></a>\<xs:restriction>: atributos

|Atributo|Schema|
|---------------|------------|
|`base`|Debe ser un tipo simple admitido o `xs:anyType`.|
|`id`|ignorado.|

### <a name="xsrestriction-for-all-other-cases-contents"></a>\<xs:restriction> en todos los demás casos: contenido

|Contenido|Schema|
|--------------|------------|
|`simpleType`|Si está presente, se debe derivar de un tipo primitivo admitido.|
|`minExclusive`|ignorado.|
|`minInclusive`|ignorado.|
|`maxExclusive`|ignorado.|
|`maxInclusive`|ignorado.|
|`totalDigits`|ignorado.|
|`fractionDigits`|ignorado.|
|`length`|ignorado.|
|`minLength`|ignorado.|
|`maxLength`|ignorado.|
|`enumeration`|ignorado.|
|`whiteSpace`|ignorado.|
|`pattern`|ignorado.|
|(en blanco)|Compatible.|

## <a name="enumeration"></a>Enumeración

### <a name="xsrestriction-for-enumerations-attributes"></a>\<xs:restriction> para enumeraciones: atributos

|Atributo|Schema|
|---------------|------------|
|`base`|Si está presente, debe ser `xs:string`.|
|`id`|ignorado.|

### <a name="xsrestriction-for-enumerations-contents"></a>\<xs:restriction> para enumeraciones: contenido

|Contenido|Schema|
|--------------|------------|
|`simpleType`|Si está presente, debe ser una restricción de enumeración admitida por el contrato de datos (esta sección).|
|`minExclusive`|ignorado.|
|`minInclusive`|ignorado.|
|`maxExclusive`|ignorado.|
|`maxInclusive`|ignorado.|
|`totalDigits`|ignorado.|
|`fractionDigits`|ignorado.|
|`length`|Prohibido.|
|`minLength`|Prohibido.|
|`maxLength`|Prohibido.|
|`enumeration`|Compatible. Se omite el "id" de enumeración y "value" se asigna al nombre del valor en el contrato de datos de enumeración.|
|`whiteSpace`|Prohibido.|
|`pattern`|Prohibido.|
|(vacío)|Compatible; se asigna a un tipo de enumeración vacío.|

 En el siguiente código se muestra una clase de enumeración de C#.

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

Esta clase se asigna al esquema siguiente mediante el `DataContractSerializer`. Si los valores de la enumeración se inician en 1, no se generan bloques `xs:annotation` .

```xml
<xs:simpleType name="MyEnum">
  <xs:restriction base="xs:string">
    <xs:enumeration value="first">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          3
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="second">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          4
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

### \<xs:list>

El`DataContractSerializer` asigna tipos de enumeración marcados con `System.FlagsAttribute` a `xs:list` derivado de `xs:string`. No se admite ninguna otra variación de `xs:list` .

### <a name="xslist-attributes"></a>\<xs:list>: atributos

|Atributo|Schema|
|---------------|------------|
|`itemType`|Prohibido.|
|`id`|ignorado.|

### <a name="xslist-contents"></a>\<xs:list>: contenido

|Contenido|Schema|
|--------------|------------|
|`simpleType`|Debe ser la restricción de `xs:string` utilizando la faceta `xs:enumeration` .|

Si el valor de enumeración no sigue una progresión de potencia 2 (valor predeterminado para marcas), el valor se almacena en `xs:annotation/xs:appInfo/ser:EnumerationValue` .

Por ejemplo, el código siguiente marca un tipo de enumeración.

```csharp
[Flags]
public enum AuthFlags
{
  AuthAnonymous = 1,
  AuthBasic = 2,
  AuthNTLM = 4,
  AuthMD5 = 16,
  AuthWindowsLiveID = 64,
}
```

Este tipo asigna al esquema siguiente.

```xml
<xs:simpleType name="AuthFlags">
    <xs:list>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value="AuthAnonymous" />
          <xs:enumeration value="AuthBasic" />
          <xs:enumeration value="AuthNTLM" />
          <xs:enumeration value="AuthMD5">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
          <xs:enumeration value="AuthWindowsLiveID">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
        </xs:restriction>
      </xs:simpleType>
    </xs:list>
  </xs:simpleType>
```

## <a name="inheritance"></a>Herencia

### <a name="general-rules"></a>Reglas Generales

Un contrato de datos puede heredar de otro contrato de datos. Tales contratos de datos asignan a una base y son derivados por tipos de extensión mediante la construcción de squema XML `<xs:extension>` .

Un contrato de datos no puede heredar de un contrato de datos de colección.

Por ejemplo, el código siguiente es un contrato de datos.

```csharp
[DataContract]
public class Person
{
  [DataMember]
  public string Name;
}
[DataContract]
public class Employee : Person
{
  [DataMember]
  public int ID;
}
```

Este contrato de datos asigna a la declaración de tipos de esquema XML siguiente.

```xml
<xs:complexType name="Employee">
 <xs:complexContent mixed="false">
  <xs:extension base="tns:Person">
   <xs:sequence>
    <xs:element minOccurs="0" name="ID" type="xs:int"/>
   </xs:sequence>
  </xs:extension>
 </xs:complexContent>
</xs:complexType>
<xs:complexType name="Person">
 <xs:sequence>
  <xs:element minOccurs="0" name="Name"
    nillable="true" type="xs:string"/>
 </xs:sequence>
</xs:complexType>
```

### <a name="xscomplexcontent-attributes"></a>\<xs:complexContent>: atributos

|Atributo|Schema|
|---------------|------------|
|`id`|ignorado.|
|`mixed`|Debe ser false.|

### <a name="xscomplexcontent-contents"></a>\<xs:complexContent>: contenido

|Contenido|Schema|
|--------------|------------|
|`restriction`|Prohibido, excepto cuando base = "`xs:anyType`". Lo último es equivalente a colocar directamente el contenido de `xs:restriction` bajo el contenedor de `xs:complexContent`.|
|`extension`|Compatible. Asigna a la herencia del contrato de datos.|

### <a name="xsextension-in-xscomplexcontent-attributes"></a>\<xs:extension> en \<xs:complexContent> : atributos

|Atributo|Schema|
|---------------|------------|
|`id`|ignorado.|
|`base`|Compatible. Asigna al tipo de contrato de datos base desde el que este tipo hereda.|

### <a name="xsextension-in-xscomplexcontent-contents"></a>\<xs:extension> en \<xs:complexContent> : contenido

Las reglas son la mismas que para el contenido `<xs:complexType>` .

Si se proporciona un `<xs:sequence>` , sus elementos de miembro asignan a los miembros de datos adicionales que se encuentran en el contrato de datos derivado.

Si un tipo derivado contiene un elemento con el mismo nombre que un elemento en un tipo base, la declaración de elementos duplicados asigna a un miembro de datos con un nombre que se genera para que sea único. Los números enteros positivos se suman al nombre del miembro de datos ("member1", "member2", etc.) hasta que se encuentre un nombre único. De manera inversa:

- Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre y tipo que un miembro de datos en un contrato de datos base, `DataContractSerializer` genera este elemento correspondiente en el tipo derivado.

- Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre que un miembro de datos en un contrato de datos base pero un tipo diferente, el `DataContractSerializer` importa un esquema con un elemento del tipo `xs:anyType` en las declaraciones de tipos base y de tipos derivados. El nombre de tipo original se conserva en `xs:annotations/xs:appInfo/ser:ActualType/@Name`.

Ambas variaciones pueden conducir a un esquema con un modelo de contenido ambiguo, que depende del orden de los miembros de datos respectivos.

## <a name="typeprimitive-mapping"></a>Asignación de tipo/primitivo.

El `DataContractSerializer` utiliza la asignación siguiente para los tipos primitivos del esquema XML.

|Tipo XSD|Tipo de .NET|
|--------------|---------------|
|`anyType`|<xref:System.Object>.|
|`anySimpleType`|<xref:System.String>.|
|`duration`|<xref:System.TimeSpan>.|
|`dateTime`|<xref:System.DateTime>.|
|`dateTimeOffset`|<xref:System.DateTime> y <xref:System.TimeSpan> para el desplazamiento. Vea abajo Serialización de DateTimeOffset.|
|`time`|<xref:System.String>.|
|`date`|<xref:System.String>.|
|`gYearMonth`|<xref:System.String>.|
|`gYear`|<xref:System.String>.|
|`gMonthDay`|<xref:System.String>.|
|`gDay`|<xref:System.String>.|
|`gMonth`|<xref:System.String>.|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|Matriz de tipo<xref:System.Byte> .|
|`hexBinary`|<xref:System.String>.|
|`float`|<xref:System.Single>.|
|`double`|<xref:System.Double>.|
|`anyURI`|<xref:System.Uri>.|
|`QName`|<xref:System.Xml.XmlQualifiedName>.|
|`string`|<xref:System.String>.|
|`normalizedString`|<xref:System.String>.|
|`token`|<xref:System.String>.|
|`language`|<xref:System.String>.|
|`Name`|<xref:System.String>.|
|`NCName`|<xref:System.String>.|
|`ID`|<xref:System.String>.|
|`IDREF`|<xref:System.String>.|
|`IDREFS`|<xref:System.String>.|
|`ENTITY`|<xref:System.String>.|
|`ENTITIES`|<xref:System.String>.|
|`NMTOKEN`|<xref:System.String>.|
|`NMTOKENS`|<xref:System.String>.|
|`decimal`|<xref:System.Decimal>.|
|`integer`|<xref:System.Int64>.|
|`nonPositiveInteger`|<xref:System.Int64>.|
|`negativeInteger`|<xref:System.Int64>.|
|`long`|<xref:System.Int64>.|
|`int`|<xref:System.Int32>.|
|`short`|<xref:System.Int16>.|
|`Byte`|<xref:System.SByte>.|
|`nonNegativeInteger`|<xref:System.Int64>.|
|`unsignedLong`|<xref:System.UInt64>.|
|`unsignedInt`|<xref:System.UInt32>.|
|`unsignedShort`|<xref:System.UInt16>.|
|`unsignedByte`|<xref:System.Byte>.|
|`positiveInteger`|<xref:System.Int64>.|

## <a name="iserializable-types-mapping"></a>Asignación de tipos ISerializable

En .NET Framework versión 1,0, <xref:System.Runtime.Serialization.ISerializable> se presentó como un mecanismo general para serializar objetos para la persistencia o la transferencia de datos. Hay muchos tipos de .NET Framework que implementan `ISerializable` y que pueden pasarse entre aplicaciones. <xref:System.Runtime.Serialization.DataContractSerializer> proporciona de manera natural compatibilidad para las clases `ISerializable` . `DataContractSerializer` asigna tipos de esquema de implementación de `ISerializable` que solo difieren en cuanto al QName (nombre completo) del tipo y son colecciones de propiedades. Por ejemplo, `DataContractSerializer` se asigna <xref:System.Exception> al siguiente tipo XSD en el `http://schemas.datacontract.org/2004/07/System` espacio de nombres.

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

El atributo opcional `ser:FactoryType` opcional declarado en el esquema de serialización de contrato de datos hace referencia a una clase de generador que puede deserializar el tipo. La clase de generador debe formar parte de la colección de tipos conocidos de la instancia de `DataContractSerializer` que se está usando. Para obtener más información sobre los tipos conocidos, consulte [Data Contract known Types](data-contract-known-types.md).

## <a name="datacontract-serialization-schema"></a>Esquema de serialización de DataContract

Varios esquemas exportados por los tipos de uso, elementos y atributos del `DataContractSerializer` , desde un espacio de nombres de serialización de contrato de datos especial:

`http://schemas.microsoft.com/2003/10/Serialization`

A continuación, se muestra una declaración de esquema de serialización de contrato de datos completa.

```xml
<xs:schema attributeFormDefault="qualified"
   elementFormDefault="qualified"
   targetNamespace =
    "http://schemas.microsoft.com/2003/10/Serialization/"
   xmlns:xs="http://www.w3.org/2001/XMLSchema"
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">

 <!-- Top-level elements for primitive types. -->
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>
 <xs:element name="base64Binary"
       nillable="true" type="xs:base64Binary"/>
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>
 <xs:element name="byte" nillable="true" type="xs:byte"/>
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>
 <xs:element name="double" nillable="true" type="xs:double"/>
 <xs:element name="float" nillable="true" type="xs:float"/>
 <xs:element name="int" nillable="true" type="xs:int"/>
 <xs:element name="long" nillable="true" type="xs:long"/>
 <xs:element name="QName" nillable="true" type="xs:QName"/>
 <xs:element name="short" nillable="true" type="xs:short"/>
 <xs:element name="string" nillable="true" type="xs:string"/>
 <xs:element name="unsignedByte"
       nillable="true" type="xs:unsignedByte"/>
 <xs:element name="unsignedInt"
       nillable="true" type="xs:unsignedInt"/>
 <xs:element name="unsignedLong"
       nillable="true" type="xs:unsignedLong"/>
 <xs:element name="unsignedShort"
       nillable="true" type="xs:unsignedShort"/>

 <!-- Primitive types introduced for certain .NET simple types. -->
 <xs:element name="char" nillable="true" type="tns:char"/>
 <xs:simpleType name="char">
  <xs:restriction base="xs:int"/>
 </xs:simpleType>

 <!-- xs:duration is restricted to an ordered value space,
    to map to System.TimeSpan -->
 <xs:element name="duration" nillable="true" type="tns:duration"/>
 <xs:simpleType name="duration">
  <xs:restriction base="xs:duration">
   <xs:pattern
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>
  </xs:restriction>
 </xs:simpleType>

 <xs:element name="guid" nillable="true" type="tns:guid"/>
 <xs:simpleType name="guid">
  <xs:restriction base="xs:string">
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>
  </xs:restriction>
 </xs:simpleType>

 <!-- This is used for schemas exported from ISerializable type. -->
 <xs:attribute name="FactoryType" type="xs:QName"/>
</xs:schema>
```

Se debería tener en cuenta lo siguiente:

- `ser:char` se introduce para representar caracteres Unicode de tipo <xref:System.Char>.

- El `valuespace` de `xs:duration` se reduce a un conjunto ordenado para que pueda asignarse a un <xref:System.TimeSpan>.

- `FactoryType` se utiliza en esquemas exportados a partir de tipos que se derivan de <xref:System.Runtime.Serialization.ISerializable>.

## <a name="importing-non-datacontract-schemas"></a>Importación de esquemas no DataContract

`DataContractSerializer` tiene la opción `ImportXmlTypes` para permitir la importación de esquemas que no cumplen el perfil XSD `DataContractSerializer` (vea la propiedad <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> ). Establecer esta opción en `true` habilita la aceptación de tipos de esquema no conformes y la asignación de ellos a la implementación siguiente, <xref:System.Xml.Serialization.IXmlSerializable> ajuste de una matriz de <xref:System.Xml.XmlNode> (solo difiere el nombre de la clase).

```csharp
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]
public partial class Person : object, IXmlSerializable
{
  private XmlNode[] nodesField;
  private static XmlQualifiedName typeName =
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");
  public XmlNode[] Nodes
  {
    get {return this.nodesField;}
    set {this.nodesField = value;}
  }
  public void ReadXml(XmlReader reader)
  {
    this.nodesField = XmlSerializableServices.ReadNodes(reader);
  }
  public void WriteXml(XmlWriter writer)
  {
    XmlSerializableServices.WriteNodes(writer, this.Nodes);
  }
  public System.Xml.Schema.XmlSchema GetSchema()
  {
    return null;
  }
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)
  {
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);
    return typeName;
  }
}
```

## <a name="datetimeoffset-serialization"></a>Serialización de DateTimeOffset

<xref:System.DateTimeOffset> no se trata como un tipo primitivo. En su lugar, se serializa como un elemento complejo con dos partes. La primera parte representa la fecha y hora, y la segunda parte representa el desplazamiento de la fecha y hora. En el siguiente código se muestra un ejemplo de un valor DateTimeOffset serializado.

```xml
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">
  <DateTime i:type="b:dateTime" xmlns=""
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00
  </DateTime>
  <OffsetMinutes i:type="b:short" xmlns=""
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480
   </OffsetMinutes>
</OffSet>
```

El esquema es de la siguiente manera.

```xml
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">
   <xs:complexType name="DateTimeOffset">
      <xs:sequence minOccurs="1" maxOccurs="1">
         <xs:element name="DateTime" type="xs:dateTime"
         minOccurs="1" maxOccurs="1" />
         <xs:element name="OffsetMinutes" type="xs:short"
         minOccurs="1" maxOccurs="1" />
      </xs:sequence>
   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [Utilización de contratos de datos](using-data-contracts.md)
