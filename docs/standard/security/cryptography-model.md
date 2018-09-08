---
title: Modelo de criptografía de .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography [.NET Framework], model
- encryption [.NET Framework], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d74ce08197ac76a601202da8e35ca6f619207076
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44132018"
---
# <a name="net-framework-cryptography-model"></a><span data-ttu-id="7dfc1-102">Modelo de criptografía de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7dfc1-102">.NET Framework Cryptography Model</span></span>
<span data-ttu-id="7dfc1-103">.NET Framework proporciona implementaciones de numerosos algoritmos criptográficos estándar.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-103">The .NET Framework provides implementations of many standard cryptographic algorithms.</span></span> <span data-ttu-id="7dfc1-104">Estos algoritmos son fáciles de usar y tienen las propiedades predeterminadas más seguras.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-104">These algorithms are easy to use and have the safest possible default properties.</span></span> <span data-ttu-id="7dfc1-105">Además, el modelo de criptografía de .NET Framework de herencia de objetos, diseño de secuencias y configuración es muy extensible.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-105">In addition, the .NET Framework cryptography model of object inheritance, stream design, and configuration is extremely extensible.</span></span>  
  
## <a name="object-inheritance"></a><span data-ttu-id="7dfc1-106">Herencia de objetos</span><span class="sxs-lookup"><span data-stu-id="7dfc1-106">Object Inheritance</span></span>  
 <span data-ttu-id="7dfc1-107">El sistema de seguridad de .NET Framework implementa un patrón extensible de herencia de clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-107">The .NET Framework security system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="7dfc1-108">La jerarquía es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-108">The hierarchy is as follows:</span></span>  
  
-   <span data-ttu-id="7dfc1-109">Clase de tipo de algoritmo, como <xref:System.Security.Cryptography.SymmetricAlgorithm>, <xref:System.Security.Cryptography.AsymmetricAlgorithm> o <xref:System.Security.Cryptography.HashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm> or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="7dfc1-110">Este nivel es abstracto.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-110">This level is abstract.</span></span>  
  
-   <span data-ttu-id="7dfc1-111">Clase de algoritmo que hereda de una clase de tipo de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2> o <xref:System.Security.Cryptography.ECDiffieHellman>.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="7dfc1-112">Este nivel es abstracto.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-112">This level is abstract.</span></span>  
  
-   <span data-ttu-id="7dfc1-113">Implementación de una clase de algoritmo que hereda de una clase de algoritmo, como, por ejemplo, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> o <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="7dfc1-114">Este nivel está completamente implementado.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-114">This level is fully implemented.</span></span>  
  
 <span data-ttu-id="7dfc1-115">Si se usa este modelo de clases derivadas, es fácil agregar un nuevo algoritmo o una nueva implementación de un algoritmo existente.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-115">Using this pattern of derived classes, it is easy to add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="7dfc1-116">Por ejemplo, para crear un nuevo algoritmo de clave pública, heredaría de la clase <xref:System.Security.Cryptography.AsymmetricAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="7dfc1-117">Para crear una nueva implementación de un algoritmo específico, crearía una clase derivada no abstracta de ese algoritmo.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>  
  
## <a name="how-algorithms-are-implemented-in-the-net-framework"></a><span data-ttu-id="7dfc1-118">Cómo se implementan los algoritmos en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7dfc1-118">How Algorithms Are Implemented in the .NET Framework</span></span>  
 <span data-ttu-id="7dfc1-119">Como ejemplo de las distintas implementaciones disponibles de un algoritmo, considere los algoritmos simétricos.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="7dfc1-120">La base de todos los algoritmos simétricos es <xref:System.Security.Cryptography.SymmetricAlgorithm>, que heredan los siguientes algoritmos:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by the following algorithms:</span></span>  
  
1.  <xref:System.Security.Cryptography.Aes>  
  
2.  <xref:System.Security.Cryptography.DES>  
  
3.  <xref:System.Security.Cryptography.RC2>  
  
4.  <xref:System.Security.Cryptography.Rijndael>  
  
