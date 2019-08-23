---
title: <cryptoClasses> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 87e64ecd79ebc54a669d33550790781c87b5917c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921130"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="30bc5-102">\<cryptoClasses >, elemento</span><span class="sxs-lookup"><span data-stu-id="30bc5-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="30bc5-103">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="30bc5-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="30bc5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="30bc5-104">\<configuration></span></span>  
<span data-ttu-id="30bc5-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="30bc5-105">\<mscorlib></span></span>  
<span data-ttu-id="30bc5-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="30bc5-106">\<cryptographySettings></span></span>  
<span data-ttu-id="30bc5-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="30bc5-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="30bc5-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="30bc5-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30bc5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30bc5-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30bc5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="30bc5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="30bc5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="30bc5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30bc5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="30bc5-112">Attributes</span></span>  
 <span data-ttu-id="30bc5-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="30bc5-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="30bc5-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="30bc5-114">Child Elements</span></span>  
  
|<span data-ttu-id="30bc5-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="30bc5-115">Element</span></span>|<span data-ttu-id="30bc5-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="30bc5-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30bc5-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="30bc5-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="30bc5-118">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="30bc5-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30bc5-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="30bc5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="30bc5-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="30bc5-120">Element</span></span>|<span data-ttu-id="30bc5-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="30bc5-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="30bc5-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30bc5-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="30bc5-123">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="30bc5-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="30bc5-124">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="30bc5-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="30bc5-125">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="30bc5-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="30bc5-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30bc5-126">Example</span></span>  
 <span data-ttu-id="30bc5-127">En el ejemplo siguiente se muestra cómo  **\<** usar el elemento > de cryptoClass para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="30bc5-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="30bc5-128">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="30bc5-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30bc5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="30bc5-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="30bc5-130">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="30bc5-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="30bc5-131">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="30bc5-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="30bc5-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="30bc5-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="30bc5-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="30bc5-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="30bc5-134">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="30bc5-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
