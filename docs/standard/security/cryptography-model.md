---
title: Modelo de criptografía de .NET
description: Revise las implementaciones de los algoritmos criptográficos habituales en .NET. Obtenga información sobre el modelo de criptografía extensible de herencia de objetos, diseño de secuencias & configuración.
ms.date: 02/26/2021
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: 2208e36ac4521f43cfd2960d92588c8349a119ca
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106935"
---
# <a name="net-cryptography-model"></a><span data-ttu-id="ccf40-104">Modelo de criptografía de .NET</span><span class="sxs-lookup"><span data-stu-id="ccf40-104">.NET cryptography model</span></span>

<span data-ttu-id="ccf40-105">.NET proporciona implementaciones de muchos algoritmos criptográficos estándar y el modelo de criptografía de .NET es extensible.</span><span class="sxs-lookup"><span data-stu-id="ccf40-105">.NET provides implementations of many standard cryptographic algorithms, and the .NET cryptography model is extensible.</span></span>

## <a name="object-inheritance"></a><span data-ttu-id="ccf40-106">Herencia de objetos</span><span class="sxs-lookup"><span data-stu-id="ccf40-106">Object inheritance</span></span>

<span data-ttu-id="ccf40-107">El sistema de criptografía de .NET implementa un patrón extensible de herencia de clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ccf40-107">The .NET cryptography system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="ccf40-108">La jerarquía es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ccf40-108">The hierarchy is as follows:</span></span>

- <span data-ttu-id="ccf40-109">Clase de tipo de algoritmo, como <xref:System.Security.Cryptography.SymmetricAlgorithm> ,  <xref:System.Security.Cryptography.AsymmetricAlgorithm> o <xref:System.Security.Cryptography.HashAlgorithm> .</span><span class="sxs-lookup"><span data-stu-id="ccf40-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm>, or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="ccf40-110">Este nivel es abstracto.</span><span class="sxs-lookup"><span data-stu-id="ccf40-110">This level is abstract.</span></span>

- <span data-ttu-id="ccf40-111">Clase de algoritmo que hereda de una clase de tipo de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> o <xref:System.Security.Cryptography.ECDiffieHellman>.</span><span class="sxs-lookup"><span data-stu-id="ccf40-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="ccf40-112">Este nivel es abstracto.</span><span class="sxs-lookup"><span data-stu-id="ccf40-112">This level is abstract.</span></span>

- <span data-ttu-id="ccf40-113">Implementación de una clase de algoritmo que hereda de una clase de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> o <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="ccf40-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="ccf40-114">Este nivel está completamente implementado.</span><span class="sxs-lookup"><span data-stu-id="ccf40-114">This level is fully implemented.</span></span>

<span data-ttu-id="ccf40-115">Este patrón de clases derivadas le permite agregar un nuevo algoritmo o una nueva implementación de un algoritmo existente.</span><span class="sxs-lookup"><span data-stu-id="ccf40-115">This pattern of derived classes lets you add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="ccf40-116">Por ejemplo, para crear un nuevo algoritmo de clave pública, heredaría de la clase <xref:System.Security.Cryptography.AsymmetricAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="ccf40-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="ccf40-117">Para crear una nueva implementación de un algoritmo específico, crearía una clase derivada no abstracta de ese algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ccf40-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>

## <a name="how-algorithms-are-implemented-in-net"></a><span data-ttu-id="ccf40-118">Cómo se implementan los algoritmos en .NET</span><span class="sxs-lookup"><span data-stu-id="ccf40-118">How algorithms are implemented in .NET</span></span>

<span data-ttu-id="ccf40-119">Como ejemplo de las distintas implementaciones disponibles de un algoritmo, considere los algoritmos simétricos.</span><span class="sxs-lookup"><span data-stu-id="ccf40-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="ccf40-120">La base de todos los algoritmos simétricos es <xref:System.Security.Cryptography.SymmetricAlgorithm> , que es heredada por <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.TripleDES> y otras que ya no se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="ccf40-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.TripleDES>, and others that are no longer recommended.</span></span>

