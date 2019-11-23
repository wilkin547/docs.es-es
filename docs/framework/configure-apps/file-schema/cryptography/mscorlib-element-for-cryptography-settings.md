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
ms.openlocfilehash: 4e2159cda5f35b5795804dede09ec17d07d71b23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699747"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="a5488-102">\<elemento > mscorlib para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="a5488-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="a5488-103">Contiene el [elemento\<> cryptographySettings](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="a5488-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="a5488-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a5488-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a5488-105">&nbsp;&nbsp; **\<mscorlib >**</span><span class="sxs-lookup"><span data-stu-id="a5488-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5488-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5488-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5488-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a5488-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a5488-108">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a5488-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5488-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5488-109">Attributes</span></span>  
 <span data-ttu-id="a5488-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a5488-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5488-111">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="a5488-111">Child Elements</span></span>  
  
|<span data-ttu-id="a5488-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5488-112">Element</span></span>|<span data-ttu-id="a5488-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5488-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="a5488-114">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="a5488-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5488-115">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="a5488-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a5488-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5488-116">Element</span></span>|<span data-ttu-id="a5488-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5488-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a5488-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5488-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a5488-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5488-119">Example</span></span>  
 <span data-ttu-id="a5488-120">En el ejemplo siguiente se muestra cómo usar el elemento **\<mscorlib >** para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5488-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="a5488-121">Después, puede pasar la cadena "RSA" al método <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> y usar el método <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> para devolver un objeto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="a5488-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5488-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5488-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="a5488-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a5488-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a5488-124">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="a5488-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a5488-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="a5488-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="a5488-126">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="a5488-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
