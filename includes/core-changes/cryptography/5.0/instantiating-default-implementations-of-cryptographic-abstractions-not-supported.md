---
ms.openlocfilehash: 8198eca5b9c63d9717260b71ac6687dbf7245f35
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159564"
---
### <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a><span data-ttu-id="73af1-101">No se admite la creación de instancias de implementaciones predeterminadas de las abstracciones criptográficas</span><span class="sxs-lookup"><span data-stu-id="73af1-101">Instantiating default implementations of cryptographic abstractions is not supported</span></span>

<span data-ttu-id="73af1-102">Las sobrecargas de `Create()` sin parámetros en las abstracciones criptográficas están obsoletas como advertencia en .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="73af1-102">The parameterless `Create()` overloads on cryptographic abstractions are obsolete as warning as of .NET 5.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="73af1-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="73af1-103">Change description</span></span>

<span data-ttu-id="73af1-104">En .NET Framework 2.0-4.8, se pueden configurar generadores primitivos de cifrado abstractos como <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> para que devuelvan otros algoritmos.</span><span class="sxs-lookup"><span data-stu-id="73af1-104">In .NET Framework 2.0 - 4.8, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> can be configured to return different algorithms.</span></span> <span data-ttu-id="73af1-105">Por ejemplo, en una instalación predeterminada de .NET Framework 4.8, el método estático sin parámetros <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> devuelve una instancia del algoritmo SHA1, como se muestra en el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="73af1-105">For example, on a default install of .NET Framework 4.8, the parameterless, static method <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> returns an instance of the SHA1 algorithm, as shown in the following snippet.</span></span>

<span data-ttu-id="73af1-106">**Solo para .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="73af1-106">**.NET Framework only**</span></span>

```csharp
// Return an instance of the default hash algorithm (SHA1).
HashAlgorithm alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA1CryptoServiceProvider'.
Console.WriteLine(alg.GetType());

// Change the default algorithm to be SHA256, not SHA1.
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), typeof(HashAlgorithm).FullName);
alg = HashAlgorithm.Create();
// Prints 'System.Security.Cryptography.SHA256CryptoServiceProvider'.
Console.WriteLine(alg.GetType());
```

<span data-ttu-id="73af1-107">También puede usar una [configuración en todo el equipo](../../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) para cambiar el algoritmo predeterminado sin necesidad de llamar a `CryptoConfig` mediante programación.</span><span class="sxs-lookup"><span data-stu-id="73af1-107">You can also use [machine-wide configuration](../../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) to change the default algorithm without needing to call into `CryptoConfig` programmatically.</span></span>

<span data-ttu-id="73af1-108">En .NET Core 2.0-3.1, los generadores primitivos de cifrado abstractos como <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> siempre inician una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="73af1-108">In .NET Core 2.0 - 3.1, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> always throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="73af1-109">En .NET 5.0 y versiones posteriores, los generadores primitivos de cifrado abstractos como <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> se marcan como obsoletos y generan una advertencia en tiempo de compilación con el identificador `SYSLIB0007`.</span><span class="sxs-lookup"><span data-stu-id="73af1-109">In .NET 5.0 and later versions, abstract cryptographic primitive factories such as <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> are marked obsolete and produce a compile-time warning with ID `SYSLIB0007`.</span></span> <span data-ttu-id="73af1-110">En tiempo de ejecución, estos métodos siguen iniciando una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="73af1-110">At run time, these methods continue to throw a <xref:System.PlatformNotSupportedException>.</span></span>

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

<span data-ttu-id="73af1-111">Se trata de un cambio solo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="73af1-111">This is a compile-time only change.</span></span> <span data-ttu-id="73af1-112">No hay ningún cambio en tiempo de ejecución con respecto a versiones anteriores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="73af1-112">There is no run-time change from previous versions of .NET Core.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="73af1-113">Solo las sobrecargas sin parámetros de los métodos `Create()` están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="73af1-113">Only the parameterless overloads of the `Create()` methods are obsolete.</span></span> <span data-ttu-id="73af1-114">Las sobrecargas con parámetros no están obsoletas y siguen funcionando de la manera esperada.</span><span class="sxs-lookup"><span data-stu-id="73af1-114">Parameterized overloads are not obsolete and still function as expected.</span></span>
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - <span data-ttu-id="73af1-115">Las sobrecargas sin parámetros de familias de algoritmos *concretos* (no abstracciones) no están obsoletas y seguirán funcionando según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="73af1-115">Parameterless overloads of *specific* algorithm families (not abstractions) are not obsolete, and will continue to function as expected.</span></span>
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

