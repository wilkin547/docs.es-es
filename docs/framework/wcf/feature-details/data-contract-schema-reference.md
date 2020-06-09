---
title: Referencia de esquema de contrato de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: 04d1f753e5788460404942a21a29e1612f674e90
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593573"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="38617-102">Referencia de esquema de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="38617-102">Data Contract Schema Reference</span></span>

<span data-ttu-id="38617-103">En este tema se describe el subconjunto del esquema XML (XSD) que <xref:System.Runtime.Serialization.DataContractSerializer> usa para describir los tipos de Common Language Runtime (CLR) para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="38617-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>

## <a name="datacontractserializer-mappings"></a><span data-ttu-id="38617-104">Asignaciones de DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="38617-104">DataContractSerializer Mappings</span></span>

<span data-ttu-id="38617-105">`DataContractSerializer`Asigna los tipos CLR a XSD cuando los metadatos se exportan desde un servicio de Windows Communication Foundation (WCF) mediante un punto de conexión de metadatos o la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="38617-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="38617-106">Para obtener más información, vea [serializador de contrato de datos](data-contract-serializer.md).</span><span class="sxs-lookup"><span data-stu-id="38617-106">For more information, see [Data Contract Serializer](data-contract-serializer.md).</span></span>

<span data-ttu-id="38617-107">El `DataContractSerializer` también asigna XSD a tipos de CLR cuando Svcutil.exe se utiliza para tener acceso al lenguaje de descripción de servicios Web (WSDL) o documentos XSD y para generar contratos de datos para servicios o clientes.</span><span class="sxs-lookup"><span data-stu-id="38617-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>

<span data-ttu-id="38617-108">Solo las instancias de esquema XML que cumplen los requisitos mencionados en este documento pueden asignarse a tipos de CLR utilizando `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="38617-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>

### <a name="support-levels"></a><span data-ttu-id="38617-109">Niveles de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="38617-109">Support Levels</span></span>

<span data-ttu-id="38617-110">El `DataContractSerializer` proporciona los niveles siguientes de compatibilidad para una característica de esquema XML determinada:</span><span class="sxs-lookup"><span data-stu-id="38617-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>

- <span data-ttu-id="38617-111">**Admitido**.</span><span class="sxs-lookup"><span data-stu-id="38617-111">**Supported**.</span></span> <span data-ttu-id="38617-112">Hay asignación explícita desde esta característica a tipos o atributos CLR (o a ambos) mediante `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="38617-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>

- <span data-ttu-id="38617-113">Se **omite**.</span><span class="sxs-lookup"><span data-stu-id="38617-113">**Ignored**.</span></span> <span data-ttu-id="38617-114">La característica se permite en esquemas importados por el `DataContractSerializer`, pero no tiene ningún efecto sobre la generación de código.</span><span class="sxs-lookup"><span data-stu-id="38617-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>

- <span data-ttu-id="38617-115">**Prohibido**.</span><span class="sxs-lookup"><span data-stu-id="38617-115">**Forbidden**.</span></span> <span data-ttu-id="38617-116">El `DataContractSerializer` no permite importar un esquema mediante la característica.</span><span class="sxs-lookup"><span data-stu-id="38617-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="38617-117">Por ejemplo, Svcutil.exe, al obtener acceso a un WSDL con un esquema que utiliza esta característica, vuelve a utilizar el <xref:System.Xml.Serialization.XmlSerializer> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="38617-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="38617-118">Esto se aplica de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="38617-118">This is by default.</span></span>

## <a name="general-information"></a><span data-ttu-id="38617-119">Información general</span><span class="sxs-lookup"><span data-stu-id="38617-119">General Information</span></span>