<span data-ttu-id="ccf40-121"><xref:System.Security.Cryptography.Aes> es heredado por <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> y <xref:System.Security.Cryptography.AesManaged> .</span><span class="sxs-lookup"><span data-stu-id="ccf40-121"><xref:System.Security.Cryptography.Aes> is inherited by <xref:System.Security.Cryptography.AesCryptoServiceProvider>, <xref:System.Security.Cryptography.AesCng>, and <xref:System.Security.Cryptography.AesManaged>.</span></span>

<span data-ttu-id="ccf40-122">En .NET Framework en Windows:</span><span class="sxs-lookup"><span data-stu-id="ccf40-122">In .NET Framework on Windows:</span></span>

* <span data-ttu-id="ccf40-123">`*CryptoServiceProvider` las clases de algoritmo, como <xref:System.Security.Cryptography.AesCryptoServiceProvider> , son contenedores en torno a la implementación de la API de criptografía de Windows (CAPI) de un algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ccf40-123">`*CryptoServiceProvider` algorithm classes, such as <xref:System.Security.Cryptography.AesCryptoServiceProvider>, are wrappers around the Windows Cryptography API (CAPI) implementation of an algorithm.</span></span>
* <span data-ttu-id="ccf40-124">`*Cng` las clases de algoritmo, como <xref:System.Security.Cryptography.ECDiffieHellmanCng> , son contenedores en torno a la implementación de Windows Cryptography Next Generation (CNG).</span><span class="sxs-lookup"><span data-stu-id="ccf40-124">`*Cng` algorithm classes, such as <xref:System.Security.Cryptography.ECDiffieHellmanCng>, are wrappers around the Windows Cryptography Next Generation (CNG) implementation.</span></span>
* <span data-ttu-id="ccf40-125">`*Managed` las clases, como <xref:System.Security.Cryptography.AesManaged> , se escriben completamente en código administrado.</span><span class="sxs-lookup"><span data-stu-id="ccf40-125">`*Managed` classes, such as <xref:System.Security.Cryptography.AesManaged>, are written entirely in managed code.</span></span> <span data-ttu-id="ccf40-126">`*Managed` las implementaciones no están certificadas por los estándares federales de procesamiento de información (FIPS) y pueden ser más lentas que las `*CryptoServiceProvider` `*Cng` clases contenedoras y.</span><span class="sxs-lookup"><span data-stu-id="ccf40-126">`*Managed` implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the `*CryptoServiceProvider` and `*Cng` wrapper classes.</span></span>

<span data-ttu-id="ccf40-127">En .NET Core y .NET 5 y versiones posteriores, todas las clases de implementación ( `*CryptoServiceProvider` , `*Managed` y `*Cng` ) son contenedores para los algoritmos del sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="ccf40-127">In .NET Core and .NET 5 and later versions, all implementation classes (`*CryptoServiceProvider`, `*Managed`, and `*Cng`) are wrappers for the operating system (OS) algorithms.</span></span> <span data-ttu-id="ccf40-128">Si los algoritmos de sistema operativo están certificados por FIPS, .NET usa algoritmos con certificación FIPS.</span><span class="sxs-lookup"><span data-stu-id="ccf40-128">If the OS algorithms are FIPS-certified, then .NET uses FIPS-certified algorithms.</span></span> <span data-ttu-id="ccf40-129">Para obtener más información, consulte [Criptografía multiplataforma](cross-platform-cryptography.md).</span><span class="sxs-lookup"><span data-stu-id="ccf40-129">For more information, see [Cross-Platform Cryptography](cross-platform-cryptography.md).</span></span>

