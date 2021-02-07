---
description: 'Más información acerca <mscorlib> de: elemento para la configuración de criptografía'
title: Elemento <mscorlib> para la configuración de criptografía
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 7606cdd1349c7594b5303832eed59ac51c1ddfe6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698900"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="9127a-103">Elemento \<mscorlib> para la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="9127a-103">\<mscorlib> Element for Cryptography Settings</span></span>

<span data-ttu-id="9127a-104">Contiene el [ \<cryptographySettings> elemento](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="9127a-104">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="9127a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9127a-105">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9127a-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9127a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9127a-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9127a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9127a-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9127a-108">Attributes</span></span>  

 <span data-ttu-id="9127a-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9127a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9127a-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9127a-110">Child Elements</span></span>  
  
|<span data-ttu-id="9127a-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="9127a-111">Element</span></span>|<span data-ttu-id="9127a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9127a-112">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="9127a-113">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="9127a-113">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9127a-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9127a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9127a-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9127a-115">Element</span></span>|<span data-ttu-id="9127a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9127a-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9127a-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9127a-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9127a-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9127a-118">Example</span></span>  

 <span data-ttu-id="9127a-119">En el ejemplo siguiente se muestra cómo usar el **\<mscorlib>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9127a-119">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="9127a-120">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="9127a-120">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9127a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9127a-121">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="9127a-122">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9127a-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9127a-123">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="9127a-123">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9127a-124">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="9127a-124">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="9127a-125">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="9127a-125">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
