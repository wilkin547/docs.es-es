---
description: 'Más información acerca de: <cryptographySettings> elemento'
title: <cryptographySettings> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: afd4fdbc24dfaac60ce24b7a439a8d4d8a9427ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730101"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="009ad-103">\<cryptographySettings> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="009ad-103">\<cryptographySettings> Element</span></span>

<span data-ttu-id="009ad-104">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="009ad-104">Contains cryptography settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**

## <a name="syntax"></a><span data-ttu-id="009ad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="009ad-105">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="009ad-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="009ad-106">Attributes and Elements</span></span>  

 <span data-ttu-id="009ad-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="009ad-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="009ad-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="009ad-108">Attributes</span></span>  

 <span data-ttu-id="009ad-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="009ad-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="009ad-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="009ad-110">Child Elements</span></span>  
  
|<span data-ttu-id="009ad-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="009ad-111">Element</span></span>|<span data-ttu-id="009ad-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="009ad-112">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](cryptonamemapping-element.md)|<span data-ttu-id="009ad-113">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="009ad-113">Contains mappings of classes to friendly names.</span></span>|  
|[\<oidMap>](oidmap-element.md)|<span data-ttu-id="009ad-114">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="009ad-114">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="009ad-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="009ad-115">Parent Elements</span></span>  
  
|<span data-ttu-id="009ad-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="009ad-116">Element</span></span>|<span data-ttu-id="009ad-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="009ad-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="009ad-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="009ad-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="009ad-119">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="009ad-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="009ad-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="009ad-120">Example</span></span>  

 <span data-ttu-id="009ad-121">En el ejemplo siguiente se muestra cómo usar el **\<cryptographySettings>** elemento para contener asignaciones de nombres de criptografía y asignaciones de OID.</span><span class="sxs-lookup"><span data-stu-id="009ad-121">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="009ad-122">En este ejemplo se configura el tiempo de ejecución para que <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> devuelva un `MyHashClass` objeto y la `MyCryptoClass` clase se asigne al identificador de objeto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="009ad-122">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="009ad-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="009ad-123">See also</span></span>

- [<span data-ttu-id="009ad-124">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="009ad-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="009ad-125">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="009ad-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="009ad-126">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="009ad-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
