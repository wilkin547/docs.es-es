---
title: <cryptoClasses> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: c93fadf51297d59ab499e25de283700364903049
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155251"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="6656d-102">\<cryptoClasses> Element</span><span class="sxs-lookup"><span data-stu-id="6656d-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="6656d-103">Contiene una lista de clases de criptografía que [ \<](nameentry-element.md) tienen una asignación a un nombre descriptivo en el elemento nameEntry>.</span><span class="sxs-lookup"><span data-stu-id="6656d-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="6656d-104">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="6656d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6656d-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6656d-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="6656d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<criptografíaConfiguración>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="6656d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="6656d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>cryptoNameMapping**](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="6656d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="6656d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span><span class="sxs-lookup"><span data-stu-id="6656d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6656d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6656d-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6656d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6656d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6656d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6656d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6656d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="6656d-112">Attributes</span></span>  
 <span data-ttu-id="6656d-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6656d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6656d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6656d-114">Child Elements</span></span>  
  
|<span data-ttu-id="6656d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="6656d-115">Element</span></span>|<span data-ttu-id="6656d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6656d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6656d-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="6656d-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="6656d-118">Contiene una clase de criptografía que tiene \*\* \<\*\* una asignación a un nombre descriptivo en el elemento nameEntry>.</span><span class="sxs-lookup"><span data-stu-id="6656d-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6656d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6656d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6656d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6656d-120">Element</span></span>|<span data-ttu-id="6656d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6656d-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6656d-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6656d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="6656d-123">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="6656d-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="6656d-124">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="6656d-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="6656d-125">Contiene `cryptographySettings` el elemento.</span><span class="sxs-lookup"><span data-stu-id="6656d-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6656d-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6656d-126">Example</span></span>  
 <span data-ttu-id="6656d-127">En el ejemplo siguiente \*\* \<\*\* se muestra cómo utilizar el elemento cryptoClass>para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6656d-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="6656d-128">A continuación, puede pasar la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> cadena "RSA" al método y utilizar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="6656d-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6656d-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6656d-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="6656d-130">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="6656d-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6656d-131">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="6656d-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6656d-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6656d-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="6656d-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="6656d-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="6656d-134">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="6656d-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
