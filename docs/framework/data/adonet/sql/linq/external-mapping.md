---
description: 'Más información acerca de: asignación externa'
title: Asignación externa
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: 8c09e3bdf1798757bedfac9e568a0384a8e6bb49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786087"
---
# <a name="external-mapping"></a><span data-ttu-id="75d30-103">Asignación externa</span><span class="sxs-lookup"><span data-stu-id="75d30-103">External Mapping</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="75d30-104">admite la *asignación externa*, un proceso por el que se utiliza un archivo XML independiente para especificar la asignación entre el modelo de datos de la base de datos y el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="75d30-104">supports *external mapping*, a process by which you use a separate XML file to specify mapping between the data model of the database and your object model.</span></span> <span data-ttu-id="75d30-105">Las ventajas de utilizar una archivo de asignación externa son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="75d30-105">Advantages of using an external mapping file include the following:</span></span>  
  
- <span data-ttu-id="75d30-106">Puede separar el código de la asignación del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75d30-106">You can keep your mapping code out of your application code.</span></span> <span data-ttu-id="75d30-107">Este enfoque reduce el desorden en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75d30-107">This approach reduces clutter in your application code.</span></span>  
  
- <span data-ttu-id="75d30-108">Puede tratar un archivo de asignación externo de forma similar a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="75d30-108">You can treat an external mapping file something like a configuration file.</span></span> <span data-ttu-id="75d30-109">Por ejemplo, puede actualizar cómo se comportará su aplicación después de distribuir los binarios simplemente cambiando el archivo de asignación externo.</span><span class="sxs-lookup"><span data-stu-id="75d30-109">For example, you can update how your application behaves after shipping the binaries by just swapping out the external mapping file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75d30-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75d30-110">Requirements</span></span>  

 <span data-ttu-id="75d30-111">El archivo de asignación debe ser un archivo XML y el archivo debe validarse en un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] archivo de definición de esquema (. xsd).</span><span class="sxs-lookup"><span data-stu-id="75d30-111">The mapping file must be an XML file, and the file must validate against a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] schema definition (.xsd) file.</span></span>  
  
 <span data-ttu-id="75d30-112">Se aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="75d30-112">The following rules apply:</span></span>  
  
- <span data-ttu-id="75d30-113">El archivo de asignación debe ser un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="75d30-113">The mapping file must be an XML file.</span></span>  
  
- <span data-ttu-id="75d30-114">El archivo de asignación XML debe ser válido según el archivo de definición de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="75d30-114">The XML mapping file must be valid against the XML schema definition file.</span></span> <span data-ttu-id="75d30-115">Para obtener más información, vea [Cómo: validar archivos DBML y de asignación externa](how-to-validate-dbml-and-external-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="75d30-115">For more information, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
- <span data-ttu-id="75d30-116">La asignación externa invalida la asignación basada en atributos.</span><span class="sxs-lookup"><span data-stu-id="75d30-116">External mapping overrides attribute-based mapping.</span></span> <span data-ttu-id="75d30-117">En otras palabras, al utilizar un origen de asignación externo para crear un <xref:System.Data.Linq.DataContext>, el <xref:System.Data.Linq.DataContext> omite todos los atributos de asignación que se han creado en las clases.</span><span class="sxs-lookup"><span data-stu-id="75d30-117">In other words, when you use an external mapping source to create a <xref:System.Data.Linq.DataContext>, the <xref:System.Data.Linq.DataContext> ignores all mapping attributes you have created on classes.</span></span> <span data-ttu-id="75d30-118">Este comportamiento es cierto si la clase está incluida en el archivo de asignación externo.</span><span class="sxs-lookup"><span data-stu-id="75d30-118">This behavior is true whether the class is included in the external mapping file.</span></span>  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="75d30-119">no admite el uso híbrido de los dos enfoques de asignación (basado en atributos y externo).</span><span class="sxs-lookup"><span data-stu-id="75d30-119">does not support the hybrid use of the two mapping approaches (attribute-based and external).</span></span>  
  
## <a name="xml-schema-definition-file"></a><span data-ttu-id="75d30-120">Archivo de definición de esquema XML</span><span class="sxs-lookup"><span data-stu-id="75d30-120">XML Schema Definition File</span></span>  

 <span data-ttu-id="75d30-121">La asignación externa en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] debe ser válida según la siguiente definición de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="75d30-121">External mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be valid against the following XML schema definition.</span></span>  
  
 <span data-ttu-id="75d30-122">Distinga este archivo de definición de esquema del archivo de definición de esquema que se utiliza para validar un archivo DBML.</span><span class="sxs-lookup"><span data-stu-id="75d30-122">Distinguish this schema definition file from the schema definition file that is used to validate a DBML file.</span></span> <span data-ttu-id="75d30-123">Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="75d30-123">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75d30-124">Los usuarios de Visual Studio también encontrarán este archivo XSD en el cuadro de diálogo esquemas XML como "LinqToSqlMapping. xsd".</span><span class="sxs-lookup"><span data-stu-id="75d30-124">Visual Studio users will also find this XSD file in the XML Schemas dialog box as "LinqToSqlMapping.xsd".</span></span> <span data-ttu-id="75d30-125">Para usar correctamente este archivo para validar un archivo de asignación externo, vea [Cómo: validar archivos DBML y de asignación externa](how-to-validate-dbml-and-external-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="75d30-125">To use this file correctly for validating an external mapping file, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75d30-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="75d30-126">See also</span></span>

- [<span data-ttu-id="75d30-127">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="75d30-127">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="75d30-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="75d30-128">Reference</span></span>](reference.md)
- [<span data-ttu-id="75d30-129">Procedimiento para generar el modelo de objetos como un archivo externo</span><span class="sxs-lookup"><span data-stu-id="75d30-129">How to: Generate the Object Model as an External File</span></span>](how-to-generate-the-object-model-as-an-external-file.md)
