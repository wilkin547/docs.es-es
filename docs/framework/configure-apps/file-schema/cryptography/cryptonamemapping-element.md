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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155224"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="a3f47-102">\<cryptoNameMapping> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a3f47-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="a3f47-103">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="a3f47-103">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="a3f47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3f47-104">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3f47-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a3f47-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a3f47-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a3f47-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3f47-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a3f47-107">Attributes</span></span>  
 <span data-ttu-id="a3f47-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a3f47-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3f47-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a3f47-109">Child Elements</span></span>  
  
|<span data-ttu-id="a3f47-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3f47-110">Element</span></span>|<span data-ttu-id="a3f47-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3f47-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="a3f47-112">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a3f47-112">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="a3f47-113">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="a3f47-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3f47-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a3f47-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a3f47-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3f47-115">Element</span></span>|<span data-ttu-id="a3f47-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3f47-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a3f47-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3f47-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a3f47-118">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="a3f47-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="a3f47-119">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="a3f47-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="a3f47-120">Contiene el \<cryptographySettings> elemento.</span><span class="sxs-lookup"><span data-stu-id="a3f47-120">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a3f47-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3f47-121">Example</span></span>  
 <span data-ttu-id="a3f47-122">En el ejemplo siguiente se muestra cómo usar el **\<cryptoNameMapping>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3f47-122">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="a3f47-123">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="a3f47-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a3f47-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3f47-124">See also</span></span>

- [<span data-ttu-id="a3f47-125">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a3f47-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a3f47-126">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="a3f47-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a3f47-127">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="a3f47-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="a3f47-128">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="a3f47-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