- <span data-ttu-id="38617-120">El espacio de nombres del esquema se describe en [Esquema XML](https://www.w3.org/2001/XMLSchema).</span><span class="sxs-lookup"><span data-stu-id="38617-120">The schema namespace is described at [XML Schema](https://www.w3.org/2001/XMLSchema).</span></span> <span data-ttu-id="38617-121">El prefijo "xs" se utiliza en este documento.</span><span class="sxs-lookup"><span data-stu-id="38617-121">The prefix "xs" is used in this document.</span></span>

- <span data-ttu-id="38617-122">Cualquier atributo con un espacio de nombres que no sea del esquema Se ignora.</span><span class="sxs-lookup"><span data-stu-id="38617-122">Any attributes with a non-schema namespace are ignored.</span></span>

- <span data-ttu-id="38617-123">Se omite cualquier anotación (excepto aquellas descritas en este documento).</span><span class="sxs-lookup"><span data-stu-id="38617-123">Any annotations (except for those described in this document) are ignored.</span></span>

### <a name="xsschema-attributes"></a><span data-ttu-id="38617-124">\<xs:schema>: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-124">\<xs:schema>: attributes</span></span>

|<span data-ttu-id="38617-125">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-125">Attribute</span></span>|<span data-ttu-id="38617-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="38617-126">DataContract</span></span>|
|---------------|------------------|
|`attributeFormDefault`|<span data-ttu-id="38617-127">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-127">Ignored.</span></span>|
|`blockDefault`|<span data-ttu-id="38617-128">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-128">Ignored.</span></span>|
|`elementFormDefault`|<span data-ttu-id="38617-129">Se debe calificar.</span><span class="sxs-lookup"><span data-stu-id="38617-129">Must be qualified.</span></span> <span data-ttu-id="38617-130">Todos los elementos se deben calificar para un esquema para que `DataContractSerializer`los admita.</span><span class="sxs-lookup"><span data-stu-id="38617-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="38617-131">Esto puede realizarse si se establece en xs:schema/@elementFormDefault "Qualified" o se establece xs:element/@form en "Qualified" en cada declaración de elemento individual.</span><span class="sxs-lookup"><span data-stu-id="38617-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|
|`finalDefault`|<span data-ttu-id="38617-132">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-132">Ignored.</span></span>|
|`Id`|<span data-ttu-id="38617-133">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-133">Ignored.</span></span>|
|`targetNamespace`|<span data-ttu-id="38617-134">Admitido y asignado al espacio de nombres del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="38617-135">Si no se especifica este atributo, se utiliza el espacio de nombres en blanco.</span><span class="sxs-lookup"><span data-stu-id="38617-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="38617-136">No puede ser el espacio de nombres reservado `http://schemas.microsoft.com/2003/10/Serialization/` .</span><span class="sxs-lookup"><span data-stu-id="38617-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|
|`version`|<span data-ttu-id="38617-137">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-137">Ignored.</span></span>|

### <a name="xsschema-contents"></a><span data-ttu-id="38617-138">\<xs:schema>: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-138">\<xs:schema>: contents</span></span>

|<span data-ttu-id="38617-139">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-139">Contents</span></span>|<span data-ttu-id="38617-140">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-140">Schema</span></span>|
|--------------|------------|
|`include`|<span data-ttu-id="38617-141">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-141">Supported.</span></span> <span data-ttu-id="38617-142">`DataContractSerializer` admite xs:include y xs:import.</span><span class="sxs-lookup"><span data-stu-id="38617-142">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="38617-143">Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="38617-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="38617-144">La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.</span><span class="sxs-lookup"><span data-stu-id="38617-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`redefine`|<span data-ttu-id="38617-145">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-145">Forbidden.</span></span> <span data-ttu-id="38617-146">El uso de `xs:redefine` se prohíbe por parte de `DataContractSerializer` por razones de seguridad: `x:redefine` requiere que se siga `schemaLocation` .</span><span class="sxs-lookup"><span data-stu-id="38617-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="38617-147">En ciertas circunstancias, el uso de DataContract por parte de Svcutil.exe restringe el uso de `schemaLocation`.</span><span class="sxs-lookup"><span data-stu-id="38617-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|
|`import`|<span data-ttu-id="38617-148">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-148">Supported.</span></span> <span data-ttu-id="38617-149">`DataContractSerializer` admite `xs:include` y `xs:import`.</span><span class="sxs-lookup"><span data-stu-id="38617-149">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="38617-150">Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="38617-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="38617-151">La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.</span><span class="sxs-lookup"><span data-stu-id="38617-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`simpleType`|<span data-ttu-id="38617-152">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-152">Supported.</span></span> <span data-ttu-id="38617-153">Vea la sección `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="38617-153">See the `xs:simpleType` section.</span></span>|
|`complexType`|<span data-ttu-id="38617-154">Admitido, se asigna a contratos de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="38617-155">Vea la sección `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="38617-155">See the `xs:complexType` section.</span></span>|
|`group`|<span data-ttu-id="38617-156">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-156">Ignored.</span></span> <span data-ttu-id="38617-157">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="38617-157">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="38617-158">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="38617-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`attributeGroup`|<span data-ttu-id="38617-159">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-159">Ignored.</span></span> <span data-ttu-id="38617-160">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="38617-160">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="38617-161">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="38617-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`element`|<span data-ttu-id="38617-162">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-162">Supported.</span></span> <span data-ttu-id="38617-163">Vea la declaración de elemento global (GED).</span><span class="sxs-lookup"><span data-stu-id="38617-163">See Global Element Declaration (GED).</span></span>|
|`attribute`|<span data-ttu-id="38617-164">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-164">Ignored.</span></span> <span data-ttu-id="38617-165">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="38617-165">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="38617-166">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="38617-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`notation`|<span data-ttu-id="38617-167">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-167">Ignored.</span></span>|

## <a name="complex-types--xscomplextype"></a><span data-ttu-id="38617-168">Tipos complejos:\<xs:complexType></span><span class="sxs-lookup"><span data-stu-id="38617-168">Complex Types – \<xs:complexType></span></span>

### <a name="general-information"></a><span data-ttu-id="38617-169">Información general</span><span class="sxs-lookup"><span data-stu-id="38617-169">General Information</span></span>

<span data-ttu-id="38617-170">Cada tipo complejo \<xs:complexType> se asigna a un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>

### <a name="xscomplextype-attributes"></a><span data-ttu-id="38617-171">\<xs:complexType>: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-171">\<xs:complexType>: attributes</span></span>

|<span data-ttu-id="38617-172">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-172">Attribute</span></span>|<span data-ttu-id="38617-173">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-173">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="38617-174">Debe ser false (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="38617-174">Must be false (default).</span></span>|
|`block`|<span data-ttu-id="38617-175">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-175">Forbidden.</span></span>|
|`final`|<span data-ttu-id="38617-176">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-176">Ignored.</span></span>|
|`id`|<span data-ttu-id="38617-177">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-177">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="38617-178">Debe ser false (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="38617-178">Must be false (default).</span></span>|
|`name`|<span data-ttu-id="38617-179">Admitido y asignado al nombre del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="38617-180">Si hay puntos en el nombre, se realiza un intento de asignar el tipo a un tipo interno.</span><span class="sxs-lookup"><span data-stu-id="38617-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="38617-181">Por ejemplo, un tipo complejo denominado `A.B` asigna a un tipo de contrato de datos que es un tipo interno de un tipo con el nombre de contrato de datos `A`, pero solo si existe este tipo de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="38617-182">Es posible más de un nivel de anidación: por ejemplo, `A.B.C` puede ser un tipo interno, pero solo si existen `A` y `A.B` .</span><span class="sxs-lookup"><span data-stu-id="38617-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|

### <a name="xscomplextype-contents"></a><span data-ttu-id="38617-183">\<xs:complexType>: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-183">\<xs:complexType>: contents</span></span>

|<span data-ttu-id="38617-184">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-184">Contents</span></span>|<span data-ttu-id="38617-185">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-185">Schema</span></span>|
|--------------|------------|
|`simpleContent`|<span data-ttu-id="38617-186">Se prohíben las extensiones.</span><span class="sxs-lookup"><span data-stu-id="38617-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="38617-187">La restricción solo se permite desde `anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="38617-187">Restriction is allowed only from `anySimpleType`.</span></span>|
|`complexContent`|<span data-ttu-id="38617-188">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-188">Supported.</span></span> <span data-ttu-id="38617-189">Vea “Herencia”.</span><span class="sxs-lookup"><span data-stu-id="38617-189">See "Inheritance".</span></span>|
|`group`|<span data-ttu-id="38617-190">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-190">Forbidden.</span></span>|
|`all`|<span data-ttu-id="38617-191">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-191">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="38617-192">Prohibido</span><span class="sxs-lookup"><span data-stu-id="38617-192">Forbidden</span></span>|
|`sequence`|<span data-ttu-id="38617-193">Admitido, asigna a los miembros de datos de un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-193">Supported, maps to data members of a data contract.</span></span>|
|`attribute`|<span data-ttu-id="38617-194">Prohibido, aun cuando uso = "prohibido" (con una excepción).</span><span class="sxs-lookup"><span data-stu-id="38617-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="38617-195">Solo se admiten los atributos opcionales del espacio de nombres del esquema de serialización estándar.</span><span class="sxs-lookup"><span data-stu-id="38617-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="38617-196">No asignan a miembros de datos en el modelo de programación del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="38617-197">Actualmente, solo un atributo de este tipo tiene significado y se trata en la sección ISerializable.</span><span class="sxs-lookup"><span data-stu-id="38617-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="38617-198">El resto se pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="38617-198">All others are ignored.</span></span>|
|`attributeGroup`|<span data-ttu-id="38617-199">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-199">Forbidden.</span></span> <span data-ttu-id="38617-200">En la versión WCF v1, `DataContractSerializer` omite la presencia de `attributeGroup` dentro de `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="38617-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|
|`anyAttribute`|<span data-ttu-id="38617-201">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-201">Forbidden.</span></span>|
|<span data-ttu-id="38617-202">(vacío)</span><span class="sxs-lookup"><span data-stu-id="38617-202">(empty)</span></span>|<span data-ttu-id="38617-203">Se asigna a un contrato de datos sin miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-203">Maps to a data contract with no data members.</span></span>|

### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="38617-204">\<xs:sequence>en un tipo complejo: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-204">\<xs:sequence> in a complex type: attributes</span></span>

|<span data-ttu-id="38617-205">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-205">Attribute</span></span>|<span data-ttu-id="38617-206">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-206">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="38617-207">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-207">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="38617-208">Debe ser 1 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="38617-208">Must be 1 (default).</span></span>|
|`minOccurs`|<span data-ttu-id="38617-209">Debe ser 1 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="38617-209">Must be 1 (default).</span></span>|

### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="38617-210">\<xs:sequence>en un tipo complejo: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-210">\<xs:sequence> in a complex type: contents</span></span>

|<span data-ttu-id="38617-211">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-211">Contents</span></span>|<span data-ttu-id="38617-212">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-212">Schema</span></span>|
|--------------|------------|
|`element`|<span data-ttu-id="38617-213">Cada instancia asigna a un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-213">Each instance maps to a data member.</span></span>|
|`group`|<span data-ttu-id="38617-214">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-214">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="38617-215">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-215">Forbidden.</span></span>|
|`sequence`|<span data-ttu-id="38617-216">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-216">Forbidden.</span></span>|
|`any`|<span data-ttu-id="38617-217">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-217">Forbidden.</span></span>|
|<span data-ttu-id="38617-218">(vacío)</span><span class="sxs-lookup"><span data-stu-id="38617-218">(empty)</span></span>|<span data-ttu-id="38617-219">Se asigna a un contrato de datos sin miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-219">Maps to a data contract with no data members.</span></span>|

## <a name="elements--xselement"></a><span data-ttu-id="38617-220">Elemento\<xs:element></span><span class="sxs-lookup"><span data-stu-id="38617-220">Elements – \<xs:element></span></span>

### <a name="general-information"></a><span data-ttu-id="38617-221">Información general</span><span class="sxs-lookup"><span data-stu-id="38617-221">General Information</span></span>

<span data-ttu-id="38617-222">`<xs:element>` puede aparecer en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="38617-222">`<xs:element>` can occur in the following contexts:</span></span>

- <span data-ttu-id="38617-223">Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos normal (no de una colección).</span><span class="sxs-lookup"><span data-stu-id="38617-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="38617-224">En este caso, el atributo `maxOccurs` debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="38617-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="38617-225">(No se permite un valor de 0).</span><span class="sxs-lookup"><span data-stu-id="38617-225">(A value of 0 is not allowed).</span></span>

- <span data-ttu-id="38617-226">Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos de colección.</span><span class="sxs-lookup"><span data-stu-id="38617-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="38617-227">En este caso, el atributo `maxOccurs` debe ser mayor que 1 o "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="38617-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>

- <span data-ttu-id="38617-228">Puede ocurrir dentro de `<xs:schema>` como una declaración de elemento global (GED).</span><span class="sxs-lookup"><span data-stu-id="38617-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="38617-229">\<xs:element>con maxOccurs = 1 dentro de \<xs:sequence> (miembros de datos)</span><span class="sxs-lookup"><span data-stu-id="38617-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>

|<span data-ttu-id="38617-230">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-230">Attribute</span></span>|<span data-ttu-id="38617-231">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-231">Schema</span></span>|
|---------------|------------|
|`ref`|<span data-ttu-id="38617-232">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-232">Forbidden.</span></span>|
|`name`|<span data-ttu-id="38617-233">Admitido, asigna al nombre del miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-233">Supported, maps to the data member name.</span></span>|
|`type`|<span data-ttu-id="38617-234">Admitido, asigna al tipo de miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="38617-235">Para obtener más información, vea Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="38617-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="38617-236">Si no se especifica (y el elemento no contiene un tipo anónimo), se supone `xs:anyType` .</span><span class="sxs-lookup"><span data-stu-id="38617-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|
|`block`|<span data-ttu-id="38617-237">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-237">Ignored.</span></span>|
|`default`|<span data-ttu-id="38617-238">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-238">Forbidden.</span></span>|
|`fixed`|<span data-ttu-id="38617-239">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-239">Forbidden.</span></span>|
|`form`|<span data-ttu-id="38617-240">Se debe calificar.</span><span class="sxs-lookup"><span data-stu-id="38617-240">Must be qualified.</span></span> <span data-ttu-id="38617-241">Este atributo se puede establecer mediante `elementFormDefault` en `xs:schema`.</span><span class="sxs-lookup"><span data-stu-id="38617-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|
|`id`|<span data-ttu-id="38617-242">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-242">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="38617-243">1</span><span class="sxs-lookup"><span data-stu-id="38617-243">1</span></span>|
|`minOccurs`|<span data-ttu-id="38617-244">Se asigna a la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> de un miembro de datos (`IsRequired` es true cuando `minOccurs` es 1).</span><span class="sxs-lookup"><span data-stu-id="38617-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|
|`nillable`|<span data-ttu-id="38617-245">Afecta a la asignación de tipo.</span><span class="sxs-lookup"><span data-stu-id="38617-245">Affects type mapping.</span></span> <span data-ttu-id="38617-246">Vea Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="38617-246">See Type/primitive mapping.</span></span>|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="38617-247">\<xs:element>con maxOccurs>1 en \<xs:sequence> (colecciones)</span><span class="sxs-lookup"><span data-stu-id="38617-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>

- <span data-ttu-id="38617-248">Asigna a un <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="38617-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>

- <span data-ttu-id="38617-249">En tipos de colección, solo se permite un xs:element dentro de un xs:sequence.</span><span class="sxs-lookup"><span data-stu-id="38617-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>

 <span data-ttu-id="38617-250">Las colecciones pueden ser de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="38617-250">Collections can be of the following types:</span></span>

- <span data-ttu-id="38617-251">Colecciones normales (por ejemplo, matrices).</span><span class="sxs-lookup"><span data-stu-id="38617-251">Regular collections (for example, arrays).</span></span>

- <span data-ttu-id="38617-252">Colecciones de diccionarios (asignan un valor a otro; por ejemplo, un <xref:System.Collections.Hashtable>).</span><span class="sxs-lookup"><span data-stu-id="38617-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>

- <span data-ttu-id="38617-253">La única diferencia entre un diccionario y una matriz de un tipo de par clave-valor está en el modelo de programación generado.</span><span class="sxs-lookup"><span data-stu-id="38617-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="38617-254">Hay un mecanismo de anotación de esquema que se puede utilizar para indicar que un tipo determinado es una colección de diccionarios.</span><span class="sxs-lookup"><span data-stu-id="38617-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>

<span data-ttu-id="38617-255">Las reglas para los atributos `ref`, `block`, `default`, `fixed`, `form`e `id` son las mismas que para el caso de que no se trate de una colección.</span><span class="sxs-lookup"><span data-stu-id="38617-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="38617-256">Entre otros atributos se incluyen los de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="38617-256">Other attributes include those in the following table.</span></span>

|<span data-ttu-id="38617-257">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-257">Attribute</span></span>|<span data-ttu-id="38617-258">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-258">Schema</span></span>|
|---------------|------------|
|`name`|<span data-ttu-id="38617-259">Admitido, asigna a la propiedad <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> en el atributo `CollectionDataContractAttribute` .</span><span class="sxs-lookup"><span data-stu-id="38617-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|
|`type`|<span data-ttu-id="38617-260">Admitido, asigna al tipo almacenado en la colección.</span><span class="sxs-lookup"><span data-stu-id="38617-260">Supported, maps to the type stored in the collection.</span></span>|
|`maxOccurs`|<span data-ttu-id="38617-261">Mayor que 1 o "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="38617-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="38617-262">El esquema de DC debería utilizar "ilimitado."</span><span class="sxs-lookup"><span data-stu-id="38617-262">The DC schema should use "unbounded".</span></span>|
|`minOccurs`|<span data-ttu-id="38617-263">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-263">Ignored.</span></span>|
|`nillable`|<span data-ttu-id="38617-264">Afecta a la asignación de tipo.</span><span class="sxs-lookup"><span data-stu-id="38617-264">Affects type mapping.</span></span> <span data-ttu-id="38617-265">Este atributo se omite para las colecciones de diccionarios.</span><span class="sxs-lookup"><span data-stu-id="38617-265">This attribute is ignored for dictionary collections.</span></span>|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="38617-266">\<xs:element>dentro de una \<xs:schema> declaración de elemento global</span><span class="sxs-lookup"><span data-stu-id="38617-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>

- <span data-ttu-id="38617-267">Una declaración de elemento global (GED) que tiene el mismo nombre y espacio de nombres que un tipo en esquema o que define un tipo anónimo dentro de sí mismo, se dice que está asociado al tipo.</span><span class="sxs-lookup"><span data-stu-id="38617-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>

- <span data-ttu-id="38617-268">Exportación del esquema: las GED asociadas se generan para cada tipo generado, tanto simple como complejo.</span><span class="sxs-lookup"><span data-stu-id="38617-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>

- <span data-ttu-id="38617-269">Deserialización/serialización: las GED asociadas se utilizan como elementos raíz para el tipo.</span><span class="sxs-lookup"><span data-stu-id="38617-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>

- <span data-ttu-id="38617-270">Importación del esquema: las GED asociadas no se requieren y se omiten si siguen las reglas siguientes (a menos que definan tipos).</span><span class="sxs-lookup"><span data-stu-id="38617-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>

|<span data-ttu-id="38617-271">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-271">Attribute</span></span>|<span data-ttu-id="38617-272">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-272">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="38617-273">Debe ser false para GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-273">Must be false for associated GEDs.</span></span>|
|`block`|<span data-ttu-id="38617-274">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-274">Forbidden in associated GEDs.</span></span>|
|`default`|<span data-ttu-id="38617-275">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-275">Forbidden in associated GEDs.</span></span>|
|`final`|<span data-ttu-id="38617-276">Debe ser false para GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-276">Must be false for associated GEDs.</span></span>|
|`fixed`|<span data-ttu-id="38617-277">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-277">Forbidden in associated GEDs.</span></span>|
|`id`|<span data-ttu-id="38617-278">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-278">Ignored.</span></span>|
|`name`|<span data-ttu-id="38617-279">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-279">Supported.</span></span> <span data-ttu-id="38617-280">Vea la definición de GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-280">See the definition of associated GEDs.</span></span>|
|`nillable`|<span data-ttu-id="38617-281">Debe ser true para las GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-281">Must be true for associated GEDs.</span></span>|
|`substitutionGroup`|<span data-ttu-id="38617-282">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="38617-282">Forbidden in associated GEDs.</span></span>|
|`type`|<span data-ttu-id="38617-283">Admitido y debe coincidir con el tipo asociado para las GED asociadas (a menos que el elemento contenga un tipo anónimo).</span><span class="sxs-lookup"><span data-stu-id="38617-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|

### <a name="xselement-contents"></a><span data-ttu-id="38617-284">\<xs:element>: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-284">\<xs:element>: contents</span></span>

|<span data-ttu-id="38617-285">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-285">Contents</span></span>|<span data-ttu-id="38617-286">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-286">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="38617-287">Admitido.\*</span><span class="sxs-lookup"><span data-stu-id="38617-287">Supported.\*</span></span>|
|`complexType`|<span data-ttu-id="38617-288">Admitido.\*</span><span class="sxs-lookup"><span data-stu-id="38617-288">Supported.\*</span></span>|
|`unique`|<span data-ttu-id="38617-289">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-289">Ignored.</span></span>|
|`key`|<span data-ttu-id="38617-290">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-290">Ignored.</span></span>|
|`keyref`|<span data-ttu-id="38617-291">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-291">Ignored.</span></span>|
|<span data-ttu-id="38617-292">(en blanco)</span><span class="sxs-lookup"><span data-stu-id="38617-292">(blank)</span></span>|<span data-ttu-id="38617-293">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-293">Supported.</span></span>|

<span data-ttu-id="38617-294">\*Cuando se usa `simpleType` la `complexType,` asignación y para tipos anónimos es igual que para los tipos no anónimos, salvo que no hay ningún contrato de datos anónimos, por lo que se crea un contrato de datos con nombre, con un nombre generado derivado del nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="38617-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="38617-295">Las reglas para los tipos anónimos están en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="38617-295">The rules for anonymous types are in the following list:</span></span>

- <span data-ttu-id="38617-296">Detalle de implementación de WCF: Si el `xs:element` nombre no contiene puntos, el tipo anónimo se asigna a un tipo interno del tipo de contrato de datos externo.</span><span class="sxs-lookup"><span data-stu-id="38617-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="38617-297">Si el nombre contiene puntos, el tipo de contrato de datos resultante es independiente (no un tipo interno).</span><span class="sxs-lookup"><span data-stu-id="38617-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>

- <span data-ttu-id="38617-298">El nombre de contrato de datos generado del tipo interno es el nombre de contrato de datos del tipo exterior seguido por un punto, el nombre del elemento, y la cadena “Type”.</span><span class="sxs-lookup"><span data-stu-id="38617-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>

- <span data-ttu-id="38617-299">Si un contrato de datos con este tipo de nombre ya existe, el nombre se hace único anexando "1", "2", "3", y así sucesivamente, hasta que se cree un nombre único.</span><span class="sxs-lookup"><span data-stu-id="38617-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>

## <a name="simple-types---xssimpletype"></a><span data-ttu-id="38617-300">Tipos simples:\<xs:simpleType></span><span class="sxs-lookup"><span data-stu-id="38617-300">Simple Types - \<xs:simpleType></span></span>

### <a name="xssimpletype-attributes"></a><span data-ttu-id="38617-301">\<xs:simpleType>: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-301">\<xs:simpleType>: attributes</span></span>

|<span data-ttu-id="38617-302">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-302">Attribute</span></span>|<span data-ttu-id="38617-303">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-303">Schema</span></span>|
|---------------|------------|
|`final`|<span data-ttu-id="38617-304">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-304">Ignored.</span></span>|
|`id`|<span data-ttu-id="38617-305">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-305">Ignored.</span></span>|
|`name`|<span data-ttu-id="38617-306">Admitido, asigna al nombre de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-306">Supported, maps to the data contract name.</span></span>|

### <a name="xssimpletype-contents"></a><span data-ttu-id="38617-307">\<xs:simpleType>: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-307">\<xs:simpleType>: contents</span></span>

|<span data-ttu-id="38617-308">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-308">Contents</span></span>|<span data-ttu-id="38617-309">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-309">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="38617-310">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-310">Supported.</span></span> <span data-ttu-id="38617-311">Asigna a contratos de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="38617-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="38617-312">Este atributo se omite si no coincide con el patrón de enumeración.</span><span class="sxs-lookup"><span data-stu-id="38617-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="38617-313">Vea la sección de restricciones de `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="38617-313">See the `xs:simpleType` restrictions section.</span></span>|
|`list`|<span data-ttu-id="38617-314">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-314">Supported.</span></span> <span data-ttu-id="38617-315">Asigna a contratos de datos de enumeración de marcas.</span><span class="sxs-lookup"><span data-stu-id="38617-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="38617-316">Vea la sección de listas de `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="38617-316">See the `xs:simpleType` lists section.</span></span>|
|`union`|<span data-ttu-id="38617-317">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-317">Forbidden.</span></span>|

### \<xs:restriction>

- <span data-ttu-id="38617-318">Las restricciones de tipos complejos solo se admiten para base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="38617-318">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>

- <span data-ttu-id="38617-319">Las restricciones de tipos simples de `xs:string` que no tienen facetas de restricciones que no sean `xs:enumeration` están asignadas a contratos de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="38617-319">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>

- <span data-ttu-id="38617-320">El resto de restricciones de tipos simples se asignan a los tipos que restringen.</span><span class="sxs-lookup"><span data-stu-id="38617-320">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="38617-321">Por ejemplo, una restricción de `xs:int` se asigna a un entero, como hace `xs:int` .</span><span class="sxs-lookup"><span data-stu-id="38617-321">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="38617-322">Para obtener más información sobre la asignación de tipos primitivos, vea asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="38617-322">For more information about primitive type mapping, see Type/primitive mapping.</span></span>

### <a name="xsrestriction-attributes"></a><span data-ttu-id="38617-323">\<xs:restriction>: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-323">\<xs:restriction>: attributes</span></span>

|<span data-ttu-id="38617-324">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-324">Attribute</span></span>|<span data-ttu-id="38617-325">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-325">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="38617-326">Debe ser un tipo simple admitido o `xs:anyType`.</span><span class="sxs-lookup"><span data-stu-id="38617-326">Must be a supported simple type or `xs:anyType`.</span></span>|
|`id`|<span data-ttu-id="38617-327">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-327">Ignored.</span></span>|

### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="38617-328">\<xs:restriction>en todos los demás casos: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-328">\<xs:restriction> for all other cases: contents</span></span>

|<span data-ttu-id="38617-329">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-329">Contents</span></span>|<span data-ttu-id="38617-330">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-330">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="38617-331">Si está presente, se debe derivar de un tipo primitivo admitido.</span><span class="sxs-lookup"><span data-stu-id="38617-331">If present, must be derived from a supported primitive type.</span></span>|
|`minExclusive`|<span data-ttu-id="38617-332">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-332">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="38617-333">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-333">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="38617-334">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-334">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="38617-335">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-335">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="38617-336">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-336">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="38617-337">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-337">Ignored.</span></span>|
|`length`|<span data-ttu-id="38617-338">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-338">Ignored.</span></span>|
|`minLength`|<span data-ttu-id="38617-339">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-339">Ignored.</span></span>|
|`maxLength`|<span data-ttu-id="38617-340">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-340">Ignored.</span></span>|
|`enumeration`|<span data-ttu-id="38617-341">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-341">Ignored.</span></span>|
|`whiteSpace`|<span data-ttu-id="38617-342">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-342">Ignored.</span></span>|
|`pattern`|<span data-ttu-id="38617-343">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-343">Ignored.</span></span>|
|<span data-ttu-id="38617-344">(en blanco)</span><span class="sxs-lookup"><span data-stu-id="38617-344">(blank)</span></span>|<span data-ttu-id="38617-345">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-345">Supported.</span></span>|

## <a name="enumeration"></a><span data-ttu-id="38617-346">Enumeración</span><span class="sxs-lookup"><span data-stu-id="38617-346">Enumeration</span></span>

### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="38617-347">\<xs:restriction>para enumeraciones: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-347">\<xs:restriction> for enumerations: attributes</span></span>

|<span data-ttu-id="38617-348">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-348">Attribute</span></span>|<span data-ttu-id="38617-349">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-349">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="38617-350">Si está presente, debe ser `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="38617-350">If present, must be `xs:string`.</span></span>|
|`id`|<span data-ttu-id="38617-351">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-351">Ignored.</span></span>|

### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="38617-352">\<xs:restriction>para enumeraciones: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-352">\<xs:restriction> for enumerations: contents</span></span>

|<span data-ttu-id="38617-353">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-353">Contents</span></span>|<span data-ttu-id="38617-354">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-354">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="38617-355">Si está presente, debe ser una restricción de enumeración admitida por el contrato de datos (esta sección).</span><span class="sxs-lookup"><span data-stu-id="38617-355">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|
|`minExclusive`|<span data-ttu-id="38617-356">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-356">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="38617-357">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-357">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="38617-358">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-358">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="38617-359">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-359">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="38617-360">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-360">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="38617-361">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-361">Ignored.</span></span>|
|`length`|<span data-ttu-id="38617-362">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-362">Forbidden.</span></span>|
|`minLength`|<span data-ttu-id="38617-363">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-363">Forbidden.</span></span>|
|`maxLength`|<span data-ttu-id="38617-364">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-364">Forbidden.</span></span>|
|`enumeration`|<span data-ttu-id="38617-365">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-365">Supported.</span></span> <span data-ttu-id="38617-366">Se omite el "id" de enumeración y "value" se asigna al nombre del valor en el contrato de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="38617-366">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|
|`whiteSpace`|<span data-ttu-id="38617-367">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-367">Forbidden.</span></span>|
|`pattern`|<span data-ttu-id="38617-368">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-368">Forbidden.</span></span>|
|<span data-ttu-id="38617-369">(vacío)</span><span class="sxs-lookup"><span data-stu-id="38617-369">(empty)</span></span>|<span data-ttu-id="38617-370">Compatible; se asigna a un tipo de enumeración vacío.</span><span class="sxs-lookup"><span data-stu-id="38617-370">Supported, maps to empty enumeration type.</span></span>|

 <span data-ttu-id="38617-371">En el siguiente código se muestra una clase de enumeración de C#.</span><span class="sxs-lookup"><span data-stu-id="38617-371">The following code shows a C# enumeration class.</span></span>

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

<span data-ttu-id="38617-372">Esta clase se asigna al esquema siguiente mediante el `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="38617-372">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="38617-373">Si los valores de la enumeración se inician en 1, no se generan bloques `xs:annotation` .</span><span class="sxs-lookup"><span data-stu-id="38617-373">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>

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

<span data-ttu-id="38617-374">El`DataContractSerializer` asigna tipos de enumeración marcados con `System.FlagsAttribute` a `xs:list` derivado de `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="38617-374">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="38617-375">No se admite ninguna otra variación de `xs:list` .</span><span class="sxs-lookup"><span data-stu-id="38617-375">No other `xs:list` variations are supported.</span></span>

### <a name="xslist-attributes"></a><span data-ttu-id="38617-376">\<xs:list>: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-376">\<xs:list>: attributes</span></span>

|<span data-ttu-id="38617-377">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-377">Attribute</span></span>|<span data-ttu-id="38617-378">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-378">Schema</span></span>|
|---------------|------------|
|`itemType`|<span data-ttu-id="38617-379">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="38617-379">Forbidden.</span></span>|
|`id`|<span data-ttu-id="38617-380">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-380">Ignored.</span></span>|

### <a name="xslist-contents"></a><span data-ttu-id="38617-381">\<xs:list>: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-381">\<xs:list>: contents</span></span>

|<span data-ttu-id="38617-382">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-382">Contents</span></span>|<span data-ttu-id="38617-383">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-383">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="38617-384">Debe ser la restricción de `xs:string` utilizando la faceta `xs:enumeration` .</span><span class="sxs-lookup"><span data-stu-id="38617-384">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|

<span data-ttu-id="38617-385">Si el valor de enumeración no sigue una progresión de potencia 2 (valor predeterminado para marcas), el valor se almacena en `xs:annotation/xs:appInfo/ser:EnumerationValue` .</span><span class="sxs-lookup"><span data-stu-id="38617-385">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>

<span data-ttu-id="38617-386">Por ejemplo, el código siguiente marca un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="38617-386">For example, the following code flags an enumeration type.</span></span>

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

<span data-ttu-id="38617-387">Este tipo asigna al esquema siguiente.</span><span class="sxs-lookup"><span data-stu-id="38617-387">This type maps to the following schema.</span></span>

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

## <a name="inheritance"></a><span data-ttu-id="38617-388">Herencia</span><span class="sxs-lookup"><span data-stu-id="38617-388">Inheritance</span></span>

### <a name="general-rules"></a><span data-ttu-id="38617-389">Reglas Generales</span><span class="sxs-lookup"><span data-stu-id="38617-389">General rules</span></span>

<span data-ttu-id="38617-390">Un contrato de datos puede heredar de otro contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-390">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="38617-391">Tales contratos de datos asignan a una base y son derivados por tipos de extensión mediante la construcción de squema XML `<xs:extension>` .</span><span class="sxs-lookup"><span data-stu-id="38617-391">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>

<span data-ttu-id="38617-392">Un contrato de datos no puede heredar de un contrato de datos de colección.</span><span class="sxs-lookup"><span data-stu-id="38617-392">A data contract cannot inherit from a collection data contract.</span></span>

<span data-ttu-id="38617-393">Por ejemplo, el código siguiente es un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-393">For example, the following code is a data contract.</span></span>

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

<span data-ttu-id="38617-394">Este contrato de datos asigna a la declaración de tipos de esquema XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="38617-394">This data contract maps to the following XML Schema type declaration.</span></span>

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

### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="38617-395">\<xs:complexContent>: atributos</span><span class="sxs-lookup"><span data-stu-id="38617-395">\<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="38617-396">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-396">Attribute</span></span>|<span data-ttu-id="38617-397">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-397">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="38617-398">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-398">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="38617-399">Debe ser false.</span><span class="sxs-lookup"><span data-stu-id="38617-399">Must be false.</span></span>|

### <a name="xscomplexcontent-contents"></a><span data-ttu-id="38617-400">\<xs:complexContent>: contenido</span><span class="sxs-lookup"><span data-stu-id="38617-400">\<xs:complexContent>: contents</span></span>

|<span data-ttu-id="38617-401">Contenido</span><span class="sxs-lookup"><span data-stu-id="38617-401">Contents</span></span>|<span data-ttu-id="38617-402">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-402">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="38617-403">Prohibido, excepto cuando base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="38617-403">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="38617-404">Lo último es equivalente a colocar directamente el contenido de `xs:restriction` bajo el contenedor de `xs:complexContent`.</span><span class="sxs-lookup"><span data-stu-id="38617-404">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|
|`extension`|<span data-ttu-id="38617-405">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-405">Supported.</span></span> <span data-ttu-id="38617-406">Asigna a la herencia del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-406">Maps to data contract inheritance.</span></span>|

### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="38617-407">\<xs:extension>en \<xs:complexContent> : atributos</span><span class="sxs-lookup"><span data-stu-id="38617-407">\<xs:extension> in \<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="38617-408">Atributo</span><span class="sxs-lookup"><span data-stu-id="38617-408">Attribute</span></span>|<span data-ttu-id="38617-409">Schema</span><span class="sxs-lookup"><span data-stu-id="38617-409">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="38617-410">ignorado.</span><span class="sxs-lookup"><span data-stu-id="38617-410">Ignored.</span></span>|
|`base`|<span data-ttu-id="38617-411">Compatible.</span><span class="sxs-lookup"><span data-stu-id="38617-411">Supported.</span></span> <span data-ttu-id="38617-412">Asigna al tipo de contrato de datos base desde el que este tipo hereda.</span><span class="sxs-lookup"><span data-stu-id="38617-412">Maps to the base data contract type that this type inherits from.</span></span>|

### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="38617-413">\<xs:extension>en \<xs:complexContent> : contenido</span><span class="sxs-lookup"><span data-stu-id="38617-413">\<xs:extension> in \<xs:complexContent>: contents</span></span>

<span data-ttu-id="38617-414">Las reglas son la mismas que para el contenido `<xs:complexType>` .</span><span class="sxs-lookup"><span data-stu-id="38617-414">The rules are the same as for `<xs:complexType>` contents.</span></span>

<span data-ttu-id="38617-415">Si se proporciona un `<xs:sequence>` , sus elementos de miembro asignan a los miembros de datos adicionales que se encuentran en el contrato de datos derivado.</span><span class="sxs-lookup"><span data-stu-id="38617-415">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>

<span data-ttu-id="38617-416">Si un tipo derivado contiene un elemento con el mismo nombre que un elemento en un tipo base, la declaración de elementos duplicados asigna a un miembro de datos con un nombre que se genera para que sea único.</span><span class="sxs-lookup"><span data-stu-id="38617-416">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="38617-417">Los números enteros positivos se suman al nombre del miembro de datos ("member1", "member2", etc.) hasta que se encuentre un nombre único.</span><span class="sxs-lookup"><span data-stu-id="38617-417">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="38617-418">De manera inversa:</span><span class="sxs-lookup"><span data-stu-id="38617-418">Conversely:</span></span>

- <span data-ttu-id="38617-419">Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre y tipo que un miembro de datos en un contrato de datos base, `DataContractSerializer` genera este elemento correspondiente en el tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="38617-419">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>

- <span data-ttu-id="38617-420">Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre que un miembro de datos en un contrato de datos base pero un tipo diferente, el `DataContractSerializer` importa un esquema con un elemento del tipo `xs:anyType` en las declaraciones de tipos base y de tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="38617-420">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="38617-421">El nombre de tipo original se conserva en `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span><span class="sxs-lookup"><span data-stu-id="38617-421">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>

<span data-ttu-id="38617-422">Ambas variaciones pueden conducir a un esquema con un modelo de contenido ambiguo, que depende del orden de los miembros de datos respectivos.</span><span class="sxs-lookup"><span data-stu-id="38617-422">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>

## <a name="typeprimitive-mapping"></a><span data-ttu-id="38617-423">Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="38617-423">Type/primitive mapping</span></span>

<span data-ttu-id="38617-424">El `DataContractSerializer` utiliza la asignación siguiente para los tipos primitivos del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="38617-424">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>

|<span data-ttu-id="38617-425">Tipo XSD</span><span class="sxs-lookup"><span data-stu-id="38617-425">XSD type</span></span>|<span data-ttu-id="38617-426">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="38617-426">.NET type</span></span>|
|--------------|---------------|
|`anyType`|<span data-ttu-id="38617-427"><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="38617-427"><xref:System.Object>.</span></span>|
|`anySimpleType`|<span data-ttu-id="38617-428"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-428"><xref:System.String>.</span></span>|
|`duration`|<span data-ttu-id="38617-429"><xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="38617-429"><xref:System.TimeSpan>.</span></span>|
|`dateTime`|<span data-ttu-id="38617-430"><xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="38617-430"><xref:System.DateTime>.</span></span>|
|`dateTimeOffset`|<span data-ttu-id="38617-431"><xref:System.DateTime> y <xref:System.TimeSpan> para el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="38617-431"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="38617-432">Vea abajo Serialización de DateTimeOffset.</span><span class="sxs-lookup"><span data-stu-id="38617-432">See DateTimeOffset Serialization below.</span></span>|
|`time`|<span data-ttu-id="38617-433"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-433"><xref:System.String>.</span></span>|
|`date`|<span data-ttu-id="38617-434"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-434"><xref:System.String>.</span></span>|
|`gYearMonth`|<span data-ttu-id="38617-435"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-435"><xref:System.String>.</span></span>|
|`gYear`|<span data-ttu-id="38617-436"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-436"><xref:System.String>.</span></span>|
|`gMonthDay`|<span data-ttu-id="38617-437"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-437"><xref:System.String>.</span></span>|
|`gDay`|<span data-ttu-id="38617-438"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-438"><xref:System.String>.</span></span>|
|`gMonth`|<span data-ttu-id="38617-439"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-439"><xref:System.String>.</span></span>|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|<span data-ttu-id="38617-440">Matriz de tipo<xref:System.Byte> .</span><span class="sxs-lookup"><span data-stu-id="38617-440"><xref:System.Byte> array.</span></span>|
|`hexBinary`|<span data-ttu-id="38617-441"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-441"><xref:System.String>.</span></span>|
|`float`|<span data-ttu-id="38617-442"><xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="38617-442"><xref:System.Single>.</span></span>|
|`double`|<span data-ttu-id="38617-443"><xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="38617-443"><xref:System.Double>.</span></span>|
|`anyURI`|<span data-ttu-id="38617-444"><xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="38617-444"><xref:System.Uri>.</span></span>|
|`QName`|<span data-ttu-id="38617-445"><xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="38617-445"><xref:System.Xml.XmlQualifiedName>.</span></span>|
|`string`|<span data-ttu-id="38617-446"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-446"><xref:System.String>.</span></span>|
|`normalizedString`|<span data-ttu-id="38617-447"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-447"><xref:System.String>.</span></span>|
|`token`|<span data-ttu-id="38617-448"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-448"><xref:System.String>.</span></span>|
|`language`|<span data-ttu-id="38617-449"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-449"><xref:System.String>.</span></span>|
|`Name`|<span data-ttu-id="38617-450"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-450"><xref:System.String>.</span></span>|
|`NCName`|<span data-ttu-id="38617-451"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-451"><xref:System.String>.</span></span>|
|`ID`|<span data-ttu-id="38617-452"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-452"><xref:System.String>.</span></span>|
|`IDREF`|<span data-ttu-id="38617-453"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-453"><xref:System.String>.</span></span>|
|`IDREFS`|<span data-ttu-id="38617-454"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-454"><xref:System.String>.</span></span>|
|`ENTITY`|<span data-ttu-id="38617-455"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-455"><xref:System.String>.</span></span>|
|`ENTITIES`|<span data-ttu-id="38617-456"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-456"><xref:System.String>.</span></span>|
|`NMTOKEN`|<span data-ttu-id="38617-457"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-457"><xref:System.String>.</span></span>|
|`NMTOKENS`|<span data-ttu-id="38617-458"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="38617-458"><xref:System.String>.</span></span>|
|`decimal`|<span data-ttu-id="38617-459"><xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="38617-459"><xref:System.Decimal>.</span></span>|
|`integer`|<span data-ttu-id="38617-460"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="38617-460"><xref:System.Int64>.</span></span>|
|`nonPositiveInteger`|<span data-ttu-id="38617-461"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="38617-461"><xref:System.Int64>.</span></span>|
|`negativeInteger`|<span data-ttu-id="38617-462"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="38617-462"><xref:System.Int64>.</span></span>|
|`long`|<span data-ttu-id="38617-463"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="38617-463"><xref:System.Int64>.</span></span>|
|`int`|<span data-ttu-id="38617-464"><xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="38617-464"><xref:System.Int32>.</span></span>|
|`short`|<span data-ttu-id="38617-465"><xref:System.Int16>.</span><span class="sxs-lookup"><span data-stu-id="38617-465"><xref:System.Int16>.</span></span>|
|`Byte`|<span data-ttu-id="38617-466"><xref:System.SByte>.</span><span class="sxs-lookup"><span data-stu-id="38617-466"><xref:System.SByte>.</span></span>|
|`nonNegativeInteger`|<span data-ttu-id="38617-467"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="38617-467"><xref:System.Int64>.</span></span>|
|`unsignedLong`|<span data-ttu-id="38617-468"><xref:System.UInt64>.</span><span class="sxs-lookup"><span data-stu-id="38617-468"><xref:System.UInt64>.</span></span>|
|`unsignedInt`|<span data-ttu-id="38617-469"><xref:System.UInt32>.</span><span class="sxs-lookup"><span data-stu-id="38617-469"><xref:System.UInt32>.</span></span>|
|`unsignedShort`|<span data-ttu-id="38617-470"><xref:System.UInt16>.</span><span class="sxs-lookup"><span data-stu-id="38617-470"><xref:System.UInt16>.</span></span>|
|`unsignedByte`|<span data-ttu-id="38617-471"><xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="38617-471"><xref:System.Byte>.</span></span>|
|`positiveInteger`|<span data-ttu-id="38617-472"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="38617-472"><xref:System.Int64>.</span></span>|

## <a name="iserializable-types-mapping"></a><span data-ttu-id="38617-473">Asignación de tipos ISerializable</span><span class="sxs-lookup"><span data-stu-id="38617-473">ISerializable types mapping</span></span>

<span data-ttu-id="38617-474">En .NET Framework versión 1,0, <xref:System.Runtime.Serialization.ISerializable> se presentó como un mecanismo general para serializar objetos para la persistencia o la transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="38617-474">In .NET Framework version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="38617-475">Hay muchos tipos de .NET Framework que implementan `ISerializable` y que pueden pasarse entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="38617-475">There are many .NET Framework types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="38617-476"><xref:System.Runtime.Serialization.DataContractSerializer> proporciona de manera natural compatibilidad para las clases `ISerializable` .</span><span class="sxs-lookup"><span data-stu-id="38617-476"><xref:System.Runtime.Serialization.DataContractSerializer> naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="38617-477">`DataContractSerializer` asigna tipos de esquema de implementación de `ISerializable` que solo difieren en cuanto al QName (nombre completo) del tipo y son colecciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="38617-477">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="38617-478">Por ejemplo, `DataContractSerializer` se asigna <xref:System.Exception> al siguiente tipo XSD en el `http://schemas.datacontract.org/2004/07/System` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="38617-478">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

<span data-ttu-id="38617-479">El atributo opcional `ser:FactoryType` opcional declarado en el esquema de serialización de contrato de datos hace referencia a una clase de generador que puede deserializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="38617-479">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="38617-480">La clase de generador debe formar parte de la colección de tipos conocidos de la instancia de `DataContractSerializer` que se está usando.</span><span class="sxs-lookup"><span data-stu-id="38617-480">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="38617-481">Para obtener más información sobre los tipos conocidos, consulte [Data Contract known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="38617-481">For more information about known types, see [Data Contract Known Types](data-contract-known-types.md).</span></span>

## <a name="datacontract-serialization-schema"></a><span data-ttu-id="38617-482">Esquema de serialización de DataContract</span><span class="sxs-lookup"><span data-stu-id="38617-482">DataContract Serialization Schema</span></span>

<span data-ttu-id="38617-483">Varios esquemas exportados por los tipos de uso, elementos y atributos del `DataContractSerializer` , desde un espacio de nombres de serialización de contrato de datos especial:</span><span class="sxs-lookup"><span data-stu-id="38617-483">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>

`http://schemas.microsoft.com/2003/10/Serialization`

<span data-ttu-id="38617-484">A continuación, se muestra una declaración de esquema de serialización de contrato de datos completa.</span><span class="sxs-lookup"><span data-stu-id="38617-484">The following is a complete Data Contract Serialization schema declaration.</span></span>

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

<span data-ttu-id="38617-485">Se debería tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38617-485">The following should be noted:</span></span>

- <span data-ttu-id="38617-486">`ser:char` se introduce para representar caracteres Unicode de tipo <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="38617-486">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>

- <span data-ttu-id="38617-487">El `valuespace` de `xs:duration` se reduce a un conjunto ordenado para que pueda asignarse a un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="38617-487">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>

- <span data-ttu-id="38617-488">`FactoryType` se utiliza en esquemas exportados a partir de tipos que se derivan de <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="38617-488">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>

## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="38617-489">Importación de esquemas no DataContract</span><span class="sxs-lookup"><span data-stu-id="38617-489">Importing non-DataContract schemas</span></span>

<span data-ttu-id="38617-490">`DataContractSerializer` tiene la opción `ImportXmlTypes` para permitir la importación de esquemas que no cumplen el perfil XSD `DataContractSerializer` (vea la propiedad <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> ).</span><span class="sxs-lookup"><span data-stu-id="38617-490">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="38617-491">Establecer esta opción en `true` habilita la aceptación de tipos de esquema no conformes y la asignación de ellos a la implementación siguiente, <xref:System.Xml.Serialization.IXmlSerializable> ajuste de una matriz de <xref:System.Xml.XmlNode> (solo difiere el nombre de la clase).</span><span class="sxs-lookup"><span data-stu-id="38617-491">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>

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

## <a name="datetimeoffset-serialization"></a><span data-ttu-id="38617-492">Serialización de DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="38617-492">DateTimeOffset Serialization</span></span>

<span data-ttu-id="38617-493"><xref:System.DateTimeOffset> no se trata como un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="38617-493">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="38617-494">En su lugar, se serializa como un elemento complejo con dos partes.</span><span class="sxs-lookup"><span data-stu-id="38617-494">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="38617-495">La primera parte representa la fecha y hora, y la segunda parte representa el desplazamiento de la fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="38617-495">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="38617-496">En el siguiente código se muestra un ejemplo de un valor DateTimeOffset serializado.</span><span class="sxs-lookup"><span data-stu-id="38617-496">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>

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

<span data-ttu-id="38617-497">El esquema es de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="38617-497">The schema is as follows.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="38617-498">Vea también</span><span class="sxs-lookup"><span data-stu-id="38617-498">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="38617-499">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="38617-499">Using Data Contracts</span></span>](using-data-contracts.md)
