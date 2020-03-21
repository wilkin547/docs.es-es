---
title: <cryptoNameMapping> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155224"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="16b44-102">\<CryptoNameMapping> Element</span><span class="sxs-lookup"><span data-stu-id="16b44-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="16b44-103">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="16b44-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="16b44-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="16b44-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="16b44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<criptografíaConfiguración>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="16b44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>cryptoNameMapping**</span><span class="sxs-lookup"><span data-stu-id="16b44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="16b44-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16b44-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16b44-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="16b44-109">Attributes and Elements</span></span>  
 <span data-ttu-id="16b44-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="16b44-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16b44-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="16b44-111">Attributes</span></span>  
 <span data-ttu-id="16b44-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="16b44-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16b44-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="16b44-113">Child Elements</span></span>  
  
|<span data-ttu-id="16b44-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="16b44-114">Element</span></span>|<span data-ttu-id="16b44-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="16b44-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="16b44-116">Contiene una lista de clases de criptografía que \*\* \<\*\* tienen una asignación a un nombre descriptivo en el elemento nameEntry>.</span><span class="sxs-lookup"><span data-stu-id="16b44-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="16b44-117">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="16b44-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16b44-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="16b44-118">Parent Elements</span></span>  
  
|<span data-ttu-id="16b44-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="16b44-119">Element</span></span>|<span data-ttu-id="16b44-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="16b44-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="16b44-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16b44-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="16b44-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="16b44-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="16b44-123">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="16b44-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="16b44-124">Contiene el elemento \<cryptographySettings>.</span><span class="sxs-lookup"><span data-stu-id="16b44-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="16b44-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16b44-125">Example</span></span>  
 <span data-ttu-id="16b44-126">En el ejemplo siguiente \*\* \<\*\* se muestra cómo utilizar el elemento de>cryptoNameMapping para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="16b44-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="16b44-127">A continuación, puede pasar la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> cadena "RSA" al método y utilizar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="16b44-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="16b44-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16b44-128">See also</span></span>

- [<span data-ttu-id="16b44-129">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="16b44-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="16b44-130">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="16b44-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="16b44-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="16b44-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="16b44-132">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="16b44-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
