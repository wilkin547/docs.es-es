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
ms.openlocfilehash: 1788205997d0dc49df172c9dfe48faceb8fc3290
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201790"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="d0675-102">Elemento \<mscorlib> para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="d0675-102">\<mscorlib> Element for Cryptography Settings</span></span>

<span data-ttu-id="d0675-103">Contiene el [ \<cryptographySettings> elemento](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="d0675-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="d0675-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0675-104">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0675-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d0675-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d0675-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d0675-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0675-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d0675-107">Attributes</span></span>  

 <span data-ttu-id="d0675-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d0675-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0675-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d0675-109">Child Elements</span></span>  
  
|<span data-ttu-id="d0675-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0675-110">Element</span></span>|<span data-ttu-id="d0675-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0675-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="d0675-112">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="d0675-112">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0675-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d0675-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d0675-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0675-114">Element</span></span>|<span data-ttu-id="d0675-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0675-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d0675-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0675-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0675-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0675-117">Example</span></span>  

 <span data-ttu-id="d0675-118">En el ejemplo siguiente se muestra cómo usar el **\<mscorlib>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d0675-118">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="d0675-119">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="d0675-119">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0675-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0675-120">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="d0675-121">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d0675-121">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d0675-122">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="d0675-122">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d0675-123">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="d0675-123">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="d0675-124">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="d0675-124">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
