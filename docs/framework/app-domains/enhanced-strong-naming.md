---
title: Nombres seguros mejorados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 429a54340cef6d608692abd71311c012afe9a3d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="enhanced-strong-naming"></a><span data-ttu-id="ab418-102">Nombres seguros mejorados</span><span class="sxs-lookup"><span data-stu-id="ab418-102">Enhanced Strong Naming</span></span>
<span data-ttu-id="ab418-103">Una firma de nombre seguro es un mecanismo de identidad de .NET Framework para identificar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ab418-103">A strong name signature is an identity mechanism in the .NET Framework for identifying assemblies.</span></span> <span data-ttu-id="ab418-104">Es una firma digital de clave pública que se suele usar para comprobar la integridad de los datos que se pasan de un remitente (firmante) a un destinatario (comprobador).</span><span class="sxs-lookup"><span data-stu-id="ab418-104">It is a public-key digital signature that is typically used to verify the integrity of data being passed from an originator (signer) to a recipient (verifier).</span></span> <span data-ttu-id="ab418-105">Esta firma se usa como identidad única para un ensamblado y garantiza que las referencias al ensamblado no son ambiguas.</span><span class="sxs-lookup"><span data-stu-id="ab418-105">This signature is used as a unique identity for an assembly and ensures that references to the assembly are not ambiguous.</span></span> <span data-ttu-id="ab418-106">El ensamblado se firma como parte del proceso de compilación y, después, se comprueba cuando se carga.</span><span class="sxs-lookup"><span data-stu-id="ab418-106">The assembly is signed as part of the build process and then verified when it is loaded.</span></span>  
  
 <span data-ttu-id="ab418-107">Las firmas de nombre seguro ayudan a impedir que personas malintencionadas manipulen un ensamblado y vuelvan a firmarlo con la clave del firmante original.</span><span class="sxs-lookup"><span data-stu-id="ab418-107">Strong name signatures help prevent malicious parties from tampering with an assembly and then re-signing the assembly with the original signer’s key.</span></span> <span data-ttu-id="ab418-108">Pero las claves de nombre seguro no contienen información confiable sobre el publicador ni una jerarquía de certificados.</span><span class="sxs-lookup"><span data-stu-id="ab418-108">However, strong name keys don’t contain any reliable information about the publisher, nor do they contain a certificate hierarchy.</span></span> <span data-ttu-id="ab418-109">Una firma de nombre seguro no garantiza la confiabilidad de la persona que ha firmado el ensamblado ni indica si dicha persona era el propietario legítimo de la clave; solo indica que el propietario de la clave ha firmado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab418-109">A strong name signature does not guarantee the trustworthiness of the person who signed the assembly or indicate whether that person was a legitimate owner of the key; it indicates only that the owner of the key signed the assembly.</span></span> <span data-ttu-id="ab418-110">Por lo tanto, no se recomienda usar una firma de nombre seguro como validador de seguridad para código de terceros de confianza.</span><span class="sxs-lookup"><span data-stu-id="ab418-110">Therefore, we do not recommend using a strong name signature as a security validator for trusting third-party code.</span></span> <span data-ttu-id="ab418-111">La manera recomendada de autenticar el código es Microsoft Authenticode.</span><span class="sxs-lookup"><span data-stu-id="ab418-111">Microsoft Authenticode is the recommended way to authenticate code.</span></span>  
  
## <a name="limitations-of-conventional-strong-names"></a><span data-ttu-id="ab418-112">Limitaciones de los nombres seguros convencionales</span><span class="sxs-lookup"><span data-stu-id="ab418-112">Limitations of Conventional Strong Names</span></span>  
 <span data-ttu-id="ab418-113">La tecnología de nomenclatura segura usada en las versiones anteriores a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] tiene las limitaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab418-113">The strong naming technology used in versions before the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] has the following shortcomings:</span></span>  
  
-   <span data-ttu-id="ab418-114">Las claves se encuentran constantemente bajo ataque, y las técnicas y el hardware mejorados hacen que sea más fácil deducir una clave privada a partir de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="ab418-114">Keys are constantly under attack, and improved techniques and hardware make it easier to infer a private key from a public key.</span></span> <span data-ttu-id="ab418-115">Para protegerse contra los ataques, son necesarias claves más largas.</span><span class="sxs-lookup"><span data-stu-id="ab418-115">To guard against attacks, larger keys are necessary.</span></span> <span data-ttu-id="ab418-116">Las versiones de .NET Framework anteriores a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ofrecen la posibilidad de firmar con una clave de cualquier tamaño (el tamaño predeterminado es de 1024 bits), pero si se firma un ensamblado con una clave nueva se interrumpen todos los binarios que hacen referencia a la identidad anterior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab418-116">.NET Framework versions before the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] provide the ability to sign with any size key (the default size is 1024 bits), but signing an assembly with a new key breaks all binaries that reference the older identity of the assembly.</span></span> <span data-ttu-id="ab418-117">Por lo tanto, es muy difícil actualizar el tamaño de una clave de firma si quiere mantener la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ab418-117">Therefore, it is extremely difficult to upgrade the size of a signing key if you want to maintain compatibility.</span></span>  
  
