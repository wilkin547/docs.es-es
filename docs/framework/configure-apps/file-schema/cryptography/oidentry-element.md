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
ms.openlocfilehash: 013994e36c4c63410a753967cbac92c38783ae62
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659590"
---
# <a name="oidentry-element"></a><span data-ttu-id="4baa2-102">\<oidEntry >, elemento</span><span class="sxs-lookup"><span data-stu-id="4baa2-102">\<oidEntry> Element</span></span>
<span data-ttu-id="4baa2-103">Asigna un identificador de objeto (OID) ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="4baa2-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="4baa2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4baa2-104">\<configuration></span></span>  
<span data-ttu-id="4baa2-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="4baa2-105">\<mscorlib></span></span>  
<span data-ttu-id="4baa2-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="4baa2-106">\<cryptographySettings></span></span>  
<span data-ttu-id="4baa2-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="4baa2-107">\<oidMap></span></span>  
<span data-ttu-id="4baa2-108">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="4baa2-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4baa2-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4baa2-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4baa2-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4baa2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4baa2-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4baa2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4baa2-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4baa2-112">Attributes</span></span>  
  
|<span data-ttu-id="4baa2-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4baa2-113">Attribute</span></span>|<span data-ttu-id="4baa2-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4baa2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4baa2-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="4baa2-115">**OID**</span></span>|<span data-ttu-id="4baa2-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4baa2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="4baa2-117">Especifica el OID ASN. 1 correspondiente al algoritmo implementado por la clase.</span><span class="sxs-lookup"><span data-stu-id="4baa2-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="4baa2-118">**name**</span><span class="sxs-lookup"><span data-stu-id="4baa2-118">**name**</span></span>|<span data-ttu-id="4baa2-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4baa2-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="4baa2-120">Especifica el valor para el atributo de **nombre** en la [ \<](nameentry-element.md) etiqueta de > de elemento nameEntry.</span><span class="sxs-lookup"><span data-stu-id="4baa2-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4baa2-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4baa2-121">Child Elements</span></span>  
 <span data-ttu-id="4baa2-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4baa2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4baa2-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4baa2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4baa2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4baa2-124">Element</span></span>|<span data-ttu-id="4baa2-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4baa2-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4baa2-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4baa2-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="4baa2-127">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="4baa2-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="4baa2-128">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="4baa2-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="4baa2-129">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="4baa2-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4baa2-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4baa2-130">Remarks</span></span>  
 <span data-ttu-id="4baa2-131">Los identificadores de objeto ASN. 1 identifican los algoritmos en algunos formatos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="4baa2-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="4baa2-132">Asigne identificadores de objeto a nombres descriptivos para los algoritmos que desee identificar.</span><span class="sxs-lookup"><span data-stu-id="4baa2-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4baa2-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4baa2-133">Example</span></span>  
 <span data-ttu-id="4baa2-134">En el ejemplo siguiente se muestra cómo usar  **\<** el elemento > de oidEntry para asignar un identificador de objeto para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="4baa2-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4baa2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4baa2-135">See also</span></span>

- [<span data-ttu-id="4baa2-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4baa2-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4baa2-137">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="4baa2-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4baa2-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4baa2-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="4baa2-139">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="4baa2-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="4baa2-140">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="4baa2-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
