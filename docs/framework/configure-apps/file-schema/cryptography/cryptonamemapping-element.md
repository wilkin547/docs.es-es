---
description: 'Más información acerca de: <cryptoNameMapping> elemento'
title: <cryptoNameMapping> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: b7dac458fdda0aabf36df96b43dca1529ffe4743
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698913"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="7a930-103">\<cryptoNameMapping> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="7a930-103">\<cryptoNameMapping> Element</span></span>

<span data-ttu-id="7a930-104">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="7a930-104">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="7a930-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a930-105">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a930-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7a930-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7a930-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7a930-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a930-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7a930-108">Attributes</span></span>  

 <span data-ttu-id="7a930-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a930-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7a930-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a930-110">Child Elements</span></span>  
  
|<span data-ttu-id="7a930-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a930-111">Element</span></span>|<span data-ttu-id="7a930-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a930-112">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="7a930-113">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="7a930-113">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="7a930-114">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="7a930-114">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a930-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7a930-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7a930-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a930-116">Element</span></span>|<span data-ttu-id="7a930-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a930-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7a930-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a930-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7a930-119">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="7a930-119">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="7a930-120">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="7a930-120">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="7a930-121">Contiene el \<cryptographySettings> elemento.</span><span class="sxs-lookup"><span data-stu-id="7a930-121">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7a930-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a930-122">Example</span></span>  

 <span data-ttu-id="7a930-123">En el ejemplo siguiente se muestra cómo usar el **\<cryptoNameMapping>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7a930-123">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="7a930-124">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="7a930-124">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7a930-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a930-125">See also</span></span>

- [<span data-ttu-id="7a930-126">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7a930-126">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7a930-127">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="7a930-127">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7a930-128">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="7a930-128">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="7a930-129">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="7a930-129">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