5.  <xref:System.Security.Cryptography.TripleDES>  
  
 <span data-ttu-id="7dfc1-121">Dos clases heredan <xref:System.Security.Cryptography.Aes>: <xref:System.Security.Cryptography.AesCryptoServiceProvider> y <xref:System.Security.Cryptography.AesManaged>.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-121"><xref:System.Security.Cryptography.Aes> is inherited by two classes: <xref:System.Security.Cryptography.AesCryptoServiceProvider> and <xref:System.Security.Cryptography.AesManaged>.</span></span> <span data-ttu-id="7dfc1-122">La clase <xref:System.Security.Cryptography.AesCryptoServiceProvider> es un contenedor que envuelve la implementación de Aes de la API de criptografía de Windows (CAPI), mientras que la clase <xref:System.Security.Cryptography.AesManaged> está escrita completamente en código administrado.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-122">The <xref:System.Security.Cryptography.AesCryptoServiceProvider> class is a wrapper around the Windows Cryptography API (CAPI) implementation of Aes, whereas the <xref:System.Security.Cryptography.AesManaged> class is written entirely in managed code.</span></span> <span data-ttu-id="7dfc1-123">También hay un tercer tipo de implementación, Cryptography Next Generation (CNG), además de las implementaciones administradas y de CAPI.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-123">There is also a third type of implementation, Cryptography Next Generation (CNG), in addition to the managed and CAPI implementations.</span></span> <span data-ttu-id="7dfc1-124">Un ejemplo de un algoritmo CNG es <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-124">An example of a CNG algorithm is <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="7dfc1-125">Los algoritmos CNG se encuentran disponibles en Windows Vista y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-125">CNG algorithms are available on Windows Vista and later.</span></span>  
  
 <span data-ttu-id="7dfc1-126">Puede elegir qué implementación es mejor para usted.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-126">You can choose which implementation is best for you.</span></span>  <span data-ttu-id="7dfc1-127">Las implementaciones administradas están disponibles en todas las plataformas compatibles con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-127">The managed implementations are available on all platforms that support the .NET Framework.</span></span>  <span data-ttu-id="7dfc1-128">Las implementaciones de CAPI están disponibles en sistemas operativos anteriores y ya no se desarrollan.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-128">The CAPI implementations are available on older operating systems, and are no longer being developed.</span></span> <span data-ttu-id="7dfc1-129">CNG es la última implementación, donde se lleva cabo el nuevo desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-129">CNG is the very latest implementation where new development will take place.</span></span> <span data-ttu-id="7dfc1-130">Sin embargo, las implementaciones administradas no disponen del certificado de Estándares de procesamiento de información federal (FIPS) y pueden ser más lentas que las clases contenedoras.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-130">However, the managed implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the wrapper classes.</span></span>  
  
## <a name="stream-design"></a><span data-ttu-id="7dfc1-131">Diseño de secuencias</span><span class="sxs-lookup"><span data-stu-id="7dfc1-131">Stream Design</span></span>  
 <span data-ttu-id="7dfc1-132">El Common Language Runtime usa un diseño orientado a secuencias para implementar algoritmos simétricos y algoritmos hash.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-132">The common language runtime uses a stream-oriented design for implementing symmetric algorithms and hash algorithms.</span></span> <span data-ttu-id="7dfc1-133">El núcleo de este diseño es la clase <xref:System.Security.Cryptography.CryptoStream>, que se deriva de la clase <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-133">The core of this design is the <xref:System.Security.Cryptography.CryptoStream> class, which derives from the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="7dfc1-134">Los objetos criptográficos basados en secuencias admiten una interfaz estándar única (`CryptoStream`) para controlar la parte de transferencia de datos del objeto.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-134">Stream-based cryptographic objects support a single standard interface (`CryptoStream`) for handling the data transfer portion of the object.</span></span> <span data-ttu-id="7dfc1-135">Como todos los objetos se crean en una interfaz estándar, puede encadenar varios objetos (como un objeto hash seguido de un objeto de cifrado) y puede realizar diversas operaciones en los datos sin necesidad de un almacenamiento intermedio para ellos.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-135">Because all the objects are built on a standard interface, you can chain together multiple objects (such as a hash object followed by an encryption object), and you can perform multiple operations on the data without needing any intermediate storage for it.</span></span> <span data-ttu-id="7dfc1-136">El modelo de transmisión por secuencias también permite crear objetos a partir de objetos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-136">The streaming model also enables you to build objects from smaller objects.</span></span> <span data-ttu-id="7dfc1-137">Por ejemplo, un algoritmo combinado de cifrado y hash puede verse como un solo objeto de secuencia, aunque este objeto podría generarse a partir de un conjunto de objetos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-137">For example, a combined encryption and hash algorithm can be viewed as a single stream object, although this object might be built from a set of stream objects.</span></span>  
  
