---
title: Asignar nombres de algoritmo a clases de criptografía
description: Asignar nombres de algoritmo a clases de criptografía en .NET. Un desarrollador tiene cuatro opciones para crear un objeto de criptografía.
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 5a1d7acdd34182dd82f4dce66d136c4ef4de6e95
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105353"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="e304b-104">Asignar nombres de algoritmo a clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="e304b-104">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="e304b-105">Hay cuatro maneras en las que un programador puede crear un objeto de criptografía mediante el Windows SDK:</span><span class="sxs-lookup"><span data-stu-id="e304b-105">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="e304b-106">Cree un objeto con el operador **New** .</span><span class="sxs-lookup"><span data-stu-id="e304b-106">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="e304b-107">Cree un objeto que implemente un algoritmo de criptografía determinado llamando al método **Create** en la clase abstracta para ese algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e304b-107">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="e304b-108">Cree un objeto que implemente un algoritmo de criptografía determinado llamando al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="e304b-108">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="e304b-109">Cree un objeto que implemente una clase de algoritmos criptográficos (por ejemplo, un cifrado de bloques simétrico) mediante una llamada al método **Create** en la clase abstracta para ese tipo de algoritmo (por ejemplo, <xref:System.Security.Cryptography.SymmetricAlgorithm> ).</span><span class="sxs-lookup"><span data-stu-id="e304b-109">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="e304b-110">Por ejemplo, supongamos que un desarrollador desea calcular el hash SHA1 de un conjunto de bytes.</span><span class="sxs-lookup"><span data-stu-id="e304b-110">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="e304b-111">El <xref:System.Security.Cryptography> espacio de nombres contiene dos implementaciones del algoritmo SHA1, una implementación estrictamente administrada y otra que contiene CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="e304b-111">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="e304b-112">El desarrollador puede elegir crear una instancia de una implementación de SHA1 determinada (como <xref:System.Security.Cryptography.SHA1Managed> ) llamando al **nuevo** operador.</span><span class="sxs-lookup"><span data-stu-id="e304b-112">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="e304b-113">Sin embargo, si no importa qué clase carga la Common Language Runtime siempre y cuando la clase implemente el algoritmo hash SHA1, el desarrollador puede crear un objeto llamando al <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="e304b-113">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e304b-114">Este método llama a **System. Security. Cryptography. CryptoConfig. CreateFromName ("System. Security. Cryptography. SHA1")**, que debe devolver una implementación del algoritmo hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="e304b-114">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="e304b-115">El desarrollador también puede llamar a **System. Security. Cryptography. CryptoConfig. CreateFromName ("SHA1")** porque, de forma predeterminada, la configuración de criptografía incluye nombres cortos para los algoritmos que se incluyen en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e304b-115">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="e304b-116">Si no importa qué algoritmo hash se usa, el desarrollador puede llamar al <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> método, que devuelve un objeto que implementa una transformación hash.</span><span class="sxs-lookup"><span data-stu-id="e304b-116">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="e304b-117">Asignar nombres de algoritmo en archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e304b-117">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="e304b-118">De forma predeterminada, el tiempo de ejecución devuelve un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> objeto para los cuatro escenarios.</span><span class="sxs-lookup"><span data-stu-id="e304b-118">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="e304b-119">Sin embargo, un administrador del equipo puede cambiar el tipo de objeto que devuelven los métodos de los dos últimos escenarios.</span><span class="sxs-lookup"><span data-stu-id="e304b-119">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="e304b-120">Para ello, debe asignar un nombre de algoritmo descriptivo a la clase que desea utilizar en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e304b-120">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="e304b-121">En el ejemplo siguiente se muestra cómo configurar el tiempo de ejecución para que **System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. CREATEFROMNAME ("SHA1")** y **System. Security. Cryptography. HashAlgorithm. Create** devuelvan un `MySHA1HashClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="e304b-121">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="e304b-122">Puede especificar el nombre del atributo en el [ \> elemento<cryptoClass](./file-schema/cryptography/cryptoclass-element.md) (el ejemplo anterior nombra el atributo `MySHA1Hash` ).</span><span class="sxs-lookup"><span data-stu-id="e304b-122">You can specify the name of the attribute in the [<cryptoClass\> element](./file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="e304b-123">El valor del atributo en el **\<cryptoClass>** elemento es una cadena que el Common Language Runtime utiliza para buscar la clase.</span><span class="sxs-lookup"><span data-stu-id="e304b-123">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="e304b-124">Puede usar cualquier cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e304b-124">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="e304b-125">Muchos nombres de algoritmos se pueden asignar a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="e304b-125">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="e304b-126">El [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md) asigna una clase a un nombre de algoritmo descriptivo.</span><span class="sxs-lookup"><span data-stu-id="e304b-126">The [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="e304b-127">El atributo de **nombre** puede ser una cadena que se usa al llamar al método **System. Security. Cryptography. CryptoConfig. CreateFromName** o el nombre de una clase de criptografía abstracta en el <xref:System.Security.Cryptography> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e304b-127">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="e304b-128">El valor del atributo **Class** es el nombre del atributo en el **\<cryptoClass>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e304b-128">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e304b-129">Puede obtener un algoritmo SHA1 llamando a <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> o al método **Security. CryptoConfig. CreateFromName ("SHA1")** .</span><span class="sxs-lookup"><span data-stu-id="e304b-129">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="e304b-130">Cada método garantiza solo que devuelve un objeto que implementa el algoritmo SHA1.</span><span class="sxs-lookup"><span data-stu-id="e304b-130">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="e304b-131">No es necesario asignar cada nombre descriptivo de un algoritmo a la misma clase en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e304b-131">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="e304b-132">Para obtener una lista de los nombres predeterminados y las clases a las que se asignan, vea <xref:System.Security.Cryptography.CryptoConfig> .</span><span class="sxs-lookup"><span data-stu-id="e304b-132">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e304b-133">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="e304b-133">See also</span></span>

- [<span data-ttu-id="e304b-134">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="e304b-134">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e304b-135">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="e304b-135">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
