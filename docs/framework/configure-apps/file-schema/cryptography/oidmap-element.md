---
title: <oidMap> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: a28eaf68fe1e6ab3f26592eee5ae2d0f2e7a3256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155172"
---
# <a name="oidmap-element"></a><span data-ttu-id="154ec-102">\<oidMap> Element</span><span class="sxs-lookup"><span data-stu-id="154ec-102">\<oidMap> Element</span></span>
<span data-ttu-id="154ec-103">Contiene asignaciones de identificador de objeto (OID) ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="154ec-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

<span data-ttu-id="154ec-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="154ec-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="154ec-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="154ec-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="154ec-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<criptografíaConfiguración>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="154ec-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="154ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>oidMap**</span><span class="sxs-lookup"><span data-stu-id="154ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>

## <a name="syntax"></a><span data-ttu-id="154ec-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="154ec-108">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="154ec-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="154ec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="154ec-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="154ec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="154ec-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="154ec-111">Attributes</span></span>  
 <span data-ttu-id="154ec-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="154ec-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="154ec-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="154ec-113">Child Elements</span></span>  
  
|<span data-ttu-id="154ec-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="154ec-114">Element</span></span>|<span data-ttu-id="154ec-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="154ec-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="154ec-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="154ec-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="154ec-117">Asigna un OID ASN.1 a un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="154ec-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="154ec-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="154ec-118">Parent Elements</span></span>  
  
|<span data-ttu-id="154ec-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="154ec-119">Element</span></span>|<span data-ttu-id="154ec-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="154ec-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="154ec-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="154ec-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="154ec-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="154ec-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="154ec-123">Contiene `cryptographySettings` el elemento.</span><span class="sxs-lookup"><span data-stu-id="154ec-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="154ec-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="154ec-124">Example</span></span>  
 <span data-ttu-id="154ec-125">En el ejemplo siguiente \*\* \<\*\* se muestra cómo utilizar el elemento>oidMap para contener una asignación de un OID para el algoritmo hash RIPEMD-160 a una implementación de ese algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="154ec-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="154ec-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="154ec-126">See also</span></span>

- [<span data-ttu-id="154ec-127">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="154ec-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="154ec-128">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="154ec-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="154ec-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="154ec-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="154ec-130">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="154ec-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="154ec-131">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="154ec-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
