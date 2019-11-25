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
ms.openlocfilehash: ca0a9a4b37f28eb03f58de4fd9b120cb7e654e0c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088641"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="a8ce1-102">\<elemento > cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="a8ce1-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="a8ce1-103">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="a8ce1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8ce1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8ce1-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a8ce1-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="a8ce1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptographySettings >**</span><span class="sxs-lookup"><span data-stu-id="a8ce1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a8ce1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8ce1-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8ce1-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a8ce1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a8ce1-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8ce1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8ce1-110">Attributes</span></span>  
 <span data-ttu-id="a8ce1-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8ce1-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a8ce1-112">Child Elements</span></span>  
  
|<span data-ttu-id="a8ce1-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8ce1-113">Element</span></span>|<span data-ttu-id="a8ce1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8ce1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8ce1-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="a8ce1-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="a8ce1-116">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="a8ce1-117">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="a8ce1-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="a8ce1-118">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8ce1-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a8ce1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a8ce1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8ce1-120">Element</span></span>|<span data-ttu-id="a8ce1-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8ce1-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a8ce1-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="a8ce1-123">Contiene el elemento `cryptographySettings`.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a8ce1-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8ce1-124">Example</span></span>  
 <span data-ttu-id="a8ce1-125">En el ejemplo siguiente se muestra cómo utilizar el elemento **\<cryptographySettings >** para contener asignaciones de nombres de criptografía y asignaciones OID.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="a8ce1-126">En este ejemplo se configura el tiempo de ejecución para que <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> devuelva un objeto `MyHashClass` y la clase `MyCryptoClass` se asigne al identificador de objeto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="a8ce1-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8ce1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8ce1-127">See also</span></span>

- [<span data-ttu-id="a8ce1-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a8ce1-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a8ce1-129">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="a8ce1-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a8ce1-130">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="a8ce1-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
