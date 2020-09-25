---
title: <nameEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 4341b1fcd3762e5aa55f0ba988f7f49d4b5cacd6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201777"
---
# <a name="nameentry-element"></a><span data-ttu-id="11c70-102">\<nameEntry> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="11c70-102">\<nameEntry> Element</span></span>

<span data-ttu-id="11c70-103">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="11c70-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**  
  
## <a name="syntax"></a><span data-ttu-id="11c70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11c70-104">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11c70-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="11c70-105">Attributes and Elements</span></span>  

 <span data-ttu-id="11c70-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="11c70-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11c70-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="11c70-107">Attributes</span></span>  
  
|<span data-ttu-id="11c70-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="11c70-108">Attribute</span></span>|<span data-ttu-id="11c70-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c70-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11c70-110">**name**</span><span class="sxs-lookup"><span data-stu-id="11c70-110">**name**</span></span>|<span data-ttu-id="11c70-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="11c70-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="11c70-112">Especifica el nombre descriptivo del algoritmo que implementa la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="11c70-112">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="11c70-113">**class**</span><span class="sxs-lookup"><span data-stu-id="11c70-113">**class**</span></span>|<span data-ttu-id="11c70-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="11c70-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="11c70-115">Especifica el valor para el atributo de **nombre** en el [\<cryptoClass>](cryptoclass-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="11c70-115">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11c70-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="11c70-116">Child Elements</span></span>  

 <span data-ttu-id="11c70-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="11c70-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11c70-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="11c70-118">Parent Elements</span></span>  
  
|<span data-ttu-id="11c70-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="11c70-119">Element</span></span>|<span data-ttu-id="11c70-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c70-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="11c70-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="11c70-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="11c70-122">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="11c70-122">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11c70-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="11c70-123">Remarks</span></span>  

 <span data-ttu-id="11c70-124">El atributo de **nombre** puede ser el nombre de una de las clases abstractas que se encuentran en el <xref:System.Security.Cryptography> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="11c70-124">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="11c70-125">Cuando se llama al método **Create** en una clase de criptografía abstracta, el nombre de la clase abstracta se pasa al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> método.</span><span class="sxs-lookup"><span data-stu-id="11c70-125">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="11c70-126">**CreateFromName** devuelve una instancia del tipo indicado por el atributo de **clase** .</span><span class="sxs-lookup"><span data-stu-id="11c70-126">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="11c70-127">Si el atributo **Name** es un nombre corto, como RSA, puede usar ese nombre al llamar al método **CreateFromName** .</span><span class="sxs-lookup"><span data-stu-id="11c70-127">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11c70-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11c70-128">Example</span></span>  

 <span data-ttu-id="11c70-129">En el ejemplo siguiente se muestra cómo usar el **\<nameEntry>** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11c70-129">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="11c70-130">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="11c70-130">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="11c70-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="11c70-131">See also</span></span>

- [<span data-ttu-id="11c70-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="11c70-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="11c70-133">Esquema de configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="11c70-133">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="11c70-134">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="11c70-134">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="11c70-135">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="11c70-135">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