<span data-ttu-id="ccf40-130">En la mayoría de los casos, no es necesario hacer referencia directamente a una clase de implementación de algoritmos, como `AesCryptoServiceProvider` .</span><span class="sxs-lookup"><span data-stu-id="ccf40-130">In most cases, you don't need to directly reference an algorithm implementation class, such as `AesCryptoServiceProvider`.</span></span> <span data-ttu-id="ccf40-131">Los métodos y las propiedades que normalmente necesita están en la clase de algoritmo base, como `Aes` .</span><span class="sxs-lookup"><span data-stu-id="ccf40-131">The methods and properties you typically need are on the base algorithm class, such as `Aes`.</span></span> <span data-ttu-id="ccf40-132">Cree una instancia de una clase de implementación predeterminada utilizando un Factory Method en la clase de algoritmo base y haga referencia a la clase de algoritmo base.</span><span class="sxs-lookup"><span data-stu-id="ccf40-132">Create an instance of a default implementation class by using a factory method on the base algorithm class, and refer to the base algorithm class.</span></span> <span data-ttu-id="ccf40-133">Por ejemplo, vea la línea de código resaltada en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ccf40-133">For example, see the highlighted line of code in the following example:</span></span>

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="20":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="17":::

## <a name="cryptographic-configuration"></a><span data-ttu-id="ccf40-134">Configuración criptográfica</span><span class="sxs-lookup"><span data-stu-id="ccf40-134">Cryptographic configuration</span></span>

<span data-ttu-id="ccf40-135">La configuración criptográfica le permite resolver una implementación específica de un algoritmo en un nombre de algoritmo, lo que permite la extensibilidad de las clases de criptografía de .NET.</span><span class="sxs-lookup"><span data-stu-id="ccf40-135">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET cryptography classes.</span></span> <span data-ttu-id="ccf40-136">Puede agregar su propia implementación de hardware o software de un algoritmo y asignar la implementación al nombre del algoritmo que quiera.</span><span class="sxs-lookup"><span data-stu-id="ccf40-136">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="ccf40-137">Si un algoritmo no se especifica en el archivo de configuración, se usa la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ccf40-137">If an algorithm is not specified in the configuration file, the default settings are used.</span></span>

## <a name="choose-an-algorithm"></a><span data-ttu-id="ccf40-138">Selección de un algoritmo</span><span class="sxs-lookup"><span data-stu-id="ccf40-138">Choose an algorithm</span></span>

<span data-ttu-id="ccf40-139">Puede seleccionar un algoritmo por diferentes motivos: por ejemplo, para proteger la integridad de los datos, para proteger la privacidad de los datos o para generar una clave.</span><span class="sxs-lookup"><span data-stu-id="ccf40-139">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="ccf40-140">Los algoritmos simétricos y hash están diseñados para proteger los datos por motivos de integridad (impedir los cambios) o por motivos de privacidad (impedir la visualización).</span><span class="sxs-lookup"><span data-stu-id="ccf40-140">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="ccf40-141">Los algoritmos hash se usan principalmente para proteger la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="ccf40-141">Hash algorithms are used primarily for data integrity.</span></span>

<span data-ttu-id="ccf40-142">Esta es una lista de los algoritmos recomendados en función de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="ccf40-142">Here is a list of recommended algorithms by application:</span></span>

- <span data-ttu-id="ccf40-143">Privacidad de los datos:</span><span class="sxs-lookup"><span data-stu-id="ccf40-143">Data privacy:</span></span>
  - <xref:System.Security.Cryptography.Aes>
- <span data-ttu-id="ccf40-144">Integridad de los datos:</span><span class="sxs-lookup"><span data-stu-id="ccf40-144">Data integrity:</span></span>
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- <span data-ttu-id="ccf40-145">Firma digital:</span><span class="sxs-lookup"><span data-stu-id="ccf40-145">Digital signature:</span></span>
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="ccf40-146">Intercambio de claves:</span><span class="sxs-lookup"><span data-stu-id="ccf40-146">Key exchange:</span></span>
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="ccf40-147">Generación de números aleatorios:</span><span class="sxs-lookup"><span data-stu-id="ccf40-147">Random number generation:</span></span>
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- <span data-ttu-id="ccf40-148">Generar una clave a partir de una contraseña:</span><span class="sxs-lookup"><span data-stu-id="ccf40-148">Generating a key from a password:</span></span>
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a><span data-ttu-id="ccf40-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ccf40-149">See also</span></span>

- [<span data-ttu-id="ccf40-150">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="ccf40-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="ccf40-151">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="ccf40-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="ccf40-152">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="ccf40-152">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
