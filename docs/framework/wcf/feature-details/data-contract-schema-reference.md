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
# <a name="data-contract-schema-reference"></a><span data-ttu-id="54045-103">Referencia de esquema de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="54045-103">Data Contract Schema Reference</span></span>

<span data-ttu-id="54045-104">En este tema se describe el subconjunto del esquema XML (XSD) que <xref:System.Runtime.Serialization.DataContractSerializer> usa para describir los tipos de Common Language Runtime (CLR) para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="54045-104">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>

## <a name="datacontractserializer-mappings"></a><span data-ttu-id="54045-105">Asignaciones de DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="54045-105">DataContractSerializer Mappings</span></span>

<span data-ttu-id="54045-106">`DataContractSerializer`Asigna los tipos CLR a XSD cuando los metadatos se exportan desde un servicio de Windows Communication Foundation (WCF) mediante un punto de conexión de metadatos o la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="54045-106">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="54045-107">Para obtener más información, vea [serializador de contrato de datos](data-contract-serializer.md).</span><span class="sxs-lookup"><span data-stu-id="54045-107">For more information, see [Data Contract Serializer](data-contract-serializer.md).</span></span>

<span data-ttu-id="54045-108">El `DataContractSerializer` también asigna XSD a tipos de CLR cuando Svcutil.exe se utiliza para tener acceso al lenguaje de descripción de servicios Web (WSDL) o documentos XSD y para generar contratos de datos para servicios o clientes.</span><span class="sxs-lookup"><span data-stu-id="54045-108">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>

<span data-ttu-id="54045-109">Solo las instancias de esquema XML que cumplen los requisitos mencionados en este documento pueden asignarse a tipos de CLR utilizando `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="54045-109">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>

### <a name="support-levels"></a><span data-ttu-id="54045-110">Niveles de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="54045-110">Support Levels</span></span>

<span data-ttu-id="54045-111">El `DataContractSerializer` proporciona los niveles siguientes de compatibilidad para una característica de esquema XML determinada:</span><span class="sxs-lookup"><span data-stu-id="54045-111">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>

- <span data-ttu-id="54045-112">**Admitido**.</span><span class="sxs-lookup"><span data-stu-id="54045-112">**Supported**.</span></span> <span data-ttu-id="54045-113">Hay asignación explícita desde esta característica a tipos o atributos CLR (o a ambos) mediante `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="54045-113">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>

- <span data-ttu-id="54045-114">Se **omite**.</span><span class="sxs-lookup"><span data-stu-id="54045-114">**Ignored**.</span></span> <span data-ttu-id="54045-115">La característica se permite en esquemas importados por el `DataContractSerializer`, pero no tiene ningún efecto sobre la generación de código.</span><span class="sxs-lookup"><span data-stu-id="54045-115">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>

- <span data-ttu-id="54045-116">**Prohibido**.</span><span class="sxs-lookup"><span data-stu-id="54045-116">**Forbidden**.</span></span> <span data-ttu-id="54045-117">El `DataContractSerializer` no permite importar un esquema mediante la característica.</span><span class="sxs-lookup"><span data-stu-id="54045-117">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="54045-118">Por ejemplo, Svcutil.exe, al obtener acceso a un WSDL con un esquema que utiliza esta característica, vuelve a utilizar el <xref:System.Xml.Serialization.XmlSerializer> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="54045-118">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="54045-119">Esto se aplica de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54045-119">This is by default.</span></span>

## <a name="general-information"></a><span data-ttu-id="54045-120">Información general</span><span class="sxs-lookup"><span data-stu-id="54045-120">General Information</span></span>