#### <a name="reason-for-change"></a><span data-ttu-id="73af1-116">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="73af1-116">Reason for change</span></span>

<span data-ttu-id="73af1-117">El sistema de configuración de cifrado de .NET Framework ya no está presente en .NET Core y .NET 5.0+, ya que el sistema heredado no permite la agilidad criptográfica adecuada.</span><span class="sxs-lookup"><span data-stu-id="73af1-117">The cryptographic configuration system present in .NET Framework is no longer present in .NET Core and .NET 5.0+, since that legacy system doesn't allow for proper cryptographic agility.</span></span> <span data-ttu-id="73af1-118">Los requisitos de compatibilidad con versiones anteriores de .NET también impiden que el marco actualice determinadas API criptográficas para mantenerse al día de los avances en la criptografía.</span><span class="sxs-lookup"><span data-stu-id="73af1-118">.NET's backward-compatibility requirements also prohibit the framework from updating certain cryptographic APIs to keep up with advances in cryptography.</span></span> <span data-ttu-id="73af1-119">Por ejemplo, el método <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> se presentó en .NET Framework 1.0, cuando el algoritmo hash SHA-1 era lo más avanzado.</span><span class="sxs-lookup"><span data-stu-id="73af1-119">For example, the <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> method was introduced in .NET Framework 1.0, when the SHA-1 hash algorithm was state-of-the-art.</span></span> <span data-ttu-id="73af1-120">Han pasado 20 años y ahora SHA-1 se considera interrumpido, pero no se puede cambiar <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> para que devuelva otro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="73af1-120">Twenty years have passed, and now SHA-1 is considered broken, but we cannot change <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> to return a different algorithm.</span></span> <span data-ttu-id="73af1-121">Si se hiciera, se produciría un cambio importante inaceptable en las aplicaciones que lo usan.</span><span class="sxs-lookup"><span data-stu-id="73af1-121">Doing so would introduce an unacceptable breaking change in consuming applications.</span></span>

