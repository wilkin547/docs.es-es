---
title: Tipos admitidos por el serializador de contrato de datos
description: Vea la lista completa de tipos que admite el serializador de contrato de datos de WCF para la serialización y deserialización.
ms.date: 03/30/2017
helpviewer_keywords:
- serialization [WCF], supported types
ms.assetid: 7381b200-437a-4506-9556-d77bf1bc3f34
ms.openlocfilehash: ef9d2e61ab7121c97bd474bb151fee32907b1dac
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246537"
---
# <a name="types-supported-by-the-data-contract-serializer"></a>Tipos admitidos por el serializador de contrato de datos

Windows Communication Foundation (WCF) utiliza <xref:System.Runtime.Serialization.DataContractSerializer> como su motor de serialización predeterminado para convertir los datos en XML y volver a convertir XML en datos. <xref:System.Runtime.Serialization.DataContractSerializer> está diseñado para serializar los tipos de *contrato de datos* . Sin embargo, admite muchos otros tipos, de los que se puede pensar que tienen un contrato de datos implícito. A continuación, se muestra una lista completa de los tipos que se pueden serializar:

- Todos los tipos públicamente visibles que tienen un constructor que no tiene parámetros.

- Tipo de contrato de datos Éstos son tipos a los que se ha aplicado el atributo <xref:System.Runtime.Serialization.DataContractAttribute> . Normalmente, los tipos personalizados que representan objetos de negocio se deberían crear como tipos de contrato de datos. Para obtener más información, vea [usar contratos de datos](using-data-contracts.md) y [tipos serializables](serializable-types.md).

- Tipos de colección. Éstos son tipos que representan listas de datos. Éstas pueden ser matrices normales de tipos o tipos de colección, como <xref:System.Collections.ArrayList> y <xref:System.Collections.Generic.Dictionary%602>. El atributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> se puede utilizar para personalizar la serialización de estos tipos, pero no se requiere. Para obtener más información, vea [tipos de colección en contratos de datos](collection-types-in-data-contracts.md).

- Tipos de enumeración. Las enumeraciones, incluidas las de marcas, son serializables. Opcionalmente, los tipos de enumeración se pueden marcar con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> , en cuyo caso cada miembro que participe en la serialización se debe marcar con el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute> . No se serializan los miembros que no están marcados. Para obtener más información, vea [tipos de enumeración en contratos de datos](enumeration-types-in-data-contracts.md).

- Tipos primitivos de .NET Framework. Los tipos siguientes integrados en .NET Framework pueden serializarse y se consideran como tipos primitivos: <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Boolean>, <xref:System.Char>, <xref:System.Decimal>, <xref:System.Object>y <xref:System.String>.

- Otros tipos primitivos. Estos tipos no son primitivos en .NET Framework, pero se tratan como primitivos en forma de XML serializado. Estos tipos son <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>, <xref:System.Xml.XmlQualifiedName>y matrices de <xref:System.Byte>.

  > [!NOTE]
  > A diferencia de otros tipos primitivos, <xref:System.DateTimeOffset> no es de un tipo conocido de forma predeterminada. Para obtener más información, vea [tipos conocidos de contratos de datos](data-contract-known-types.md).

- Tipos marcados con el atributo <xref:System.SerializableAttribute> . Muchos tipos incluidos en la biblioteca de clases base .NET Framework entran dentro de esta categoría. <xref:System.Runtime.Serialization.DataContractSerializer> admite totalmente este modelo de programación de serialización que fue utilizado por la comunicación remota de .NET Framework, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>, incluida la compatibilidad para la interfaz <xref:System.Runtime.Serialization.ISerializable> .

- Tipos que representan XML sin formato o tipos que representan datos relacionales ADO.NET. <xref:System.Xml.XmlElement> y la matriz de tipos <xref:System.Xml.XmlNode> se admiten como una manera de representar XML directamente. De manera adicional, se admiten los tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable> , incluido el atributo relacionado <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> y los tipos <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement> . El <xref:System.Data.DataTable> tipo ADO.net y el <xref:System.Data.DataSet> tipo (así como sus clases derivadas con tipo) implementan la <xref:System.Xml.Serialization.IXmlSerializable> interfaz y, por tanto, entran en esta categoría. Para obtener más información, vea [tipos XML y ADO.net en los contratos de datos](xml-and-ado-net-types-in-data-contracts.md).