## <a name="cryptographic-configuration"></a><span data-ttu-id="7dfc1-138">Configuración criptográfica</span><span class="sxs-lookup"><span data-stu-id="7dfc1-138">Cryptographic Configuration</span></span>  
 <span data-ttu-id="7dfc1-139">La configuración criptográfica le permite resolver una implementación específica de un algoritmo a un nombre de algoritmo, lo que permite la extensibilidad de las clases de criptografía de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-139">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET Framework cryptography classes.</span></span> <span data-ttu-id="7dfc1-140">Puede agregar su propia implementación de hardware o software de un algoritmo y asignar la implementación al nombre del algoritmo que quiera.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-140">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="7dfc1-141">Si un algoritmo no se especifica en el archivo de configuración, se usa la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-141">If an algorithm is not specified in the configuration file, the default settings are used.</span></span> <span data-ttu-id="7dfc1-142">Para obtener más información acerca de la configuración criptográfica, consulte [configurar clases de criptografía](../../../docs/framework/configure-apps/configure-cryptography-classes.md).</span><span class="sxs-lookup"><span data-stu-id="7dfc1-142">For more information about cryptographic configuration, see [Configuring Cryptography Classes](../../../docs/framework/configure-apps/configure-cryptography-classes.md).</span></span>  
  
## <a name="choosing-an-algorithm"></a><span data-ttu-id="7dfc1-143">Elegir un algoritmo</span><span class="sxs-lookup"><span data-stu-id="7dfc1-143">Choosing an Algorithm</span></span>  
 <span data-ttu-id="7dfc1-144">Puede seleccionar un algoritmo por diferentes motivos: por ejemplo, para proteger la integridad de los datos, para proteger la privacidad de los datos o para generar una clave.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-144">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="7dfc1-145">Los algoritmos simétricos y hash están diseñados para proteger los datos por motivos de integridad (impedir los cambios) o por motivos de privacidad (impedir la visualización).</span><span class="sxs-lookup"><span data-stu-id="7dfc1-145">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="7dfc1-146">Los algoritmos hash se usan principalmente para proteger la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="7dfc1-146">Hash algorithms are used primarily for data integrity.</span></span>  
  
 <span data-ttu-id="7dfc1-147">Esta es una lista de los algoritmos recomendados en función de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-147">Here is a list of recommended algorithms by application:</span></span>  
  
-   <span data-ttu-id="7dfc1-148">Privacidad de los datos:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-148">Data privacy:</span></span>  
  
    -   <xref:System.Security.Cryptography.Aes>  
  
-   <span data-ttu-id="7dfc1-149">Integridad de los datos:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-149">Data integrity:</span></span>  
  
    -   <xref:System.Security.Cryptography.HMACSHA256>  
  
    -   <xref:System.Security.Cryptography.HMACSHA512>  
  
-   <span data-ttu-id="7dfc1-150">Firma digital:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-150">Digital signature:</span></span>  
  
    -   <xref:System.Security.Cryptography.ECDsa>  
  
    -   <xref:System.Security.Cryptography.RSA>  
  
-   <span data-ttu-id="7dfc1-151">Intercambio de claves:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-151">Key exchange:</span></span>  
  
    -   <xref:System.Security.Cryptography.ECDiffieHellman>  
  
    -   <xref:System.Security.Cryptography.RSA>  
  
-   <span data-ttu-id="7dfc1-152">Generación de números aleatorios:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-152">Random number generation:</span></span>  
  
    -   <xref:System.Security.Cryptography.RNGCryptoServiceProvider>  
  
-   <span data-ttu-id="7dfc1-153">Generar una clave a partir de una contraseña:</span><span class="sxs-lookup"><span data-stu-id="7dfc1-153">Generating a key from a password:</span></span>  
  
    -   <xref:System.Security.Cryptography.Rfc2898DeriveBytes>  
  
## <a name="see-also"></a><span data-ttu-id="7dfc1-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dfc1-154">See also</span></span>

- [<span data-ttu-id="7dfc1-155">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7dfc1-155">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