<span data-ttu-id="73af1-122">El procedimiento recomendado determina que las bibliotecas que consumen primitivas criptográficas (como AES, SHA-\* y RSA) deben tener control total sobre cómo consumen estas primitivas.</span><span class="sxs-lookup"><span data-stu-id="73af1-122">Best practice dictates that libraries that consume cryptographic primitives (such as AES, SHA-\*, and RSA) should be in full control over how they consume these primitives.</span></span> <span data-ttu-id="73af1-123">Las aplicaciones que necesiten revisiones futuras deben usar bibliotecas de nivel superior que encapsulen estas primitivas y agreguen funciones de administración de claves y agilidad criptográfica.</span><span class="sxs-lookup"><span data-stu-id="73af1-123">Applications that require future-proofing should utilize higher-level libraries that wrap these primitives and add key management and cryptographic agility capabilities.</span></span> <span data-ttu-id="73af1-124">Normalmente, estas bibliotecas las proporciona el entorno de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="73af1-124">These libraries are often provided by the hosting environment.</span></span> <span data-ttu-id="73af1-125">Un ejemplo es [la biblioteca de protección de datos de ASP.NET](/aspnet/core/security/data-protection/), que controla estos aspectos en nombre de la aplicación que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="73af1-125">One example is [ASP.NET's Data Protection library](/aspnet/core/security/data-protection/), which handles these concerns on behalf of the calling application.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="73af1-126">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="73af1-126">Version introduced</span></span>

<span data-ttu-id="73af1-127">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="73af1-127">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="73af1-128">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="73af1-128">Recommended action</span></span>

- <span data-ttu-id="73af1-129">La acción recomendada consiste en reemplazar las llamadas a las API que ahora son obsoletas por llamadas a métodos de generador para algoritmos específicos, como por ejemplo <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="73af1-129">The recommended course of action is to replace calls to the now-obsolete APIs with calls to factory methods for specific algorithms, for example, <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>.</span></span> <span data-ttu-id="73af1-130">Esto le proporciona control total sobre los algoritmos de los que se crean instancias.</span><span class="sxs-lookup"><span data-stu-id="73af1-130">This gives you full control over which algorithms are instantiated.</span></span>

- <span data-ttu-id="73af1-131">Si tiene que mantener la compatibilidad con cargas existentes generadas por aplicaciones de .NET Framework en las que se usan las API obsoletas, use los reemplazos sugeridos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="73af1-131">If you need to maintain compatibility with existing payloads generated by .NET Framework apps that use the now-obsolete APIs, use the replacements suggested in the following table.</span></span> <span data-ttu-id="73af1-132">En la tabla se proporciona una asignación de los algoritmos predeterminados de .NET Framework a sus equivalentes de .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="73af1-132">The table provides a mapping from .NET Framework default algorithms to their .NET 5+ equivalents.</span></span>

  | <span data-ttu-id="73af1-133">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="73af1-133">.NET Framework</span></span> | <span data-ttu-id="73af1-134">Reemplazo compatible con .NET Core / .NET 5.0+</span><span class="sxs-lookup"><span data-stu-id="73af1-134">.NET Core / .NET 5.0+ compatible replacement</span></span> | <span data-ttu-id="73af1-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73af1-135">Remarks</span></span> |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | <span data-ttu-id="73af1-136">El algoritmo SHA-1 se considera interrumpido.</span><span class="sxs-lookup"><span data-stu-id="73af1-136">The SHA-1 algorithm is considered broken.</span></span> <span data-ttu-id="73af1-137">Considere la posibilidad de usar un algoritmo más seguro si es posible.</span><span class="sxs-lookup"><span data-stu-id="73af1-137">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="73af1-138">Consulte con el asesor de seguridad para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73af1-138">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="73af1-139">El algoritmo HMACSHA1 no se recomienda para la mayoría de las aplicaciones modernas.</span><span class="sxs-lookup"><span data-stu-id="73af1-139">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="73af1-140">Considere la posibilidad de usar un algoritmo más seguro si es posible.</span><span class="sxs-lookup"><span data-stu-id="73af1-140">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="73af1-141">Consulte con el asesor de seguridad para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73af1-141">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | <span data-ttu-id="73af1-142">El algoritmo HMACSHA1 no se recomienda para la mayoría de las aplicaciones modernas.</span><span class="sxs-lookup"><span data-stu-id="73af1-142">The HMACSHA1 algorithm is discouraged for most modern applications.</span></span> <span data-ttu-id="73af1-143">Considere la posibilidad de usar un algoritmo más seguro si es posible.</span><span class="sxs-lookup"><span data-stu-id="73af1-143">Consider using a stronger algorithm if possible.</span></span> <span data-ttu-id="73af1-144">Consulte con el asesor de seguridad para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73af1-144">Consult your security advisor for further guidance.</span></span> |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- <span data-ttu-id="73af1-145">Si todavía tiene que llamar a las sobrecargas de `Create()` sin parámetros obsoletas, puede suprimir la advertencia `SYSLIB0007` en el código.</span><span class="sxs-lookup"><span data-stu-id="73af1-145">If you must continue to call the obsolete parameterless `Create()` overloads, you can suppress the `SYSLIB0007` warning in code.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  <span data-ttu-id="73af1-146">También puede suprimir la advertencia en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="73af1-146">You can also suppress the warning in your project file.</span></span> <span data-ttu-id="73af1-147">Al hacerlo, se deshabilita la advertencia para todos los archivos de código fuente del proyecto.</span><span class="sxs-lookup"><span data-stu-id="73af1-147">Doing so disables the warning for all source files within the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0007 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0007</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="73af1-148">La supresión de `SYSLIB0007` solo deshabilita las advertencias de API de criptografía obsoletas que se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="73af1-148">Suppressing `SYSLIB0007` disables only the obsoletion warnings for the cryptography APIs listed here.</span></span> <span data-ttu-id="73af1-149">No se deshabilita ninguna otra advertencia.</span><span class="sxs-lookup"><span data-stu-id="73af1-149">It does not disable any other warnings.</span></span> <span data-ttu-id="73af1-150">Además, aunque se suprima la advertencia, en estas API obsoletas se seguirá iniciando una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="73af1-150">Additionally, even if you suppress the warning, these obsoleted APIs will still throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

#### <a name="category"></a><span data-ttu-id="73af1-151">Categoría</span><span class="sxs-lookup"><span data-stu-id="73af1-151">Category</span></span>

- <span data-ttu-id="73af1-152">Criptografía</span><span class="sxs-lookup"><span data-stu-id="73af1-152">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="73af1-153">API afectadas</span><span class="sxs-lookup"><span data-stu-id="73af1-153">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

-->
