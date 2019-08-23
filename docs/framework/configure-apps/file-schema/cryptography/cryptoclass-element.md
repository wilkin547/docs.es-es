---
title: <cryptoClass> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: 6a868f62c6a327012a6225b86bf0103d178d6ab7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921168"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="59ae0-102">\<cryptoClass >, elemento</span><span class="sxs-lookup"><span data-stu-id="59ae0-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="59ae0-103">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="59ae0-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="59ae0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="59ae0-104">\<configuration></span></span>  
<span data-ttu-id="59ae0-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="59ae0-105">\<mscorlib></span></span>  
<span data-ttu-id="59ae0-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="59ae0-106">\<cryptographySettings></span></span>  
<span data-ttu-id="59ae0-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="59ae0-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="59ae0-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="59ae0-108">\<cryptoClasses></span></span>  
<span data-ttu-id="59ae0-109">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="59ae0-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ae0-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59ae0-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59ae0-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59ae0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="59ae0-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59ae0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59ae0-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="59ae0-113">Attributes</span></span>  
  
|<span data-ttu-id="59ae0-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="59ae0-114">Attribute</span></span>|<span data-ttu-id="59ae0-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59ae0-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="59ae0-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="59ae0-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="59ae0-117">Contiene la información de la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="59ae0-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="59ae0-118">Use este atributo para proporcionar un nombre corto para la clase.</span><span class="sxs-lookup"><span data-stu-id="59ae0-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="59ae0-119">Debe especificar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="59ae0-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59ae0-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59ae0-120">Child Elements</span></span>  
 <span data-ttu-id="59ae0-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59ae0-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59ae0-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59ae0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="59ae0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="59ae0-123">Element</span></span>|<span data-ttu-id="59ae0-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59ae0-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="59ae0-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59ae0-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="59ae0-126">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="59ae0-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="59ae0-127">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="59ae0-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="59ae0-128">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="59ae0-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="59ae0-129">Contiene el elemento [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="59ae0-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59ae0-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59ae0-130">Example</span></span>  
 <span data-ttu-id="59ae0-131">En el ejemplo siguiente se muestra cómo  **\<** usar el elemento > de cryptoClass para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59ae0-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="59ae0-132">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="59ae0-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59ae0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="59ae0-133">See also</span></span>

- [<span data-ttu-id="59ae0-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="59ae0-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="59ae0-135">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="59ae0-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="59ae0-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="59ae0-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="59ae0-137">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="59ae0-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
