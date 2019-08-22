---
title: Elemento <mscorlib> para la configuración de criptografía
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 312db8ea5ae4b66fd00faad1b788eac0356aeaa7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659595"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="ad19e-102">\<Elemento > mscorlib para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="ad19e-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="ad19e-103">Contiene el [ \<elemento > de cryptographySettings](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="ad19e-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="ad19e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ad19e-104">\<configuration></span></span>  
<span data-ttu-id="ad19e-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="ad19e-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad19e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad19e-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad19e-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ad19e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ad19e-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ad19e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad19e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ad19e-109">Attributes</span></span>  
 <span data-ttu-id="ad19e-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ad19e-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad19e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ad19e-111">Child Elements</span></span>  
  
|<span data-ttu-id="ad19e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad19e-112">Element</span></span>|<span data-ttu-id="ad19e-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ad19e-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="ad19e-114">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="ad19e-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad19e-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ad19e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ad19e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad19e-116">Element</span></span>|<span data-ttu-id="ad19e-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ad19e-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ad19e-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad19e-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ad19e-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad19e-119">Example</span></span>  
 <span data-ttu-id="ad19e-120">En el ejemplo siguiente se muestra cómo usar el  **\<elemento > mscorlib** para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ad19e-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ad19e-121">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="ad19e-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ad19e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad19e-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="ad19e-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ad19e-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ad19e-124">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="ad19e-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ad19e-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="ad19e-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="ad19e-126">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="ad19e-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
