---
title: '&lt;cryptoClass&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 448e2c83f6897fd876bb79dfb781bcf4ddd2252b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptoclassgt-element"></a><span data-ttu-id="6f440-102">&lt;cryptoClass&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="6f440-102">&lt;cryptoClass&gt; Element</span></span>
<span data-ttu-id="6f440-103">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="6f440-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="6f440-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6f440-104">\<configuration></span></span>  
<span data-ttu-id="6f440-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="6f440-105">\<mscorlib></span></span>  
<span data-ttu-id="6f440-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="6f440-106">\<cryptographySettings></span></span>  
<span data-ttu-id="6f440-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="6f440-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="6f440-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="6f440-108">\<cryptoClasses></span></span>  
<span data-ttu-id="6f440-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="6f440-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f440-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f440-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f440-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6f440-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6f440-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6f440-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f440-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f440-113">Attributes</span></span>  
  
|<span data-ttu-id="6f440-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="6f440-114">Attribute</span></span>|<span data-ttu-id="6f440-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f440-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="6f440-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="6f440-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="6f440-117">Contiene la información de la clase criptográfica.</span><span class="sxs-lookup"><span data-stu-id="6f440-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="6f440-118">Utilice este atributo para proporcionar un nombre corto para la clase.</span><span class="sxs-lookup"><span data-stu-id="6f440-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="6f440-119">Debe especificar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="6f440-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f440-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f440-120">Child Elements</span></span>  
 <span data-ttu-id="6f440-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6f440-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f440-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6f440-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6f440-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f440-123">Element</span></span>|<span data-ttu-id="6f440-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f440-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6f440-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f440-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="6f440-126">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="6f440-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="6f440-127">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="6f440-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="6f440-128">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="6f440-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="6f440-129">Contiene el elemento [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="6f440-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6f440-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f440-130">Example</span></span>  
 <span data-ttu-id="6f440-131">El ejemplo siguiente se muestra cómo utilizar el  **\<cryptoClass >** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6f440-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="6f440-132">A continuación, puede pasar la cadena "RSA" a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y el uso el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="6f440-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6f440-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f440-133">See Also</span></span>  
 [<span data-ttu-id="6f440-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6f440-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6f440-135">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="6f440-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="6f440-136">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="6f440-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="6f440-137">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="6f440-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
