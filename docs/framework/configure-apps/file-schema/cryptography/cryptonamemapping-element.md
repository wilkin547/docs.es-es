---
title: '&lt;cryptoNameMapping&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: b9daa1c11a151d905af934b62f386a1229ece4ed
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083787"
---
# <a name="ltcryptonamemappinggt-element"></a><span data-ttu-id="97a6c-102">&lt;cryptoNameMapping&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="97a6c-102">&lt;cryptoNameMapping&gt; Element</span></span>
<span data-ttu-id="97a6c-103">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="97a6c-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="97a6c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="97a6c-104">\<configuration></span></span>  
<span data-ttu-id="97a6c-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="97a6c-105">\<mscorlib></span></span>  
<span data-ttu-id="97a6c-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="97a6c-106">\<cryptographySettings></span></span>  
<span data-ttu-id="97a6c-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="97a6c-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a6c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97a6c-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97a6c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97a6c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="97a6c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97a6c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97a6c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="97a6c-111">Attributes</span></span>  
 <span data-ttu-id="97a6c-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97a6c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97a6c-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97a6c-113">Child Elements</span></span>  
  
|<span data-ttu-id="97a6c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="97a6c-114">Element</span></span>|<span data-ttu-id="97a6c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a6c-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="97a6c-116">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>**.</span><span class="sxs-lookup"><span data-stu-id="97a6c-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="97a6c-117">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="97a6c-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97a6c-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97a6c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="97a6c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="97a6c-119">Element</span></span>|<span data-ttu-id="97a6c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a6c-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="97a6c-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97a6c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="97a6c-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="97a6c-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="97a6c-123">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="97a6c-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="97a6c-124">Contiene el \<cryptographySettings > elemento.</span><span class="sxs-lookup"><span data-stu-id="97a6c-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="97a6c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97a6c-125">Example</span></span>  
 <span data-ttu-id="97a6c-126">El ejemplo siguiente muestra cómo usar el  **\<cryptoNameMapping >** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="97a6c-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="97a6c-127">A continuación, puede pasar la cadena "RSA" a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y el uso la <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método devuelva un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="97a6c-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="97a6c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="97a6c-128">See also</span></span>
- [<span data-ttu-id="97a6c-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="97a6c-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="97a6c-130">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="97a6c-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="97a6c-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="97a6c-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="97a6c-132">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="97a6c-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
