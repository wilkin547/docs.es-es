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
ms.openlocfilehash: d1d805f7154c18dba2dcd4eb7228cc200d8da811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155186"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="ebeae-102">\<elemento mscorlib> para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="ebeae-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="ebeae-103">Contiene el [ \<elemento de> cryptographySettings](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="ebeae-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="ebeae-104">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="ebeae-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ebeae-105">&nbsp;&nbsp;**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="ebeae-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebeae-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebeae-106">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebeae-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ebeae-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ebeae-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ebeae-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebeae-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ebeae-109">Attributes</span></span>  
 <span data-ttu-id="ebeae-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ebeae-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ebeae-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ebeae-111">Child Elements</span></span>  
  
|<span data-ttu-id="ebeae-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ebeae-112">Element</span></span>|<span data-ttu-id="ebeae-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebeae-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="ebeae-114">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="ebeae-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ebeae-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ebeae-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ebeae-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="ebeae-116">Element</span></span>|<span data-ttu-id="ebeae-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebeae-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ebeae-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebeae-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ebeae-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebeae-119">Example</span></span>  
 <span data-ttu-id="ebeae-120">En el ejemplo siguiente \*\* \<\*\* se muestra cómo utilizar el elemento de>mscorlib para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ebeae-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ebeae-121">A continuación, puede pasar la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> cadena "RSA" al método y utilizar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="ebeae-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ebeae-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebeae-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="ebeae-123">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ebeae-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ebeae-124">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="ebeae-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ebeae-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="ebeae-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="ebeae-126">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="ebeae-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
