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
ms.openlocfilehash: 462db50a42e55c0c5a9570317ceeeb0ae69215a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927649"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="b746a-102">\<cryptographySettings >, elemento</span><span class="sxs-lookup"><span data-stu-id="b746a-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="b746a-103">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="b746a-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="b746a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b746a-104">\<configuration></span></span>  
<span data-ttu-id="b746a-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="b746a-105">\<mscorlib></span></span>  
<span data-ttu-id="b746a-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="b746a-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b746a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b746a-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b746a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b746a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b746a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b746a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b746a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b746a-110">Attributes</span></span>  
 <span data-ttu-id="b746a-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b746a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b746a-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b746a-112">Child Elements</span></span>  
  
|<span data-ttu-id="b746a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="b746a-113">Element</span></span>|<span data-ttu-id="b746a-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b746a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b746a-115">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="b746a-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="b746a-116">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="b746a-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="b746a-117">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="b746a-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="b746a-118">Contiene las asignaciones de identificador de objetos (OID) ASN. 1 a las clases.</span><span class="sxs-lookup"><span data-stu-id="b746a-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b746a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b746a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b746a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b746a-120">Element</span></span>|<span data-ttu-id="b746a-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b746a-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b746a-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b746a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="b746a-123">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="b746a-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b746a-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b746a-124">Example</span></span>  
 <span data-ttu-id="b746a-125">En el ejemplo siguiente se muestra cómo  **\<** utilizar el elemento > de cryptographySettings para contener asignaciones de nombres de criptografía y asignaciones de OID.</span><span class="sxs-lookup"><span data-stu-id="b746a-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="b746a-126">En este ejemplo se configura el tiempo de ejecución <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> para que `MyHashClass` devuelva un `MyCryptoClass` objeto y la clase se asigne al identificador de objeto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="b746a-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b746a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b746a-127">See also</span></span>

- [<span data-ttu-id="b746a-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b746a-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b746a-129">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="b746a-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b746a-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b746a-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
