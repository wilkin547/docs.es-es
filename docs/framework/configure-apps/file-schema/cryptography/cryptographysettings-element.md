---
title: <cryptographySettings> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: fe6de09213c6f980e8eb205a318aae50033b2a84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155237"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="adbec-102">\<criptografíaConfiguración> elemento</span><span class="sxs-lookup"><span data-stu-id="adbec-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="adbec-103">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="adbec-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="adbec-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="adbec-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="adbec-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="adbec-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="adbec-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<criptografíaConfiguración>**</span><span class="sxs-lookup"><span data-stu-id="adbec-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="adbec-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adbec-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adbec-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="adbec-108">Attributes and Elements</span></span>  
 <span data-ttu-id="adbec-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="adbec-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adbec-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="adbec-110">Attributes</span></span>  
 <span data-ttu-id="adbec-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="adbec-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="adbec-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="adbec-112">Child Elements</span></span>  
  
|<span data-ttu-id="adbec-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="adbec-113">Element</span></span>|<span data-ttu-id="adbec-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="adbec-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="adbec-115">\<>cryptoNameMapping</span><span class="sxs-lookup"><span data-stu-id="adbec-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="adbec-116">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="adbec-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="adbec-117">\<>oidMap</span><span class="sxs-lookup"><span data-stu-id="adbec-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="adbec-118">Contiene asignaciones de identificador de objeto (OID) ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="adbec-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="adbec-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="adbec-119">Parent Elements</span></span>  
  
|<span data-ttu-id="adbec-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="adbec-120">Element</span></span>|<span data-ttu-id="adbec-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="adbec-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="adbec-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="adbec-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="adbec-123">Contiene `cryptographySettings` el elemento.</span><span class="sxs-lookup"><span data-stu-id="adbec-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="adbec-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="adbec-124">Example</span></span>  
 <span data-ttu-id="adbec-125">En el ejemplo siguiente se muestra cómo utilizar el \*\* \<elemento de>cryptographySettings\*\* para contener asignaciones de nombres de criptografía y asignaciones de OID.</span><span class="sxs-lookup"><span data-stu-id="adbec-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="adbec-126">En este ejemplo se <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> configura `MyHashClass` el tiempo `MyCryptoClass` de ejecución para que devuelva un objeto y la clase se asigne al identificador de objeto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="adbec-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="adbec-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="adbec-127">See also</span></span>

- [<span data-ttu-id="adbec-128">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="adbec-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="adbec-129">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="adbec-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="adbec-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="adbec-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
