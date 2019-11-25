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
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088658"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="3e5e2-102">\<elemento > cryptoClass</span><span class="sxs-lookup"><span data-stu-id="3e5e2-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="3e5e2-103">Contiene una clase de criptografía que tiene una asignación a un nombre descriptivo en el elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="3e5e2-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

<span data-ttu-id="3e5e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3e5e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3e5e2-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3e5e2-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="3e5e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="3e5e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="3e5e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping**](cryptonamemapping-element.md) ></span><span class="sxs-lookup"><span data-stu-id="3e5e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="3e5e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClasses**](cryptoclasses-element.md) ></span><span class="sxs-lookup"><span data-stu-id="3e5e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="3e5e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoClass >**</span><span class="sxs-lookup"><span data-stu-id="3e5e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3e5e2-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e5e2-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e5e2-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3e5e2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3e5e2-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e5e2-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3e5e2-113">Attributes</span></span>  
  
|<span data-ttu-id="3e5e2-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="3e5e2-114">Attribute</span></span>|<span data-ttu-id="3e5e2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e5e2-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="3e5e2-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="3e5e2-117">Contiene la información de la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="3e5e2-118">Use este atributo para proporcionar un nombre corto para la clase.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="3e5e2-119">Debe especificar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="3e5e2-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e5e2-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e5e2-120">Child Elements</span></span>  
 <span data-ttu-id="3e5e2-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e5e2-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e5e2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3e5e2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e5e2-123">Element</span></span>|<span data-ttu-id="3e5e2-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e5e2-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3e5e2-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="3e5e2-126">Contiene una lista de las clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="3e5e2-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="3e5e2-127">Contiene la configuración de criptografía.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="3e5e2-128">Contiene asignaciones de clases a nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="3e5e2-129">Contiene el elemento [\<cryptographySettings>](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="3e5e2-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3e5e2-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e5e2-130">Example</span></span>  
 <span data-ttu-id="3e5e2-131">En el ejemplo siguiente se muestra cómo usar el elemento **\<cryptoClass >** para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="3e5e2-132">Después, puede pasar la cadena "RSA" al método <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> y usar el método <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> para devolver un objeto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="3e5e2-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3e5e2-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e5e2-133">See also</span></span>

- [<span data-ttu-id="3e5e2-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3e5e2-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3e5e2-135">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="3e5e2-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3e5e2-136">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="3e5e2-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="3e5e2-137">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="3e5e2-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