- <span data-ttu-id="54045-121">El espacio de nombres del esquema se describe en [Esquema XML](https://www.w3.org/2001/XMLSchema).</span><span class="sxs-lookup"><span data-stu-id="54045-121">The schema namespace is described at [XML Schema](https://www.w3.org/2001/XMLSchema).</span></span> <span data-ttu-id="54045-122">El prefijo "xs" se utiliza en este documento.</span><span class="sxs-lookup"><span data-stu-id="54045-122">The prefix "xs" is used in this document.</span></span>

- <span data-ttu-id="54045-123">Cualquier atributo con un espacio de nombres que no sea del esquema Se ignora.</span><span class="sxs-lookup"><span data-stu-id="54045-123">Any attributes with a non-schema namespace are ignored.</span></span>

- <span data-ttu-id="54045-124">Se omite cualquier anotación (excepto aquellas descritas en este documento).</span><span class="sxs-lookup"><span data-stu-id="54045-124">Any annotations (except for those described in this document) are ignored.</span></span>

### <a name="xsschema-attributes"></a><span data-ttu-id="54045-125">\<xs:schema>: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-125">\<xs:schema>: attributes</span></span>

|<span data-ttu-id="54045-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-126">Attribute</span></span>|<span data-ttu-id="54045-127">DataContract</span><span class="sxs-lookup"><span data-stu-id="54045-127">DataContract</span></span>|
|---------------|------------------|
|`attributeFormDefault`|<span data-ttu-id="54045-128">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-128">Ignored.</span></span>|
|`blockDefault`|<span data-ttu-id="54045-129">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-129">Ignored.</span></span>|
|`elementFormDefault`|<span data-ttu-id="54045-130">Se debe calificar.</span><span class="sxs-lookup"><span data-stu-id="54045-130">Must be qualified.</span></span> <span data-ttu-id="54045-131">Todos los elementos se deben calificar para un esquema para que `DataContractSerializer`los admita.</span><span class="sxs-lookup"><span data-stu-id="54045-131">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="54045-132">Esto puede realizarse si se establece en xs:schema/@elementFormDefault "Qualified" o se establece xs:element/@form en "Qualified" en cada declaración de elemento individual.</span><span class="sxs-lookup"><span data-stu-id="54045-132">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|
|`finalDefault`|<span data-ttu-id="54045-133">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-133">Ignored.</span></span>|
|`Id`|<span data-ttu-id="54045-134">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-134">Ignored.</span></span>|
|`targetNamespace`|<span data-ttu-id="54045-135">Admitido y asignado al espacio de nombres del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-135">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="54045-136">Si no se especifica este atributo, se utiliza el espacio de nombres en blanco.</span><span class="sxs-lookup"><span data-stu-id="54045-136">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="54045-137">No puede ser el espacio de nombres reservado `http://schemas.microsoft.com/2003/10/Serialization/` .</span><span class="sxs-lookup"><span data-stu-id="54045-137">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|
|`version`|<span data-ttu-id="54045-138">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-138">Ignored.</span></span>|

### <a name="xsschema-contents"></a><span data-ttu-id="54045-139">\<xs:schema>: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-139">\<xs:schema>: contents</span></span>

|<span data-ttu-id="54045-140">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-140">Contents</span></span>|<span data-ttu-id="54045-141">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-141">Schema</span></span>|
|--------------|------------|
|`include`|<span data-ttu-id="54045-142">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-142">Supported.</span></span> <span data-ttu-id="54045-143">`DataContractSerializer` admite xs:include y xs:import.</span><span class="sxs-lookup"><span data-stu-id="54045-143">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="54045-144">Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="54045-144">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="54045-145">La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.</span><span class="sxs-lookup"><span data-stu-id="54045-145">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`redefine`|<span data-ttu-id="54045-146">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-146">Forbidden.</span></span> <span data-ttu-id="54045-147">El uso de `xs:redefine` se prohíbe por parte de `DataContractSerializer` por razones de seguridad: `x:redefine` requiere que se siga `schemaLocation` .</span><span class="sxs-lookup"><span data-stu-id="54045-147">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="54045-148">En ciertas circunstancias, el uso de DataContract por parte de Svcutil.exe restringe el uso de `schemaLocation`.</span><span class="sxs-lookup"><span data-stu-id="54045-148">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|
|`import`|<span data-ttu-id="54045-149">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-149">Supported.</span></span> <span data-ttu-id="54045-150">`DataContractSerializer` admite `xs:include` y `xs:import`.</span><span class="sxs-lookup"><span data-stu-id="54045-150">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="54045-151">Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="54045-151">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="54045-152">La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.</span><span class="sxs-lookup"><span data-stu-id="54045-152">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`simpleType`|<span data-ttu-id="54045-153">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-153">Supported.</span></span> <span data-ttu-id="54045-154">Vea la sección `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="54045-154">See the `xs:simpleType` section.</span></span>|
|`complexType`|<span data-ttu-id="54045-155">Admitido, se asigna a contratos de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-155">Supported, maps to data contracts.</span></span> <span data-ttu-id="54045-156">Vea la sección `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="54045-156">See the `xs:complexType` section.</span></span>|
|`group`|<span data-ttu-id="54045-157">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-157">Ignored.</span></span> <span data-ttu-id="54045-158">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="54045-158">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="54045-159">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="54045-159">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`attributeGroup`|<span data-ttu-id="54045-160">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-160">Ignored.</span></span> <span data-ttu-id="54045-161">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="54045-161">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="54045-162">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="54045-162">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`element`|<span data-ttu-id="54045-163">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-163">Supported.</span></span> <span data-ttu-id="54045-164">Vea la declaración de elemento global (GED).</span><span class="sxs-lookup"><span data-stu-id="54045-164">See Global Element Declaration (GED).</span></span>|
|`attribute`|<span data-ttu-id="54045-165">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-165">Ignored.</span></span> <span data-ttu-id="54045-166">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="54045-166">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="54045-167">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="54045-167">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`notation`|<span data-ttu-id="54045-168">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-168">Ignored.</span></span>|

## <a name="complex-types--xscomplextype"></a><span data-ttu-id="54045-169">Tipos complejos: \<xs:complexType></span><span class="sxs-lookup"><span data-stu-id="54045-169">Complex Types – \<xs:complexType></span></span>

### <a name="general-information"></a><span data-ttu-id="54045-170">Información general</span><span class="sxs-lookup"><span data-stu-id="54045-170">General Information</span></span>

<span data-ttu-id="54045-171">Cada tipo complejo \<xs:complexType> se asigna a un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-171">Each complex type \<xs:complexType> maps to a data contract.</span></span>

### <a name="xscomplextype-attributes"></a><span data-ttu-id="54045-172">\<xs:complexType>: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-172">\<xs:complexType>: attributes</span></span>

|<span data-ttu-id="54045-173">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-173">Attribute</span></span>|<span data-ttu-id="54045-174">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-174">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="54045-175">Debe ser false (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="54045-175">Must be false (default).</span></span>|
|`block`|<span data-ttu-id="54045-176">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-176">Forbidden.</span></span>|
|`final`|<span data-ttu-id="54045-177">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-177">Ignored.</span></span>|
|`id`|<span data-ttu-id="54045-178">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-178">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="54045-179">Debe ser false (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="54045-179">Must be false (default).</span></span>|
|`name`|<span data-ttu-id="54045-180">Admitido y asignado al nombre del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-180">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="54045-181">Si hay puntos en el nombre, se realiza un intento de asignar el tipo a un tipo interno.</span><span class="sxs-lookup"><span data-stu-id="54045-181">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="54045-182">Por ejemplo, un tipo complejo denominado `A.B` asigna a un tipo de contrato de datos que es un tipo interno de un tipo con el nombre de contrato de datos `A`, pero solo si existe este tipo de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-182">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="54045-183">Es posible más de un nivel de anidación: por ejemplo, `A.B.C` puede ser un tipo interno, pero solo si existen `A` y `A.B` .</span><span class="sxs-lookup"><span data-stu-id="54045-183">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|

### <a name="xscomplextype-contents"></a><span data-ttu-id="54045-184">\<xs:complexType>: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-184">\<xs:complexType>: contents</span></span>

|<span data-ttu-id="54045-185">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-185">Contents</span></span>|<span data-ttu-id="54045-186">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-186">Schema</span></span>|
|--------------|------------|
|`simpleContent`|<span data-ttu-id="54045-187">Se prohíben las extensiones.</span><span class="sxs-lookup"><span data-stu-id="54045-187">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="54045-188">La restricción solo se permite desde `anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="54045-188">Restriction is allowed only from `anySimpleType`.</span></span>|
|`complexContent`|<span data-ttu-id="54045-189">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-189">Supported.</span></span> <span data-ttu-id="54045-190">Vea “Herencia”.</span><span class="sxs-lookup"><span data-stu-id="54045-190">See "Inheritance".</span></span>|
|`group`|<span data-ttu-id="54045-191">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-191">Forbidden.</span></span>|
|`all`|<span data-ttu-id="54045-192">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-192">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="54045-193">Prohibido</span><span class="sxs-lookup"><span data-stu-id="54045-193">Forbidden</span></span>|
|`sequence`|<span data-ttu-id="54045-194">Admitido, asigna a los miembros de datos de un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-194">Supported, maps to data members of a data contract.</span></span>|
|`attribute`|<span data-ttu-id="54045-195">Prohibido, aun cuando uso = "prohibido" (con una excepción).</span><span class="sxs-lookup"><span data-stu-id="54045-195">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="54045-196">Solo se admiten los atributos opcionales del espacio de nombres del esquema de serialización estándar.</span><span class="sxs-lookup"><span data-stu-id="54045-196">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="54045-197">No asignan a miembros de datos en el modelo de programación del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-197">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="54045-198">Actualmente, solo un atributo de este tipo tiene significado y se trata en la sección ISerializable.</span><span class="sxs-lookup"><span data-stu-id="54045-198">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="54045-199">El resto se pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="54045-199">All others are ignored.</span></span>|
|`attributeGroup`|<span data-ttu-id="54045-200">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-200">Forbidden.</span></span> <span data-ttu-id="54045-201">En la versión WCF v1, `DataContractSerializer` omite la presencia de `attributeGroup` dentro de `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="54045-201">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|
|`anyAttribute`|<span data-ttu-id="54045-202">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-202">Forbidden.</span></span>|
|<span data-ttu-id="54045-203">(vacío)</span><span class="sxs-lookup"><span data-stu-id="54045-203">(empty)</span></span>|<span data-ttu-id="54045-204">Se asigna a un contrato de datos sin miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-204">Maps to a data contract with no data members.</span></span>|

### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="54045-205">\<xs:sequence> en un tipo complejo: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-205">\<xs:sequence> in a complex type: attributes</span></span>

|<span data-ttu-id="54045-206">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-206">Attribute</span></span>|<span data-ttu-id="54045-207">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-207">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="54045-208">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-208">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="54045-209">Debe ser 1 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="54045-209">Must be 1 (default).</span></span>|
|`minOccurs`|<span data-ttu-id="54045-210">Debe ser 1 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="54045-210">Must be 1 (default).</span></span>|

### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="54045-211">\<xs:sequence> en un tipo complejo: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-211">\<xs:sequence> in a complex type: contents</span></span>

|<span data-ttu-id="54045-212">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-212">Contents</span></span>|<span data-ttu-id="54045-213">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-213">Schema</span></span>|
|--------------|------------|
|`element`|<span data-ttu-id="54045-214">Cada instancia asigna a un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-214">Each instance maps to a data member.</span></span>|
|`group`|<span data-ttu-id="54045-215">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-215">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="54045-216">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-216">Forbidden.</span></span>|
|`sequence`|<span data-ttu-id="54045-217">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-217">Forbidden.</span></span>|
|`any`|<span data-ttu-id="54045-218">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-218">Forbidden.</span></span>|
|<span data-ttu-id="54045-219">(vacío)</span><span class="sxs-lookup"><span data-stu-id="54045-219">(empty)</span></span>|<span data-ttu-id="54045-220">Se asigna a un contrato de datos sin miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-220">Maps to a data contract with no data members.</span></span>|

## <a name="elements--xselement"></a><span data-ttu-id="54045-221">Elemento \<xs:element></span><span class="sxs-lookup"><span data-stu-id="54045-221">Elements – \<xs:element></span></span>

### <a name="general-information"></a><span data-ttu-id="54045-222">Información general</span><span class="sxs-lookup"><span data-stu-id="54045-222">General Information</span></span>

<span data-ttu-id="54045-223">`<xs:element>` puede aparecer en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="54045-223">`<xs:element>` can occur in the following contexts:</span></span>

- <span data-ttu-id="54045-224">Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos normal (no de una colección).</span><span class="sxs-lookup"><span data-stu-id="54045-224">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="54045-225">En este caso, el atributo `maxOccurs` debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="54045-225">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="54045-226">(No se permite un valor de 0).</span><span class="sxs-lookup"><span data-stu-id="54045-226">(A value of 0 is not allowed).</span></span>

- <span data-ttu-id="54045-227">Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos de colección.</span><span class="sxs-lookup"><span data-stu-id="54045-227">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="54045-228">En este caso, el atributo `maxOccurs` debe ser mayor que 1 o "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="54045-228">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>

- <span data-ttu-id="54045-229">Puede ocurrir dentro de `<xs:schema>` como una declaración de elemento global (GED).</span><span class="sxs-lookup"><span data-stu-id="54045-229">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="54045-230">\<xs:element> con maxOccurs = 1 dentro de \<xs:sequence> (miembros de datos)</span><span class="sxs-lookup"><span data-stu-id="54045-230">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>

|<span data-ttu-id="54045-231">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-231">Attribute</span></span>|<span data-ttu-id="54045-232">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-232">Schema</span></span>|
|---------------|------------|
|`ref`|<span data-ttu-id="54045-233">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-233">Forbidden.</span></span>|
|`name`|<span data-ttu-id="54045-234">Admitido, asigna al nombre del miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-234">Supported, maps to the data member name.</span></span>|
|`type`|<span data-ttu-id="54045-235">Admitido, asigna al tipo de miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-235">Supported, maps to the data member type.</span></span> <span data-ttu-id="54045-236">Para obtener más información, vea Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="54045-236">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="54045-237">Si no se especifica (y el elemento no contiene un tipo anónimo), se supone `xs:anyType` .</span><span class="sxs-lookup"><span data-stu-id="54045-237">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|
|`block`|<span data-ttu-id="54045-238">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-238">Ignored.</span></span>|
|`default`|<span data-ttu-id="54045-239">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-239">Forbidden.</span></span>|
|`fixed`|<span data-ttu-id="54045-240">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-240">Forbidden.</span></span>|
|`form`|<span data-ttu-id="54045-241">Se debe calificar.</span><span class="sxs-lookup"><span data-stu-id="54045-241">Must be qualified.</span></span> <span data-ttu-id="54045-242">Este atributo se puede establecer mediante `elementFormDefault` en `xs:schema`.</span><span class="sxs-lookup"><span data-stu-id="54045-242">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|
|`id`|<span data-ttu-id="54045-243">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-243">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="54045-244">1</span><span class="sxs-lookup"><span data-stu-id="54045-244">1</span></span>|
|`minOccurs`|<span data-ttu-id="54045-245">Se asigna a la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> de un miembro de datos (`IsRequired` es true cuando `minOccurs` es 1).</span><span class="sxs-lookup"><span data-stu-id="54045-245">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|
|`nillable`|<span data-ttu-id="54045-246">Afecta a la asignación de tipo.</span><span class="sxs-lookup"><span data-stu-id="54045-246">Affects type mapping.</span></span> <span data-ttu-id="54045-247">Vea Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="54045-247">See Type/primitive mapping.</span></span>|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="54045-248">\<xs:element> con maxOccurs>1 en \<xs:sequence> (colecciones)</span><span class="sxs-lookup"><span data-stu-id="54045-248">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>

- <span data-ttu-id="54045-249">Asigna a un <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="54045-249">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>

- <span data-ttu-id="54045-250">En tipos de colección, solo se permite un xs:element dentro de un xs:sequence.</span><span class="sxs-lookup"><span data-stu-id="54045-250">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>

 <span data-ttu-id="54045-251">Las colecciones pueden ser de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="54045-251">Collections can be of the following types:</span></span>

- <span data-ttu-id="54045-252">Colecciones normales (por ejemplo, matrices).</span><span class="sxs-lookup"><span data-stu-id="54045-252">Regular collections (for example, arrays).</span></span>

- <span data-ttu-id="54045-253">Colecciones de diccionarios (asignan un valor a otro; por ejemplo, un <xref:System.Collections.Hashtable>).</span><span class="sxs-lookup"><span data-stu-id="54045-253">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>

- <span data-ttu-id="54045-254">La única diferencia entre un diccionario y una matriz de un tipo de par clave-valor está en el modelo de programación generado.</span><span class="sxs-lookup"><span data-stu-id="54045-254">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="54045-255">Hay un mecanismo de anotación de esquema que se puede utilizar para indicar que un tipo determinado es una colección de diccionarios.</span><span class="sxs-lookup"><span data-stu-id="54045-255">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>

<span data-ttu-id="54045-256">Las reglas para los atributos `ref`, `block`, `default`, `fixed`, `form`e `id` son las mismas que para el caso de que no se trate de una colección.</span><span class="sxs-lookup"><span data-stu-id="54045-256">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="54045-257">Entre otros atributos se incluyen los de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="54045-257">Other attributes include those in the following table.</span></span>

|<span data-ttu-id="54045-258">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-258">Attribute</span></span>|<span data-ttu-id="54045-259">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-259">Schema</span></span>|
|---------------|------------|
|`name`|<span data-ttu-id="54045-260">Admitido, asigna a la propiedad <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> en el atributo `CollectionDataContractAttribute` .</span><span class="sxs-lookup"><span data-stu-id="54045-260">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|
|`type`|<span data-ttu-id="54045-261">Admitido, asigna al tipo almacenado en la colección.</span><span class="sxs-lookup"><span data-stu-id="54045-261">Supported, maps to the type stored in the collection.</span></span>|
|`maxOccurs`|<span data-ttu-id="54045-262">Mayor que 1 o "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="54045-262">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="54045-263">El esquema de DC debería utilizar "ilimitado."</span><span class="sxs-lookup"><span data-stu-id="54045-263">The DC schema should use "unbounded".</span></span>|
|`minOccurs`|<span data-ttu-id="54045-264">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-264">Ignored.</span></span>|
|`nillable`|<span data-ttu-id="54045-265">Afecta a la asignación de tipo.</span><span class="sxs-lookup"><span data-stu-id="54045-265">Affects type mapping.</span></span> <span data-ttu-id="54045-266">Este atributo se omite para las colecciones de diccionarios.</span><span class="sxs-lookup"><span data-stu-id="54045-266">This attribute is ignored for dictionary collections.</span></span>|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="54045-267">\<xs:element> dentro de una \<xs:schema> declaración de elemento global</span><span class="sxs-lookup"><span data-stu-id="54045-267">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>

- <span data-ttu-id="54045-268">Una declaración de elemento global (GED) que tiene el mismo nombre y espacio de nombres que un tipo en esquema o que define un tipo anónimo dentro de sí mismo, se dice que está asociado al tipo.</span><span class="sxs-lookup"><span data-stu-id="54045-268">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>

- <span data-ttu-id="54045-269">Exportación del esquema: las GED asociadas se generan para cada tipo generado, tanto simple como complejo.</span><span class="sxs-lookup"><span data-stu-id="54045-269">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>

- <span data-ttu-id="54045-270">Deserialización/serialización: las GED asociadas se utilizan como elementos raíz para el tipo.</span><span class="sxs-lookup"><span data-stu-id="54045-270">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>

- <span data-ttu-id="54045-271">Importación del esquema: las GED asociadas no se requieren y se omiten si siguen las reglas siguientes (a menos que definan tipos).</span><span class="sxs-lookup"><span data-stu-id="54045-271">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>

|<span data-ttu-id="54045-272">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-272">Attribute</span></span>|<span data-ttu-id="54045-273">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-273">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="54045-274">Debe ser false para GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-274">Must be false for associated GEDs.</span></span>|
|`block`|<span data-ttu-id="54045-275">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-275">Forbidden in associated GEDs.</span></span>|
|`default`|<span data-ttu-id="54045-276">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-276">Forbidden in associated GEDs.</span></span>|
|`final`|<span data-ttu-id="54045-277">Debe ser false para GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-277">Must be false for associated GEDs.</span></span>|
|`fixed`|<span data-ttu-id="54045-278">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-278">Forbidden in associated GEDs.</span></span>|
|`id`|<span data-ttu-id="54045-279">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-279">Ignored.</span></span>|
|`name`|<span data-ttu-id="54045-280">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-280">Supported.</span></span> <span data-ttu-id="54045-281">Vea la definición de GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-281">See the definition of associated GEDs.</span></span>|
|`nillable`|<span data-ttu-id="54045-282">Debe ser true para las GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-282">Must be true for associated GEDs.</span></span>|
|`substitutionGroup`|<span data-ttu-id="54045-283">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="54045-283">Forbidden in associated GEDs.</span></span>|
|`type`|<span data-ttu-id="54045-284">Admitido y debe coincidir con el tipo asociado para las GED asociadas (a menos que el elemento contenga un tipo anónimo).</span><span class="sxs-lookup"><span data-stu-id="54045-284">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|

### <a name="xselement-contents"></a><span data-ttu-id="54045-285">\<xs:element>: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-285">\<xs:element>: contents</span></span>

|<span data-ttu-id="54045-286">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-286">Contents</span></span>|<span data-ttu-id="54045-287">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-287">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="54045-288">Admitido.\*</span><span class="sxs-lookup"><span data-stu-id="54045-288">Supported.\*</span></span>|
|`complexType`|<span data-ttu-id="54045-289">Admitido.\*</span><span class="sxs-lookup"><span data-stu-id="54045-289">Supported.\*</span></span>|
|`unique`|<span data-ttu-id="54045-290">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-290">Ignored.</span></span>|
|`key`|<span data-ttu-id="54045-291">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-291">Ignored.</span></span>|
|`keyref`|<span data-ttu-id="54045-292">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-292">Ignored.</span></span>|
|<span data-ttu-id="54045-293">(en blanco)</span><span class="sxs-lookup"><span data-stu-id="54045-293">(blank)</span></span>|<span data-ttu-id="54045-294">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-294">Supported.</span></span>|

<span data-ttu-id="54045-295">\* Cuando se usa `simpleType` la `complexType,` asignación y para tipos anónimos es igual que para los tipos no anónimos, salvo que no hay ningún contrato de datos anónimos, por lo que se crea un contrato de datos con nombre, con un nombre generado derivado del nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="54045-295">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="54045-296">Las reglas para los tipos anónimos están en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="54045-296">The rules for anonymous types are in the following list:</span></span>

- <span data-ttu-id="54045-297">Detalle de implementación de WCF: Si el `xs:element` nombre no contiene puntos, el tipo anónimo se asigna a un tipo interno del tipo de contrato de datos externo.</span><span class="sxs-lookup"><span data-stu-id="54045-297">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="54045-298">Si el nombre contiene puntos, el tipo de contrato de datos resultante es independiente (no un tipo interno).</span><span class="sxs-lookup"><span data-stu-id="54045-298">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>

- <span data-ttu-id="54045-299">El nombre de contrato de datos generado del tipo interno es el nombre de contrato de datos del tipo exterior seguido por un punto, el nombre del elemento, y la cadena “Type”.</span><span class="sxs-lookup"><span data-stu-id="54045-299">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>

- <span data-ttu-id="54045-300">Si un contrato de datos con este tipo de nombre ya existe, el nombre se hace único anexando "1", "2", "3", y así sucesivamente, hasta que se cree un nombre único.</span><span class="sxs-lookup"><span data-stu-id="54045-300">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>

## <a name="simple-types---xssimpletype"></a><span data-ttu-id="54045-301">Tipos simples: \<xs:simpleType></span><span class="sxs-lookup"><span data-stu-id="54045-301">Simple Types - \<xs:simpleType></span></span>

### <a name="xssimpletype-attributes"></a><span data-ttu-id="54045-302">\<xs:simpleType>: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-302">\<xs:simpleType>: attributes</span></span>

|<span data-ttu-id="54045-303">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-303">Attribute</span></span>|<span data-ttu-id="54045-304">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-304">Schema</span></span>|
|---------------|------------|
|`final`|<span data-ttu-id="54045-305">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-305">Ignored.</span></span>|
|`id`|<span data-ttu-id="54045-306">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-306">Ignored.</span></span>|
|`name`|<span data-ttu-id="54045-307">Admitido, asigna al nombre de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-307">Supported, maps to the data contract name.</span></span>|

### <a name="xssimpletype-contents"></a><span data-ttu-id="54045-308">\<xs:simpleType>: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-308">\<xs:simpleType>: contents</span></span>

|<span data-ttu-id="54045-309">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-309">Contents</span></span>|<span data-ttu-id="54045-310">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-310">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="54045-311">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-311">Supported.</span></span> <span data-ttu-id="54045-312">Asigna a contratos de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="54045-312">Maps to enumeration data contracts.</span></span> <span data-ttu-id="54045-313">Este atributo se omite si no coincide con el patrón de enumeración.</span><span class="sxs-lookup"><span data-stu-id="54045-313">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="54045-314">Vea la sección de restricciones de `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="54045-314">See the `xs:simpleType` restrictions section.</span></span>|
|`list`|<span data-ttu-id="54045-315">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-315">Supported.</span></span> <span data-ttu-id="54045-316">Asigna a contratos de datos de enumeración de marcas.</span><span class="sxs-lookup"><span data-stu-id="54045-316">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="54045-317">Vea la sección de listas de `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="54045-317">See the `xs:simpleType` lists section.</span></span>|
|`union`|<span data-ttu-id="54045-318">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-318">Forbidden.</span></span>|

### \<xs:restriction>

- <span data-ttu-id="54045-319">Las restricciones de tipos complejos solo se admiten para base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="54045-319">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>

- <span data-ttu-id="54045-320">Las restricciones de tipos simples de `xs:string` que no tienen facetas de restricciones que no sean `xs:enumeration` están asignadas a contratos de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="54045-320">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>

- <span data-ttu-id="54045-321">El resto de restricciones de tipos simples se asignan a los tipos que restringen.</span><span class="sxs-lookup"><span data-stu-id="54045-321">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="54045-322">Por ejemplo, una restricción de `xs:int` se asigna a un entero, como hace `xs:int` .</span><span class="sxs-lookup"><span data-stu-id="54045-322">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="54045-323">Para obtener más información sobre la asignación de tipos primitivos, vea asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="54045-323">For more information about primitive type mapping, see Type/primitive mapping.</span></span>

### <a name="xsrestriction-attributes"></a><span data-ttu-id="54045-324">\<xs:restriction>: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-324">\<xs:restriction>: attributes</span></span>

|<span data-ttu-id="54045-325">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-325">Attribute</span></span>|<span data-ttu-id="54045-326">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-326">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="54045-327">Debe ser un tipo simple admitido o `xs:anyType`.</span><span class="sxs-lookup"><span data-stu-id="54045-327">Must be a supported simple type or `xs:anyType`.</span></span>|
|`id`|<span data-ttu-id="54045-328">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-328">Ignored.</span></span>|

### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="54045-329">\<xs:restriction> en todos los demás casos: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-329">\<xs:restriction> for all other cases: contents</span></span>

|<span data-ttu-id="54045-330">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-330">Contents</span></span>|<span data-ttu-id="54045-331">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-331">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="54045-332">Si está presente, se debe derivar de un tipo primitivo admitido.</span><span class="sxs-lookup"><span data-stu-id="54045-332">If present, must be derived from a supported primitive type.</span></span>|
|`minExclusive`|<span data-ttu-id="54045-333">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-333">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="54045-334">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-334">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="54045-335">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-335">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="54045-336">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-336">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="54045-337">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-337">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="54045-338">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-338">Ignored.</span></span>|
|`length`|<span data-ttu-id="54045-339">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-339">Ignored.</span></span>|
|`minLength`|<span data-ttu-id="54045-340">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-340">Ignored.</span></span>|
|`maxLength`|<span data-ttu-id="54045-341">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-341">Ignored.</span></span>|
|`enumeration`|<span data-ttu-id="54045-342">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-342">Ignored.</span></span>|
|`whiteSpace`|<span data-ttu-id="54045-343">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-343">Ignored.</span></span>|
|`pattern`|<span data-ttu-id="54045-344">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-344">Ignored.</span></span>|
|<span data-ttu-id="54045-345">(en blanco)</span><span class="sxs-lookup"><span data-stu-id="54045-345">(blank)</span></span>|<span data-ttu-id="54045-346">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-346">Supported.</span></span>|

## <a name="enumeration"></a><span data-ttu-id="54045-347">Enumeración</span><span class="sxs-lookup"><span data-stu-id="54045-347">Enumeration</span></span>

### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="54045-348">\<xs:restriction> para enumeraciones: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-348">\<xs:restriction> for enumerations: attributes</span></span>

|<span data-ttu-id="54045-349">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-349">Attribute</span></span>|<span data-ttu-id="54045-350">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-350">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="54045-351">Si está presente, debe ser `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="54045-351">If present, must be `xs:string`.</span></span>|
|`id`|<span data-ttu-id="54045-352">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-352">Ignored.</span></span>|

### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="54045-353">\<xs:restriction> para enumeraciones: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-353">\<xs:restriction> for enumerations: contents</span></span>

|<span data-ttu-id="54045-354">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-354">Contents</span></span>|<span data-ttu-id="54045-355">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-355">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="54045-356">Si está presente, debe ser una restricción de enumeración admitida por el contrato de datos (esta sección).</span><span class="sxs-lookup"><span data-stu-id="54045-356">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|
|`minExclusive`|<span data-ttu-id="54045-357">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-357">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="54045-358">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-358">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="54045-359">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-359">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="54045-360">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-360">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="54045-361">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-361">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="54045-362">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-362">Ignored.</span></span>|
|`length`|<span data-ttu-id="54045-363">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-363">Forbidden.</span></span>|
|`minLength`|<span data-ttu-id="54045-364">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-364">Forbidden.</span></span>|
|`maxLength`|<span data-ttu-id="54045-365">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-365">Forbidden.</span></span>|
|`enumeration`|<span data-ttu-id="54045-366">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-366">Supported.</span></span> <span data-ttu-id="54045-367">Se omite el "id" de enumeración y "value" se asigna al nombre del valor en el contrato de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="54045-367">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|
|`whiteSpace`|<span data-ttu-id="54045-368">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-368">Forbidden.</span></span>|
|`pattern`|<span data-ttu-id="54045-369">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-369">Forbidden.</span></span>|
|<span data-ttu-id="54045-370">(vacío)</span><span class="sxs-lookup"><span data-stu-id="54045-370">(empty)</span></span>|<span data-ttu-id="54045-371">Compatible; se asigna a un tipo de enumeración vacío.</span><span class="sxs-lookup"><span data-stu-id="54045-371">Supported, maps to empty enumeration type.</span></span>|

 <span data-ttu-id="54045-372">En el siguiente código se muestra una clase de enumeración de C#.</span><span class="sxs-lookup"><span data-stu-id="54045-372">The following code shows a C# enumeration class.</span></span>

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

<span data-ttu-id="54045-373">Esta clase se asigna al esquema siguiente mediante el `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="54045-373">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="54045-374">Si los valores de la enumeración se inician en 1, no se generan bloques `xs:annotation` .</span><span class="sxs-lookup"><span data-stu-id="54045-374">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>

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

<span data-ttu-id="54045-375">El`DataContractSerializer` asigna tipos de enumeración marcados con `System.FlagsAttribute` a `xs:list` derivado de `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="54045-375">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="54045-376">No se admite ninguna otra variación de `xs:list` .</span><span class="sxs-lookup"><span data-stu-id="54045-376">No other `xs:list` variations are supported.</span></span>

### <a name="xslist-attributes"></a><span data-ttu-id="54045-377">\<xs:list>: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-377">\<xs:list>: attributes</span></span>

|<span data-ttu-id="54045-378">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-378">Attribute</span></span>|<span data-ttu-id="54045-379">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-379">Schema</span></span>|
|---------------|------------|
|`itemType`|<span data-ttu-id="54045-380">Prohibido.</span><span class="sxs-lookup"><span data-stu-id="54045-380">Forbidden.</span></span>|
|`id`|<span data-ttu-id="54045-381">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-381">Ignored.</span></span>|

### <a name="xslist-contents"></a><span data-ttu-id="54045-382">\<xs:list>: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-382">\<xs:list>: contents</span></span>

|<span data-ttu-id="54045-383">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-383">Contents</span></span>|<span data-ttu-id="54045-384">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-384">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="54045-385">Debe ser la restricción de `xs:string` utilizando la faceta `xs:enumeration` .</span><span class="sxs-lookup"><span data-stu-id="54045-385">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|

<span data-ttu-id="54045-386">Si el valor de enumeración no sigue una progresión de potencia 2 (valor predeterminado para marcas), el valor se almacena en `xs:annotation/xs:appInfo/ser:EnumerationValue` .</span><span class="sxs-lookup"><span data-stu-id="54045-386">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>

<span data-ttu-id="54045-387">Por ejemplo, el código siguiente marca un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="54045-387">For example, the following code flags an enumeration type.</span></span>

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

<span data-ttu-id="54045-388">Este tipo asigna al esquema siguiente.</span><span class="sxs-lookup"><span data-stu-id="54045-388">This type maps to the following schema.</span></span>

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

## <a name="inheritance"></a><span data-ttu-id="54045-389">Herencia</span><span class="sxs-lookup"><span data-stu-id="54045-389">Inheritance</span></span>

### <a name="general-rules"></a><span data-ttu-id="54045-390">Reglas Generales</span><span class="sxs-lookup"><span data-stu-id="54045-390">General rules</span></span>

<span data-ttu-id="54045-391">Un contrato de datos puede heredar de otro contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-391">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="54045-392">Tales contratos de datos asignan a una base y son derivados por tipos de extensión mediante la construcción de squema XML `<xs:extension>` .</span><span class="sxs-lookup"><span data-stu-id="54045-392">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>

<span data-ttu-id="54045-393">Un contrato de datos no puede heredar de un contrato de datos de colección.</span><span class="sxs-lookup"><span data-stu-id="54045-393">A data contract cannot inherit from a collection data contract.</span></span>

<span data-ttu-id="54045-394">Por ejemplo, el código siguiente es un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-394">For example, the following code is a data contract.</span></span>

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

<span data-ttu-id="54045-395">Este contrato de datos asigna a la declaración de tipos de esquema XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="54045-395">This data contract maps to the following XML Schema type declaration.</span></span>

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

### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="54045-396">\<xs:complexContent>: atributos</span><span class="sxs-lookup"><span data-stu-id="54045-396">\<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="54045-397">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-397">Attribute</span></span>|<span data-ttu-id="54045-398">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-398">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="54045-399">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-399">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="54045-400">Debe ser false.</span><span class="sxs-lookup"><span data-stu-id="54045-400">Must be false.</span></span>|

### <a name="xscomplexcontent-contents"></a><span data-ttu-id="54045-401">\<xs:complexContent>: contenido</span><span class="sxs-lookup"><span data-stu-id="54045-401">\<xs:complexContent>: contents</span></span>

|<span data-ttu-id="54045-402">Contenido</span><span class="sxs-lookup"><span data-stu-id="54045-402">Contents</span></span>|<span data-ttu-id="54045-403">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-403">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="54045-404">Prohibido, excepto cuando base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="54045-404">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="54045-405">Lo último es equivalente a colocar directamente el contenido de `xs:restriction` bajo el contenedor de `xs:complexContent`.</span><span class="sxs-lookup"><span data-stu-id="54045-405">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|
|`extension`|<span data-ttu-id="54045-406">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-406">Supported.</span></span> <span data-ttu-id="54045-407">Asigna a la herencia del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-407">Maps to data contract inheritance.</span></span>|

### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="54045-408">\<xs:extension> en \<xs:complexContent> : atributos</span><span class="sxs-lookup"><span data-stu-id="54045-408">\<xs:extension> in \<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="54045-409">Atributo</span><span class="sxs-lookup"><span data-stu-id="54045-409">Attribute</span></span>|<span data-ttu-id="54045-410">Schema</span><span class="sxs-lookup"><span data-stu-id="54045-410">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="54045-411">ignorado.</span><span class="sxs-lookup"><span data-stu-id="54045-411">Ignored.</span></span>|
|`base`|<span data-ttu-id="54045-412">Compatible.</span><span class="sxs-lookup"><span data-stu-id="54045-412">Supported.</span></span> <span data-ttu-id="54045-413">Asigna al tipo de contrato de datos base desde el que este tipo hereda.</span><span class="sxs-lookup"><span data-stu-id="54045-413">Maps to the base data contract type that this type inherits from.</span></span>|

### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="54045-414">\<xs:extension> en \<xs:complexContent> : contenido</span><span class="sxs-lookup"><span data-stu-id="54045-414">\<xs:extension> in \<xs:complexContent>: contents</span></span>

<span data-ttu-id="54045-415">Las reglas son la mismas que para el contenido `<xs:complexType>` .</span><span class="sxs-lookup"><span data-stu-id="54045-415">The rules are the same as for `<xs:complexType>` contents.</span></span>

<span data-ttu-id="54045-416">Si se proporciona un `<xs:sequence>` , sus elementos de miembro asignan a los miembros de datos adicionales que se encuentran en el contrato de datos derivado.</span><span class="sxs-lookup"><span data-stu-id="54045-416">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>

<span data-ttu-id="54045-417">Si un tipo derivado contiene un elemento con el mismo nombre que un elemento en un tipo base, la declaración de elementos duplicados asigna a un miembro de datos con un nombre que se genera para que sea único.</span><span class="sxs-lookup"><span data-stu-id="54045-417">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="54045-418">Los números enteros positivos se suman al nombre del miembro de datos ("member1", "member2", etc.) hasta que se encuentre un nombre único.</span><span class="sxs-lookup"><span data-stu-id="54045-418">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="54045-419">De manera inversa:</span><span class="sxs-lookup"><span data-stu-id="54045-419">Conversely:</span></span>

- <span data-ttu-id="54045-420">Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre y tipo que un miembro de datos en un contrato de datos base, `DataContractSerializer` genera este elemento correspondiente en el tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="54045-420">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>

- <span data-ttu-id="54045-421">Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre que un miembro de datos en un contrato de datos base pero un tipo diferente, el `DataContractSerializer` importa un esquema con un elemento del tipo `xs:anyType` en las declaraciones de tipos base y de tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="54045-421">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="54045-422">El nombre de tipo original se conserva en `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span><span class="sxs-lookup"><span data-stu-id="54045-422">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>

<span data-ttu-id="54045-423">Ambas variaciones pueden conducir a un esquema con un modelo de contenido ambiguo, que depende del orden de los miembros de datos respectivos.</span><span class="sxs-lookup"><span data-stu-id="54045-423">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>

## <a name="typeprimitive-mapping"></a><span data-ttu-id="54045-424">Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="54045-424">Type/primitive mapping</span></span>

<span data-ttu-id="54045-425">El `DataContractSerializer` utiliza la asignación siguiente para los tipos primitivos del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="54045-425">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>

|<span data-ttu-id="54045-426">Tipo XSD</span><span class="sxs-lookup"><span data-stu-id="54045-426">XSD type</span></span>|<span data-ttu-id="54045-427">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="54045-427">.NET type</span></span>|
|--------------|---------------|
|`anyType`|<span data-ttu-id="54045-428"><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="54045-428"><xref:System.Object>.</span></span>|
|`anySimpleType`|<span data-ttu-id="54045-429"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-429"><xref:System.String>.</span></span>|
|`duration`|<span data-ttu-id="54045-430"><xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="54045-430"><xref:System.TimeSpan>.</span></span>|
|`dateTime`|<span data-ttu-id="54045-431"><xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="54045-431"><xref:System.DateTime>.</span></span>|
|`dateTimeOffset`|<span data-ttu-id="54045-432"><xref:System.DateTime> y <xref:System.TimeSpan> para el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="54045-432"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="54045-433">Vea abajo Serialización de DateTimeOffset.</span><span class="sxs-lookup"><span data-stu-id="54045-433">See DateTimeOffset Serialization below.</span></span>|
|`time`|<span data-ttu-id="54045-434"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-434"><xref:System.String>.</span></span>|
|`date`|<span data-ttu-id="54045-435"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-435"><xref:System.String>.</span></span>|
|`gYearMonth`|<span data-ttu-id="54045-436"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-436"><xref:System.String>.</span></span>|
|`gYear`|<span data-ttu-id="54045-437"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-437"><xref:System.String>.</span></span>|
|`gMonthDay`|<span data-ttu-id="54045-438"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-438"><xref:System.String>.</span></span>|
|`gDay`|<span data-ttu-id="54045-439"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-439"><xref:System.String>.</span></span>|
|`gMonth`|<span data-ttu-id="54045-440"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-440"><xref:System.String>.</span></span>|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|<span data-ttu-id="54045-441">Matriz de tipo<xref:System.Byte> .</span><span class="sxs-lookup"><span data-stu-id="54045-441"><xref:System.Byte> array.</span></span>|
|`hexBinary`|<span data-ttu-id="54045-442"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-442"><xref:System.String>.</span></span>|
|`float`|<span data-ttu-id="54045-443"><xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="54045-443"><xref:System.Single>.</span></span>|
|`double`|<span data-ttu-id="54045-444"><xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="54045-444"><xref:System.Double>.</span></span>|
|`anyURI`|<span data-ttu-id="54045-445"><xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="54045-445"><xref:System.Uri>.</span></span>|
|`QName`|<span data-ttu-id="54045-446"><xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="54045-446"><xref:System.Xml.XmlQualifiedName>.</span></span>|
|`string`|<span data-ttu-id="54045-447"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-447"><xref:System.String>.</span></span>|
|`normalizedString`|<span data-ttu-id="54045-448"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-448"><xref:System.String>.</span></span>|
|`token`|<span data-ttu-id="54045-449"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-449"><xref:System.String>.</span></span>|
|`language`|<span data-ttu-id="54045-450"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-450"><xref:System.String>.</span></span>|
|`Name`|<span data-ttu-id="54045-451"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-451"><xref:System.String>.</span></span>|
|`NCName`|<span data-ttu-id="54045-452"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-452"><xref:System.String>.</span></span>|
|`ID`|<span data-ttu-id="54045-453"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-453"><xref:System.String>.</span></span>|
|`IDREF`|<span data-ttu-id="54045-454"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-454"><xref:System.String>.</span></span>|
|`IDREFS`|<span data-ttu-id="54045-455"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-455"><xref:System.String>.</span></span>|
|`ENTITY`|<span data-ttu-id="54045-456"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-456"><xref:System.String>.</span></span>|
|`ENTITIES`|<span data-ttu-id="54045-457"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-457"><xref:System.String>.</span></span>|
|`NMTOKEN`|<span data-ttu-id="54045-458"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-458"><xref:System.String>.</span></span>|
|`NMTOKENS`|<span data-ttu-id="54045-459"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="54045-459"><xref:System.String>.</span></span>|
|`decimal`|<span data-ttu-id="54045-460"><xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="54045-460"><xref:System.Decimal>.</span></span>|
|`integer`|<span data-ttu-id="54045-461"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="54045-461"><xref:System.Int64>.</span></span>|
|`nonPositiveInteger`|<span data-ttu-id="54045-462"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="54045-462"><xref:System.Int64>.</span></span>|
|`negativeInteger`|<span data-ttu-id="54045-463"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="54045-463"><xref:System.Int64>.</span></span>|
|`long`|<span data-ttu-id="54045-464"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="54045-464"><xref:System.Int64>.</span></span>|
|`int`|<span data-ttu-id="54045-465"><xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="54045-465"><xref:System.Int32>.</span></span>|
|`short`|<span data-ttu-id="54045-466"><xref:System.Int16>.</span><span class="sxs-lookup"><span data-stu-id="54045-466"><xref:System.Int16>.</span></span>|
|`Byte`|<span data-ttu-id="54045-467"><xref:System.SByte>.</span><span class="sxs-lookup"><span data-stu-id="54045-467"><xref:System.SByte>.</span></span>|
|`nonNegativeInteger`|<span data-ttu-id="54045-468"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="54045-468"><xref:System.Int64>.</span></span>|
|`unsignedLong`|<span data-ttu-id="54045-469"><xref:System.UInt64>.</span><span class="sxs-lookup"><span data-stu-id="54045-469"><xref:System.UInt64>.</span></span>|
|`unsignedInt`|<span data-ttu-id="54045-470"><xref:System.UInt32>.</span><span class="sxs-lookup"><span data-stu-id="54045-470"><xref:System.UInt32>.</span></span>|
|`unsignedShort`|<span data-ttu-id="54045-471"><xref:System.UInt16>.</span><span class="sxs-lookup"><span data-stu-id="54045-471"><xref:System.UInt16>.</span></span>|
|`unsignedByte`|<span data-ttu-id="54045-472"><xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="54045-472"><xref:System.Byte>.</span></span>|
|`positiveInteger`|<span data-ttu-id="54045-473"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="54045-473"><xref:System.Int64>.</span></span>|

## <a name="iserializable-types-mapping"></a><span data-ttu-id="54045-474">Asignación de tipos ISerializable</span><span class="sxs-lookup"><span data-stu-id="54045-474">ISerializable types mapping</span></span>

<span data-ttu-id="54045-475">En .NET Framework versión 1,0, <xref:System.Runtime.Serialization.ISerializable> se presentó como un mecanismo general para serializar objetos para la persistencia o la transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="54045-475">In .NET Framework version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="54045-476">Hay muchos tipos de .NET Framework que implementan `ISerializable` y que pueden pasarse entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="54045-476">There are many .NET Framework types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="54045-477"><xref:System.Runtime.Serialization.DataContractSerializer> proporciona de manera natural compatibilidad para las clases `ISerializable` .</span><span class="sxs-lookup"><span data-stu-id="54045-477"><xref:System.Runtime.Serialization.DataContractSerializer> naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="54045-478">`DataContractSerializer` asigna tipos de esquema de implementación de `ISerializable` que solo difieren en cuanto al QName (nombre completo) del tipo y son colecciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="54045-478">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="54045-479">Por ejemplo, `DataContractSerializer` se asigna <xref:System.Exception> al siguiente tipo XSD en el `http://schemas.datacontract.org/2004/07/System` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="54045-479">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

<span data-ttu-id="54045-480">El atributo opcional `ser:FactoryType` opcional declarado en el esquema de serialización de contrato de datos hace referencia a una clase de generador que puede deserializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="54045-480">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="54045-481">La clase de generador debe formar parte de la colección de tipos conocidos de la instancia de `DataContractSerializer` que se está usando.</span><span class="sxs-lookup"><span data-stu-id="54045-481">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="54045-482">Para obtener más información sobre los tipos conocidos, consulte [Data Contract known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="54045-482">For more information about known types, see [Data Contract Known Types](data-contract-known-types.md).</span></span>

## <a name="datacontract-serialization-schema"></a><span data-ttu-id="54045-483">Esquema de serialización de DataContract</span><span class="sxs-lookup"><span data-stu-id="54045-483">DataContract Serialization Schema</span></span>

<span data-ttu-id="54045-484">Varios esquemas exportados por los tipos de uso, elementos y atributos del `DataContractSerializer` , desde un espacio de nombres de serialización de contrato de datos especial:</span><span class="sxs-lookup"><span data-stu-id="54045-484">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>

`http://schemas.microsoft.com/2003/10/Serialization`

<span data-ttu-id="54045-485">A continuación, se muestra una declaración de esquema de serialización de contrato de datos completa.</span><span class="sxs-lookup"><span data-stu-id="54045-485">The following is a complete Data Contract Serialization schema declaration.</span></span>

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

<span data-ttu-id="54045-486">Se debería tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="54045-486">The following should be noted:</span></span>

- <span data-ttu-id="54045-487">`ser:char` se introduce para representar caracteres Unicode de tipo <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="54045-487">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>

- <span data-ttu-id="54045-488">El `valuespace` de `xs:duration` se reduce a un conjunto ordenado para que pueda asignarse a un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="54045-488">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>

- <span data-ttu-id="54045-489">`FactoryType` se utiliza en esquemas exportados a partir de tipos que se derivan de <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="54045-489">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>

## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="54045-490">Importación de esquemas no DataContract</span><span class="sxs-lookup"><span data-stu-id="54045-490">Importing non-DataContract schemas</span></span>

<span data-ttu-id="54045-491">`DataContractSerializer` tiene la opción `ImportXmlTypes` para permitir la importación de esquemas que no cumplen el perfil XSD `DataContractSerializer` (vea la propiedad <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> ).</span><span class="sxs-lookup"><span data-stu-id="54045-491">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="54045-492">Establecer esta opción en `true` habilita la aceptación de tipos de esquema no conformes y la asignación de ellos a la implementación siguiente, <xref:System.Xml.Serialization.IXmlSerializable> ajuste de una matriz de <xref:System.Xml.XmlNode> (solo difiere el nombre de la clase).</span><span class="sxs-lookup"><span data-stu-id="54045-492">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>

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

## <a name="datetimeoffset-serialization"></a><span data-ttu-id="54045-493">Serialización de DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="54045-493">DateTimeOffset Serialization</span></span>

<span data-ttu-id="54045-494"><xref:System.DateTimeOffset> no se trata como un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="54045-494">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="54045-495">En su lugar, se serializa como un elemento complejo con dos partes.</span><span class="sxs-lookup"><span data-stu-id="54045-495">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="54045-496">La primera parte representa la fecha y hora, y la segunda parte representa el desplazamiento de la fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="54045-496">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="54045-497">En el siguiente código se muestra un ejemplo de un valor DateTimeOffset serializado.</span><span class="sxs-lookup"><span data-stu-id="54045-497">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>

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

<span data-ttu-id="54045-498">El esquema es de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="54045-498">The schema is as follows.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="54045-499">Vea también</span><span class="sxs-lookup"><span data-stu-id="54045-499">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="54045-500">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="54045-500">Using Data Contracts</span></span>](using-data-contracts.md)
