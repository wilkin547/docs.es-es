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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155186"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="3cccf-102">Elemento \<mscorlib> para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="3cccf-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="3cccf-103">Contiene el [ \<cryptographySettings> elemento](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="3cccf-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="3cccf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cccf-104">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cccf-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3cccf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3cccf-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3cccf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cccf-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3cccf-107">Attributes</span></span>  
 <span data-ttu-id="3cccf-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3cccf-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3cccf-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3cccf-109">Child Elements</span></span>  
  
|<span data-ttu-id="3cccf-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cccf-110">Element</span></span>|<span data-ttu-id="3cccf-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cccf-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="3cccf-112">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="3cccf-112">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cccf-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3cccf-113">Parent Elements</span></span>  
  
|<span data-ttu-id="3cccf-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cccf-114">Element</span></span>|<span data-ttu-id="3cccf-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cccf-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3cccf-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3cccf-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3cccf-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cccf-117">Example</span></span>  
 <span data-ttu-id="3cccf-118">En el ejemplo siguiente se muestra cómo usar el **\<mscorlib>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3cccf-118">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="3cccf-119">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="3cccf-119">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3cccf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cccf-120">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="3cccf-121">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3cccf-121">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3cccf-122">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="3cccf-122">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3cccf-123">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="3cccf-123">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="3cccf-124">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="3cccf-124">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