## <a name="limitations-of-using-certain-types-in-partial-trust-mode"></a>Limitaciones del uso de ciertos tipos en modo de confianza parcial

A continuación, se enumeran las limitaciones que existen al utilizar ciertos tipos en escenarios de modo de confianza parcial:

- Para serializar o deserializar un tipo que implementa <xref:System.Runtime.Serialization.ISerializable> en código de confianza parcial mediante el uso de <xref:System.Runtime.Serialization.DataContractSerializer> se requieren los permisos <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> y <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> .

- Al ejecutar el código de WCF en el modo de [confianza parcial](partial-trust.md) , no se admite la serialización y deserialización de `readonly` los campos ( `public` y `private` ). Esto se debe a que el IL generado no se puede comprobar y, por consiguiente, requiere permisos elevados.

- Tanto <xref:System.Runtime.Serialization.DataContractSerializer> como <xref:System.Xml.Serialization.XmlSerializer> se admiten en un entorno de confianza parcial. Sin embargo, el uso de <xref:System.Runtime.Serialization.DataContractSerializer> está sujeto a las condiciones siguientes:

  - Todos los tipos `[DataContract]` serializables deben ser públicos.

  - Todos los campos `[DataMember]` serializables o propiedades en un tipo `[DataContract]` deben ser públicos y de lectura/escritura. No se admite la serialización y deserialización de `readonly` campos al ejecutar WCF en una aplicación de confianza parcial.

  - El atributo `[Serializable]`/`ISerializable]` no se admite en un entorno de confianza parcial.

  - Los tipos conocidos se deben especificar mediante código o configuración del nivel de equipo (`Machine.config`). Los tipos conocidos no se pueden especificar en la configuración del nivel de de aplicación por razones de seguridad.

- Los tipos que implementan <xref:System.Runtime.Serialization.IObjectReference> producirán una excepción en un entorno de confianza parcial porque el método <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%2A> requiere el permiso de seguridad `[SecurityPermission(SecurityAction.LinkDemand, Flags=SecurityPermissionFlag.SerializationFormatter)]`.

## <a name="additional-notes-on-serialization"></a>Notas adicionales sobre serialización

Las reglas siguientes también se aplican a los tipos admitidos por el serializador de contrato de datos:

- El serializador del contrato de datos admite totalmente los tipos genéricos.

- El serializador del contrato de datos admite totalmente los tipos de valor que aceptan valores NULL.

- Los tipos de interfaz se tratan como <xref:System.Object> o, en el caso de interfaces de colección, como tipos de colección.

- Se admiten tanto las estructuras como las clases.

- No <xref:System.Runtime.Serialization.DataContractSerializer> admite el modelo de programación utilizado por los <xref:System.Xml.Serialization.XmlSerializer> servicios Web y ASP.net. En particular, no admite atributos como <xref:System.Xml.Serialization.XmlElementAttribute> y <xref:System.Xml.Serialization.XmlAttributeAttribute>. Para habilitar la compatibilidad con este modelo de programación, se debe cambiar WCF para que use en <xref:System.Xml.Serialization.XmlSerializer> lugar de <xref:System.Runtime.Serialization.DataContractSerializer> .

- El tipo <xref:System.DBNull> se trata de una manera especial. Es un tipo singleton y tras la deserialización, el deserializador respeta la restricción de singleton y señala todas las referencias `DBNull` a la instancia de singleton. Dado que `DBNull` es un tipo serializable, exige permiso <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> .

## <a name="see-also"></a>Vea también

- [Clases de XML y ADO.NET en contratos de datos](xml-and-ado-net-types-in-data-contracts.md)
- [Utilización de contratos de datos](using-data-contracts.md)
- [Tipos serializables](serializable-types.md)
- [Tipos de colección en contratos de datos](collection-types-in-data-contracts.md)
- [Tipos de enumeración en contratos de datos](enumeration-types-in-data-contracts.md)