-   <span data-ttu-id="ab418-118">La firma con nombre seguro solo admite el algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="ab418-118">Strong name signing supports only the SHA-1 algorithm.</span></span> <span data-ttu-id="ab418-119">Recientemente se ha descubierto que SHA-1 no es adecuado para las aplicaciones de hash seguro.</span><span class="sxs-lookup"><span data-stu-id="ab418-119">SHA-1 has recently been found to be inadequate for secure hashing applications.</span></span> <span data-ttu-id="ab418-120">Por lo tanto, es necesario un algoritmo más seguro (SHA-256 o superior).</span><span class="sxs-lookup"><span data-stu-id="ab418-120">Therefore, a stronger algorithm (SHA-256 or greater) is necessary.</span></span> <span data-ttu-id="ab418-121">Es posible que SHA-1 pierda su compatibilidad con FIPS, lo que causaría problemas a los clientes que deciden usar solo algoritmos y software compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="ab418-121">It is possible that SHA-1 will lose its FIPS-compliant standing, which would present problems for those who choose to use only FIPS-compliant software and algorithms.</span></span>  
  
## <a name="advantages-of-enhanced-strong-names"></a><span data-ttu-id="ab418-122">Ventajas de los nombres seguros mejorados</span><span class="sxs-lookup"><span data-stu-id="ab418-122">Advantages of Enhanced Strong Names</span></span>  
 <span data-ttu-id="ab418-123">Las principales ventajas de los nombres seguros mejorados son la compatibilidad con los nombres seguros existentes y la capacidad de afirmar que una identidad es equivalente a otra:</span><span class="sxs-lookup"><span data-stu-id="ab418-123">The main advantages of enhanced strong names are compatibility with pre-existing strong names and the ability to claim that one identity is equivalent to another:</span></span>  
  
-   <span data-ttu-id="ab418-124">Los desarrolladores que ya tengan ensamblados firmados pueden migrar sus identidades a los algoritmos SHA-2 y mantener la compatibilidad con los ensamblados que hacen referencia a identidades anteriores.</span><span class="sxs-lookup"><span data-stu-id="ab418-124">Developers who have pre-existing signed assemblies can migrate their identities to the SHA-2 algorithms while maintaining compatibility with assemblies that reference the old identities.</span></span>  
  
-   <span data-ttu-id="ab418-125">Los desarrolladores que creen ensamblados y no se vean afectados por las firmas de nombre seguro existentes pueden usar los algoritmos SHA-2, que son más seguros, y firmar los ensamblados tal como han hecho siempre.</span><span class="sxs-lookup"><span data-stu-id="ab418-125">Developers who create new assemblies and are not concerned with pre-existing strong name signatures can use the more secure SHA-2 algorithms and sign the assemblies as they always have.</span></span>  
  
## <a name="using-enhanced-strong-names"></a><span data-ttu-id="ab418-126">Usar nombres seguros mejorados</span><span class="sxs-lookup"><span data-stu-id="ab418-126">Using Enhanced Strong Names</span></span>  
 <span data-ttu-id="ab418-127">Las claves de nombre seguro se componen de una clave de firma y una clave de identidad.</span><span class="sxs-lookup"><span data-stu-id="ab418-127">Strong name keys consist of a signature key and an identity key.</span></span> <span data-ttu-id="ab418-128">El ensamblado se firma con la clave de firma y se identifica mediante la clave de identidad.</span><span class="sxs-lookup"><span data-stu-id="ab418-128">The assembly is signed with the signature key and is identified by the identity key.</span></span> <span data-ttu-id="ab418-129">Antes de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], estas dos claves eran idénticas.</span><span class="sxs-lookup"><span data-stu-id="ab418-129">Prior to the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], these two keys were identical.</span></span> <span data-ttu-id="ab418-130">A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], la clave de identidad sigue siendo la misma que en versiones anteriores de .NET Framework, pero la clave de firma se ha mejorado con un algoritmo hash más seguro.</span><span class="sxs-lookup"><span data-stu-id="ab418-130">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the identity key remains the same as in earlier .NET Framework versions, but the signature key is enhanced with a stronger hash algorithm.</span></span> <span data-ttu-id="ab418-131">Además, la clave de firma se firma con la clave de identidad para crear una contrafirma.</span><span class="sxs-lookup"><span data-stu-id="ab418-131">In addition, the signature key is signed with the identity key to create a counter-signature.</span></span>  
  
 <span data-ttu-id="ab418-132">El atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> permite que los metadatos del ensamblado usen la clave pública existente para la identidad del ensamblado, lo que permite que las referencias anteriores del ensamblado sigan funcionando.</span><span class="sxs-lookup"><span data-stu-id="ab418-132">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute enables the assembly metadata to use the pre-existing public key for assembly identity, which allows old assembly references to continue to work.</span></span>  <span data-ttu-id="ab418-133">El atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> usa la contrafirma para asegurarse de que el propietario de la clave de firma nueva también es el propietario de la clave de identidad anterior.</span><span class="sxs-lookup"><span data-stu-id="ab418-133">The <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute uses the counter-signature to ensure that the owner of the new signature key is also the owner of the old identity key.</span></span>  
  
