---
description: 'Más información acerca de: <cryptoClasses> elemento'
title: <cryptoClasses> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 5ae9b85d477a71eedc3c8b32bba2b4639414163c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698926"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="3d9a9-103">\<cryptoClasses> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="3d9a9-103">\<cryptoClasses> Element</span></span>

<span data-ttu-id="3d9a9-104">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-104">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="3d9a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d9a9-105">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d9a9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3d9a9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3d9a9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d9a9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d9a9-108">Attributes</span></span>  

 <span data-ttu-id="3d9a9-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d9a9-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3d9a9-110">Child Elements</span></span>  
  
|<span data-ttu-id="3d9a9-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d9a9-111">Element</span></span>|<span data-ttu-id="3d9a9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d9a9-112">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="3d9a9-113">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-113">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d9a9-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d9a9-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3d9a9-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d9a9-115">Element</span></span>|<span data-ttu-id="3d9a9-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d9a9-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3d9a9-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="3d9a9-118">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="3d9a9-119">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="3d9a9-120">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-120">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3d9a9-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d9a9-121">Example</span></span>  

 <span data-ttu-id="3d9a9-122">En el ejemplo siguiente se muestra cómo usar el **\<cryptoClass>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-122">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="3d9a9-123">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="3d9a9-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d9a9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d9a9-124">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="3d9a9-125">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3d9a9-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3d9a9-126">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="3d9a9-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3d9a9-127">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="3d9a9-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="3d9a9-128">System. Security. Cryptography. CryptoConfig. CreateFromName</span><span class="sxs-lookup"><span data-stu-id="3d9a9-128">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="3d9a9-129">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="3d9a9-129">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
