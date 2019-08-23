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
ms.openlocfilehash: d8f4d4aa9c80990cdf858da9fcdf6465438866cf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927562"
---
# <a name="nameentry-element"></a><span data-ttu-id="efbef-102">\<Elemento nameEntry >, elemento</span><span class="sxs-lookup"><span data-stu-id="efbef-102">\<nameEntry> Element</span></span>
<span data-ttu-id="efbef-103">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="efbef-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="efbef-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="efbef-104">\<configuration></span></span>  
<span data-ttu-id="efbef-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="efbef-105">\<mscorlib></span></span>  
<span data-ttu-id="efbef-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="efbef-106">\<cryptographySettings></span></span>  
<span data-ttu-id="efbef-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="efbef-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="efbef-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="efbef-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efbef-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efbef-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efbef-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="efbef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="efbef-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="efbef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efbef-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="efbef-112">Attributes</span></span>  
  
|<span data-ttu-id="efbef-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="efbef-113">Attribute</span></span>|<span data-ttu-id="efbef-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="efbef-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="efbef-115">**name**</span><span class="sxs-lookup"><span data-stu-id="efbef-115">**name**</span></span>|<span data-ttu-id="efbef-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="efbef-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="efbef-117">Especifica el nombre descriptivo del algoritmo que implementa la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="efbef-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="efbef-118">**class**</span><span class="sxs-lookup"><span data-stu-id="efbef-118">**class**</span></span>|<span data-ttu-id="efbef-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="efbef-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="efbef-120">Especifica el valor para el atributo **Name** en el [ \<elemento > de cryptoClass](cryptoclass-element.md) .</span><span class="sxs-lookup"><span data-stu-id="efbef-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efbef-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="efbef-121">Child Elements</span></span>  
 <span data-ttu-id="efbef-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="efbef-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efbef-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="efbef-123">Parent Elements</span></span>  
  
|<span data-ttu-id="efbef-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="efbef-124">Element</span></span>|<span data-ttu-id="efbef-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="efbef-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="efbef-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="efbef-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="efbef-127">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="efbef-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efbef-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efbef-128">Remarks</span></span>  
 <span data-ttu-id="efbef-129">El atributo de **nombre** puede ser el nombre de una de las clases abstractas que <xref:System.Security.Cryptography> se encuentran en el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="efbef-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="efbef-130">Cuando se llama al método **Create** en una clase de criptografía abstracta, el nombre de la clase abstracta se pasa <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> al método.</span><span class="sxs-lookup"><span data-stu-id="efbef-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="efbef-131">**CreateFromName** devuelve una instancia del tipo indicado por el atributo de **clase** .</span><span class="sxs-lookup"><span data-stu-id="efbef-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="efbef-132">Si el atributo **Name** es un nombre corto, como RSA, puede usar ese nombre al llamar al método **CreateFromName** .</span><span class="sxs-lookup"><span data-stu-id="efbef-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efbef-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efbef-133">Example</span></span>  
 <span data-ttu-id="efbef-134">En el ejemplo siguiente se muestra cómo usar  **\<** el elemento > de elemento nameEntry para hacer referencia a una clase de criptografía y para configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="efbef-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="efbef-135">Después, puede pasar la cadena "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y usar el <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método para devolver un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="efbef-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="efbef-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="efbef-136">See also</span></span>

- [<span data-ttu-id="efbef-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="efbef-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="efbef-138">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="efbef-138">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="efbef-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="efbef-139">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="efbef-140">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="efbef-140">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