### <a name="signing-with-sha-2-without-key-migration"></a><span data-ttu-id="ab418-134">Firmar con SHA-2 (sin migración de clave)</span><span class="sxs-lookup"><span data-stu-id="ab418-134">Signing with SHA-2, Without Key Migration</span></span>  
 <span data-ttu-id="ab418-135">Ejecute los comandos siguientes desde una ventana del símbolo del sistema para firmar un ensamblado sin migrar una firma de nombre seguro:</span><span class="sxs-lookup"><span data-stu-id="ab418-135">Run the following commands from a Command Prompt window to sign an assembly without migrating a strong name signature:</span></span>  
  
1.  <span data-ttu-id="ab418-136">Genere la nueva clave de identidad (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="ab418-136">Generate the new identity key (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  <span data-ttu-id="ab418-137">Extraiga la clave pública de identidad y especifique que se debe usar un algoritmo SHA-2 al firmar con esta clave.</span><span class="sxs-lookup"><span data-stu-id="ab418-137">Extract the identity public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  <span data-ttu-id="ab418-138">Retrase la firma del ensamblado con el archivo de clave pública de identidad.</span><span class="sxs-lookup"><span data-stu-id="ab418-138">Delay-sign the assembly with the identity public key file.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  <span data-ttu-id="ab418-139">Vuelva a firmar el ensamblado con el par de claves de identidad completa.</span><span class="sxs-lookup"><span data-stu-id="ab418-139">Re-sign the assembly with the full identity key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a><span data-ttu-id="ab418-140">Firmar con SHA-2 (con migración de clave)</span><span class="sxs-lookup"><span data-stu-id="ab418-140">Signing with SHA-2, with Key Migration</span></span>  
 <span data-ttu-id="ab418-141">Ejecute los comandos siguientes desde una ventana del símbolo del sistema para firmar un ensamblado con una firma de nombre seguro migrada.</span><span class="sxs-lookup"><span data-stu-id="ab418-141">Run the following commands from a Command Prompt window to sign an assembly with a migrated strong name signature.</span></span>  
  
1.  <span data-ttu-id="ab418-142">Genere un par de claves de identidad y firma (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="ab418-142">Generate an identity and signature key pair (if necessary).</span></span>  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  <span data-ttu-id="ab418-143">Extraiga la clave pública de firma y especifique que se debe usar un algoritmo SHA-2 al firmar con esta clave.</span><span class="sxs-lookup"><span data-stu-id="ab418-143">Extract the signature public key, and specify that a SHA-2 algorithm should be used when signing with this key.</span></span>  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  <span data-ttu-id="ab418-144">Extraiga la clave pública de identidad, que determina el algoritmo hash que genera una contrafirma.</span><span class="sxs-lookup"><span data-stu-id="ab418-144">Extract the identity public key, which determines the hash algorithm that generates a counter-signature.</span></span>  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  <span data-ttu-id="ab418-145">Genere los parámetros para un atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> y adjunte el atributo al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab418-145">Generate the parameters for a <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute, and attach the attribute to the assembly.</span></span>  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  <span data-ttu-id="ab418-146">Retrase la firma del ensamblado con la clave pública de identidad.</span><span class="sxs-lookup"><span data-stu-id="ab418-146">Delay-sign the assembly with the identity public key.</span></span>  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6.  <span data-ttu-id="ab418-147">Firme por completo el ensamblado con el par de claves de firma.</span><span class="sxs-lookup"><span data-stu-id="ab418-147">Fully sign the assembly with the signature key pair.</span></span>  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ab418-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab418-148">See Also</span></span>  
 [<span data-ttu-id="ab418-149">Crear y utilizar ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="ab418-149">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
