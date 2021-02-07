---
description: 'Más información acerca de: <nameEntry> elemento'
title: <nameEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 0ca227a2ba17a6b1e67fb75ec91aac9194b54737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730010"
---
# <a name="nameentry-element"></a><span data-ttu-id="8a2ee-103">\<nameEntry> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="8a2ee-103">\<nameEntry> Element</span></span>

<span data-ttu-id="8a2ee-104">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-104">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**  
  
## <a name="syntax"></a><span data-ttu-id="8a2ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a2ee-105">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a2ee-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a2ee-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8a2ee-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a2ee-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a2ee-108">Attributes</span></span>  
  
|<span data-ttu-id="8a2ee-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a2ee-109">Attribute</span></span>|<span data-ttu-id="8a2ee-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a2ee-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a2ee-111">**name**</span><span class="sxs-lookup"><span data-stu-id="8a2ee-111">**name**</span></span>|<span data-ttu-id="8a2ee-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="8a2ee-113">Especifica el nombre descriptivo del algoritmo que implementa la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-113">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="8a2ee-114">**class**</span><span class="sxs-lookup"><span data-stu-id="8a2ee-114">**class**</span></span>|<span data-ttu-id="8a2ee-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="8a2ee-116">Especifica el valor para el atributo de **nombre** en el [\<cryptoClass>](cryptoclass-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-116">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a2ee-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a2ee-117">Child Elements</span></span>  

 <span data-ttu-id="8a2ee-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a2ee-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a2ee-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8a2ee-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a2ee-120">Element</span></span>|<span data-ttu-id="8a2ee-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a2ee-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8a2ee-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="8a2ee-123">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a2ee-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a2ee-124">Remarks</span></span>  

 <span data-ttu-id="8a2ee-125">El atributo de **nombre** puede ser el nombre de una de las clases abstractas que se encuentran en el <xref:System.Security.Cryptography> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-125">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="8a2ee-126">Cuando se llama al método **Create** en una clase de criptografía abstracta, el nombre de la clase abstracta se pasa al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-126">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="8a2ee-127">**CreateFromName** devuelve una instancia del tipo indicado por el atributo de **clase** .</span><span class="sxs-lookup"><span data-stu-id="8a2ee-127">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="8a2ee-128">Si el atributo **Name** es un nombre corto, como RSA, puede usar ese nombre al llamar al método **CreateFromName** .</span><span class="sxs-lookup"><span data-stu-id="8a2ee-128">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a2ee-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a2ee-129">Example</span></span>  

 <span data-ttu-id="8a2ee-130">En el ejemplo siguiente se muestra cómo usar el **\<nameEntry>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-130">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="8a2ee-131">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="8a2ee-131">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8a2ee-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a2ee-132">See also</span></span>

- [<span data-ttu-id="8a2ee-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8a2ee-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8a2ee-134">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="8a2ee-134">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8a2ee-135">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="8a2ee-135">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="8a2ee-136">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="8a2ee-136">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
