---
description: 'Más información acerca de: <cryptoClass> elemento'
title: <cryptoClass> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: 503a079ea78a71a11e4c750a629cf67c9244a25d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698941"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="83a11-103">\<cryptoClass> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="83a11-103">\<cryptoClass> Element</span></span>

<span data-ttu-id="83a11-104">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="83a11-104">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="83a11-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83a11-105">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83a11-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83a11-106">Attributes and Elements</span></span>  

 <span data-ttu-id="83a11-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83a11-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83a11-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="83a11-108">Attributes</span></span>  
  
|<span data-ttu-id="83a11-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="83a11-109">Attribute</span></span>|<span data-ttu-id="83a11-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="83a11-110">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="83a11-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="83a11-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="83a11-112">Contiene la información de la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="83a11-112">Contains the information for the cryptography class.</span></span> <span data-ttu-id="83a11-113">Use este atributo para proporcionar un nombre corto para la clase.</span><span class="sxs-lookup"><span data-stu-id="83a11-113">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="83a11-114">Debe especificar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="83a11-114">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83a11-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83a11-115">Child Elements</span></span>  

 <span data-ttu-id="83a11-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83a11-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83a11-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83a11-117">Parent Elements</span></span>  
  
|<span data-ttu-id="83a11-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="83a11-118">Element</span></span>|<span data-ttu-id="83a11-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="83a11-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83a11-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83a11-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="83a11-121">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el [\<nameEntry>](nameentry-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="83a11-121">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="83a11-122">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="83a11-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="83a11-123">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="83a11-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="83a11-124">Contiene el [\<cryptographySettings>](cryptographysettings-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="83a11-124">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="83a11-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83a11-125">Example</span></span>  

 <span data-ttu-id="83a11-126">En el ejemplo siguiente se muestra cómo usar el **\<cryptoClass>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="83a11-126">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="83a11-127">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="83a11-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83a11-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="83a11-128">See also</span></span>

- [<span data-ttu-id="83a11-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="83a11-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="83a11-130">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="83a11-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83a11-131">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="83a11-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="83a11-132">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="83a11-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
