---
title: <cryptoNameMapping> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: 4b3495d17e07ca611a384bf958ee06e928eb2506
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088015"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="04637-102">\<elemento > cryptoNameMapping</span><span class="sxs-lookup"><span data-stu-id="04637-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="04637-103">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="04637-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="04637-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04637-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04637-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="04637-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="04637-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="04637-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="04637-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoNameMapping >**</span><span class="sxs-lookup"><span data-stu-id="04637-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="04637-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04637-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04637-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="04637-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04637-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="04637-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04637-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="04637-111">Attributes</span></span>  
 <span data-ttu-id="04637-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="04637-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="04637-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04637-113">Child Elements</span></span>  
  
|<span data-ttu-id="04637-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="04637-114">Element</span></span>|<span data-ttu-id="04637-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="04637-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="04637-116">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="04637-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="04637-117">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="04637-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04637-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04637-118">Parent Elements</span></span>  
  
|<span data-ttu-id="04637-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="04637-119">Element</span></span>|<span data-ttu-id="04637-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="04637-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="04637-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04637-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="04637-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="04637-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="04637-123">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="04637-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="04637-124">Contiene el elemento \<> cryptographySettings.</span><span class="sxs-lookup"><span data-stu-id="04637-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="04637-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04637-125">Example</span></span>  
 <span data-ttu-id="04637-126">En el ejemplo siguiente se muestra cómo usar el elemento **\<cryptoNameMapping >** para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="04637-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="04637-127">Después, puede pasar la cadena "RSA" al método <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> y usar el método <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> para devolver un objeto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="04637-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04637-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="04637-128">See also</span></span>

- [<span data-ttu-id="04637-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="04637-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="04637-130">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="04637-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="04637-131">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="04637-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="04637-132">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="04637-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
