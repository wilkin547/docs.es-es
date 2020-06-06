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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155251"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="8beff-102">\<cryptoClasses> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="8beff-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="8beff-103">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8beff-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="8beff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8beff-104">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8beff-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8beff-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8beff-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8beff-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8beff-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8beff-107">Attributes</span></span>  
 <span data-ttu-id="8beff-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8beff-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8beff-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8beff-109">Child Elements</span></span>  
  
|<span data-ttu-id="8beff-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="8beff-110">Element</span></span>|<span data-ttu-id="8beff-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8beff-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="8beff-112">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="8beff-112">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8beff-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8beff-113">Parent Elements</span></span>  
  
|<span data-ttu-id="8beff-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="8beff-114">Element</span></span>|<span data-ttu-id="8beff-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8beff-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8beff-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8beff-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="8beff-117">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="8beff-117">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="8beff-118">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="8beff-118">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="8beff-119">Contiene el `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="8beff-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8beff-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8beff-120">Example</span></span>  
 <span data-ttu-id="8beff-121">En el ejemplo siguiente se muestra cómo usar el **\<cryptoClass>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8beff-121">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="8beff-122">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="8beff-122">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8beff-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8beff-123">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="8beff-124">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8beff-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8beff-125">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="8beff-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8beff-126">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="8beff-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="8beff-127">System. Security. Cryptography. CryptoConfig. CreateFromName</span><span class="sxs-lookup"><span data-stu-id="8beff-127">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="8beff-128">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="8beff-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
