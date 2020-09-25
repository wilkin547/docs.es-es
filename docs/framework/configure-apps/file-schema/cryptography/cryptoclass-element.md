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
ms.openlocfilehash: f7fe6d02b4697af3a1d0d04471a2736045fc9ecc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181809"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="35d25-102">\<cryptoClass> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="35d25-102">\<cryptoClass> Element</span></span>

<span data-ttu-id="35d25-103">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="35d25-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="35d25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35d25-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35d25-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="35d25-105">Attributes and Elements</span></span>  

 <span data-ttu-id="35d25-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="35d25-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35d25-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="35d25-107">Attributes</span></span>  
  
|<span data-ttu-id="35d25-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="35d25-108">Attribute</span></span>|<span data-ttu-id="35d25-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="35d25-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="35d25-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="35d25-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="35d25-111">Contiene la información de la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="35d25-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="35d25-112">Use este atributo para proporcionar un nombre corto para la clase.</span><span class="sxs-lookup"><span data-stu-id="35d25-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="35d25-113">Debe especificar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="35d25-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35d25-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="35d25-114">Child Elements</span></span>  

 <span data-ttu-id="35d25-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="35d25-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35d25-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35d25-116">Parent Elements</span></span>  
  
|<span data-ttu-id="35d25-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="35d25-117">Element</span></span>|<span data-ttu-id="35d25-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="35d25-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35d25-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35d25-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="35d25-120">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="35d25-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="35d25-121">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="35d25-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="35d25-122">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="35d25-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="35d25-123">Contiene el [\<cryptographySettings>](cryptographysettings-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="35d25-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="35d25-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35d25-124">Example</span></span>  

 <span data-ttu-id="35d25-125">En el ejemplo siguiente se muestra cómo usar el **\<cryptoClass>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="35d25-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="35d25-126">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="35d25-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35d25-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="35d25-127">See also</span></span>

- [<span data-ttu-id="35d25-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="35d25-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="35d25-129">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="35d25-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="35d25-130">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="35d25-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="35d25-131">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="35d25-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
