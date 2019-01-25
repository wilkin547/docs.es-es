---
title: '&lt;cryptographySettings&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 0d1dfe5cadf59122994f1a751f985e186c6cf5b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602512"
---
# <a name="ltcryptographysettingsgt-element"></a><span data-ttu-id="207a2-102">&lt;cryptographySettings&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="207a2-102">&lt;cryptographySettings&gt; Element</span></span>
<span data-ttu-id="207a2-103">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="207a2-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="207a2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="207a2-104">\<configuration></span></span>  
<span data-ttu-id="207a2-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="207a2-105">\<mscorlib></span></span>  
<span data-ttu-id="207a2-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="207a2-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="207a2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="207a2-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="207a2-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="207a2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="207a2-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="207a2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="207a2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="207a2-110">Attributes</span></span>  
 <span data-ttu-id="207a2-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="207a2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="207a2-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="207a2-112">Child Elements</span></span>  
  
|<span data-ttu-id="207a2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="207a2-113">Element</span></span>|<span data-ttu-id="207a2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="207a2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="207a2-115">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="207a2-115">\<cryptoNameMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="207a2-116">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="207a2-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="207a2-117">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="207a2-117">\<oidMap></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="207a2-118">Contiene asignaciones de identificador (OID) de objeto ASN.1 a clases.</span><span class="sxs-lookup"><span data-stu-id="207a2-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="207a2-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="207a2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="207a2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="207a2-120">Element</span></span>|<span data-ttu-id="207a2-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="207a2-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="207a2-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="207a2-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="207a2-123">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="207a2-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="207a2-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="207a2-124">Example</span></span>  
 <span data-ttu-id="207a2-125">El ejemplo siguiente se muestra cómo utilizar el  **\<cryptographySettings >** elemento que se va a contener las asignaciones de nombres de criptografía y asignaciones de OID.</span><span class="sxs-lookup"><span data-stu-id="207a2-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="207a2-126">Este ejemplo configura el tiempo de ejecución para que <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> devuelve un `MyHashClass` objeto y el `MyCryptoClass` clase se asigna al identificador de objetos 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="207a2-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="207a2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="207a2-127">See also</span></span>
- [<span data-ttu-id="207a2-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="207a2-128">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="207a2-129">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="207a2-129">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="207a2-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="207a2-130">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
