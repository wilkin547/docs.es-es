---
title: <oidEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: c686d2b99ad66aec753a356b09fa3c7151193808
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219348"
---
# <a name="oidentry-element"></a><span data-ttu-id="d1d8b-102">\<oidEntry > elemento</span><span class="sxs-lookup"><span data-stu-id="d1d8b-102">\<oidEntry> Element</span></span>
<span data-ttu-id="d1d8b-103">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="d1d8b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d1d8b-104">\<configuration></span></span>  
<span data-ttu-id="d1d8b-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="d1d8b-105">\<mscorlib></span></span>  
<span data-ttu-id="d1d8b-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="d1d8b-106">\<cryptographySettings></span></span>  
<span data-ttu-id="d1d8b-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="d1d8b-107">\<oidMap></span></span>  
<span data-ttu-id="d1d8b-108">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="d1d8b-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1d8b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1d8b-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1d8b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d1d8b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d1d8b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1d8b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1d8b-112">Attributes</span></span>  
  
|<span data-ttu-id="d1d8b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d1d8b-113">Attribute</span></span>|<span data-ttu-id="d1d8b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1d8b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1d8b-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="d1d8b-115">**OID**</span></span>|<span data-ttu-id="d1d8b-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="d1d8b-117">Especifica el OID ASN.1 correspondiente al algoritmo implementado por la clase.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="d1d8b-118">**name**</span><span class="sxs-lookup"><span data-stu-id="d1d8b-118">**name**</span></span>|<span data-ttu-id="d1d8b-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="d1d8b-120">Especifica el valor de la **nombre** atributo en el [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) etiqueta.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1d8b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d1d8b-121">Child Elements</span></span>  
 <span data-ttu-id="d1d8b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1d8b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d1d8b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d1d8b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1d8b-124">Element</span></span>|<span data-ttu-id="d1d8b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1d8b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d1d8b-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="d1d8b-127">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="d1d8b-128">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="d1d8b-129">Contiene asignaciones de identificador (OID) de objeto ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1d8b-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1d8b-130">Remarks</span></span>  
 <span data-ttu-id="d1d8b-131">Los identificadores de objeto ASN.1 identifican algoritmos en algunos formatos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="d1d8b-132">Los identificadores de objetos se asignan a nombres descriptivos para los algoritmos que desea identificar.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1d8b-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1d8b-133">Example</span></span>  
 <span data-ttu-id="d1d8b-134">El ejemplo siguiente muestra cómo usar el  **\<oidEntry >** elemento para asignar un identificador de objeto para el algoritmo de hash RIPEMD-160 a una implementación del algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d1d8b-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1d8b-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1d8b-135">See also</span></span>

- [<span data-ttu-id="d1d8b-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d1d8b-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d1d8b-137">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="d1d8b-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="d1d8b-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="d1d8b-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="d1d8b-139">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="d1d8b-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="d1d8b-140">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="d1d8b-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
