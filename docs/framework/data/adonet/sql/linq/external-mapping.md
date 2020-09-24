---
title: Asignación externa
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: 79427cde0784746480e851cf1be56c8bce854919
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161391"
---
# <a name="external-mapping"></a>Asignación externa

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite la *asignación externa*, un proceso por el que se utiliza un archivo XML independiente para especificar la asignación entre el modelo de datos de la base de datos y el modelo de objetos. Las ventajas de utilizar una archivo de asignación externa son las siguientes:  
  
- Puede separar el código de la asignación del código de la aplicación. Este enfoque reduce el desorden en el código de la aplicación.  
  
- Puede tratar un archivo de asignación externo de forma similar a un archivo de configuración. Por ejemplo, puede actualizar cómo se comportará su aplicación después de distribuir los binarios simplemente cambiando el archivo de asignación externo.  
  
## <a name="requirements"></a>Requisitos  

 El archivo de asignación debe ser un archivo XML y el archivo debe validarse en un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] archivo de definición de esquema (. xsd).  
  
 Se aplican las reglas siguientes:  
  
- El archivo de asignación debe ser un archivo XML.  
  
- El archivo de asignación XML debe ser válido según el archivo de definición de esquema XML. Para obtener más información, vea [Cómo: validar archivos DBML y de asignación externa](how-to-validate-dbml-and-external-mapping-files.md).  
  
- La asignación externa invalida la asignación basada en atributos. En otras palabras, al utilizar un origen de asignación externo para crear un <xref:System.Data.Linq.DataContext>, el <xref:System.Data.Linq.DataContext> omite todos los atributos de asignación que se han creado en las clases. Este comportamiento es cierto si la clase está incluida en el archivo de asignación externo.  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite el uso híbrido de los dos enfoques de asignación (basado en atributos y externo).  
  
## <a name="xml-schema-definition-file"></a>Archivo de definición de esquema XML  

 La asignación externa en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] debe ser válida según la siguiente definición de esquema XML.  
  
 Distinga este archivo de definición de esquema del archivo de definición de esquema que se utiliza para validar un archivo DBML. Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md)).  
  
> [!NOTE]
> Los usuarios de Visual Studio también encontrarán este archivo XSD en el cuadro de diálogo esquemas XML como "LinqToSqlMapping. xsd". Para usar correctamente este archivo para validar un archivo de asignación externo, vea [Cómo: validar archivos DBML y de asignación externa](how-to-validate-dbml-and-external-mapping-files.md).  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Consulte también

- [Generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md)
- [Referencia](reference.md)
- [Procedimiento para generar el modelo de objetos como un archivo externo](how-to-generate-the-object-model-as-an-external-file.md)
