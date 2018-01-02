---
title: "&lt;mscorlib&gt; , elemento de configuración de criptografía"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 18948d538b01304e90cac3b36988ccf29a586da0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a><span data-ttu-id="4dadd-102">&lt;mscorlib&gt; , elemento de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="4dadd-102">&lt;mscorlib&gt; Element for Cryptography Settings</span></span>
<span data-ttu-id="4dadd-103">Contiene el [ \<cryptographySettings > elemento](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="4dadd-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="4dadd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4dadd-104">\<configuration></span></span>  
<span data-ttu-id="4dadd-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="4dadd-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dadd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dadd-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dadd-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4dadd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4dadd-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4dadd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dadd-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4dadd-109">Attributes</span></span>  
 <span data-ttu-id="4dadd-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4dadd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4dadd-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4dadd-111">Child Elements</span></span>  
  
|<span data-ttu-id="4dadd-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dadd-112">Element</span></span>|<span data-ttu-id="4dadd-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4dadd-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="4dadd-114">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="4dadd-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4dadd-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4dadd-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4dadd-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dadd-116">Element</span></span>|<span data-ttu-id="4dadd-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4dadd-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4dadd-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4dadd-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4dadd-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4dadd-119">Example</span></span>  
 <span data-ttu-id="4dadd-120">En el ejemplo siguiente se muestra cómo utilizar el  **\<mscorlib >** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4dadd-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="4dadd-121">A continuación, puede pasar la cadena "RSA" a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y el uso el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="4dadd-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4dadd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dadd-122">See Also</span></span>  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="4dadd-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4dadd-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="4dadd-124">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="4dadd-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="4dadd-125">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="4dadd-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="4dadd-126">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="4dadd-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
