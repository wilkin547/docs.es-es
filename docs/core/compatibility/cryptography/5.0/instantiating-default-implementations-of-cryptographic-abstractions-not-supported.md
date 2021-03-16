---
title: 'Cambio importante: No se admite la creación de instancias de implementaciones predeterminadas de las abstracciones criptográficas'
description: Obtenga información sobre el cambio importante en .NET 5 donde las sobrecargas de Create() sin parámetros en las abstracciones criptográficas están obsoletas.
ms.date: 10/16/2020
ms.openlocfilehash: b75f3568317d1db8ae1bb629f760aaec7e69776a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256795"
---
# <a name="instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported"></a>No se admite la creación de instancias de implementaciones predeterminadas de las abstracciones criptográficas

Las sobrecargas de `Create()` sin parámetros en las abstracciones criptográficas están obsoletas como advertencia en .NET 5.0.

## <a name="change-description"></a>Descripción del cambio

En .NET Framework 2.0-4.8, se pueden configurar generadores primitivos de cifrado abstractos como <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> para que devuelvan otros algoritmos. Por ejemplo, en una instalación predeterminada de .NET Framework 4.8, el método estático sin parámetros <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> devuelve una instancia del algoritmo SHA1, como se muestra en el fragmento de código siguiente.

**Solo para .NET Framework**

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

También puede usar una [configuración en todo el equipo](../../../../framework/configure-apps/map-algorithm-names-to-cryptography-classes.md) para cambiar el algoritmo predeterminado sin necesidad de llamar a `CryptoConfig` mediante programación.

En .NET Core 2.0-3.1, los generadores primitivos de cifrado abstractos como <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> siempre inician una excepción <xref:System.PlatformNotSupportedException>.

```csharp
// Throws PlatformNotSupportedException on .NET Core.
HashAlgorithm alg = HashAlgorithm.Create();
```

En .NET 5 y versiones posteriores, los generadores primitivos de cifrado abstractos como <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> se marcan como obsoletos y generan una advertencia en tiempo de compilación con el identificador `SYSLIB0007`. En tiempo de ejecución, estos métodos siguen iniciando una excepción <xref:System.PlatformNotSupportedException>.

```csharp
// Throws PlatformNotSupportedException.
// Also produces compile-time warning SYSLIB0007 on .NET 5+.
HashAlgorithm alg = HashAlgorithm.Create();
```

Se trata de un cambio solo en tiempo de compilación. No hay ningún cambio en tiempo de ejecución con respecto a versiones anteriores de .NET Core.

> [!NOTE]
>
> - Solo las sobrecargas sin parámetros de los métodos `Create()` están obsoletas. Las sobrecargas con parámetros no están obsoletas y siguen funcionando de la manera esperada.
>
>   ```csharp
>   // Call Create(string), providing an explicit algorithm family name.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   HashAlgorithm hashAlg = HashAlgorithm.Create("SHA256");
>   ```
>
> - Las sobrecargas sin parámetros de familias de algoritmos *concretos* (no abstracciones) no están obsoletas y seguirán funcionando según lo previsto.
>
>   ```csharp
>   // Call a specific algorithm family's parameterless Create() ctor.
>   // Works in .NET Framework, .NET Core, and .NET 5.0+.
>   Aes aesAlg = Aes.Create();
>   ```

## <a name="reason-for-change"></a>Motivo del cambio

El sistema de configuración de cifrado de .NET Framework ya no está presente en .NET Core y .NET 5.0+, ya que el sistema heredado no permite la agilidad criptográfica adecuada. Los requisitos de compatibilidad con versiones anteriores de .NET también impiden que el marco actualice determinadas API criptográficas para mantenerse al día de los avances en la criptografía. Por ejemplo, el método <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> se presentó en .NET Framework 1.0, cuando el algoritmo hash SHA-1 era lo más avanzado. Han pasado 20 años y ahora SHA-1 se considera interrumpido, pero no se puede cambiar <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> para que devuelva otro algoritmo. Si se hiciera, se produciría un cambio importante inaceptable en las aplicaciones que lo usan.

El procedimiento recomendado determina que las bibliotecas que consumen primitivas criptográficas (como AES, SHA-* y RSA) deben tener control total sobre cómo consumen estas primitivas. Las aplicaciones que necesiten revisiones futuras deben usar bibliotecas de nivel superior que encapsulen estas primitivas y agreguen funciones de administración de claves y agilidad criptográfica. Normalmente, estas bibliotecas las proporciona el entorno de hospedaje. Un ejemplo es [la biblioteca de protección de datos de ASP.NET](/aspnet/core/security/data-protection/), que controla estos aspectos en nombre de la aplicación que realiza la llamada.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- La acción recomendada consiste en reemplazar las llamadas a las API que ahora son obsoletas por llamadas a métodos de generador para algoritmos específicos, como por ejemplo <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType>. Esto le proporciona control total sobre los algoritmos de los que se crean instancias.

- Si tiene que mantener la compatibilidad con cargas existentes generadas por aplicaciones de .NET Framework en las que se usan las API obsoletas, use los reemplazos sugeridos en la tabla siguiente. En la tabla se proporciona una asignación de los algoritmos predeterminados de .NET Framework a sus equivalentes de .NET 5+.

  | .NET Framework | Reemplazo compatible con .NET Core / .NET 5.0+ | Comentarios |
  | - | - | - |
  | <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.RSA.Create?displayProperty=nameWithType> | |
  | <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.SHA1.Create?displayProperty=nameWithType> | El algoritmo SHA-1 se considera interrumpido. Considere la posibilidad de usar un algoritmo más seguro si es posible. Consulte con el asesor de seguridad para obtener más información. |
  | <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | El algoritmo HMACSHA1 no se recomienda para la mayoría de las aplicaciones modernas. Considere la posibilidad de usar un algoritmo más seguro si es posible. Consulte con el asesor de seguridad para obtener más información. |
  | <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.HMACSHA1.%23ctor> | El algoritmo HMACSHA1 no se recomienda para la mayoría de las aplicaciones modernas. Considere la posibilidad de usar un algoritmo más seguro si es posible. Consulte con el asesor de seguridad para obtener más información. |
  | <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <xref:System.Security.Cryptography.Aes.Create?displayProperty=nameWithType> |

- Si todavía tiene que llamar a las sobrecargas de `Create()` sin parámetros obsoletas, puede suprimir la advertencia `SYSLIB0007` en el código.

  ```csharp
  #pragma warning disable SYSLIB0007 // Disable the warning.
  HashAlgorithm alg = HashAlgorithm.Create(); // Still throws PNSE.
  #pragma warning restore SYSLIB0007 // Re-enable the warning.
  ```

  También puede suprimir la advertencia en el archivo del proyecto. Al hacerlo, se deshabilita la advertencia para todos los archivos de código fuente del proyecto.

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
  > La supresión de `SYSLIB0007` solo deshabilita las advertencias de API de criptografía obsoletas que se muestran aquí. No se deshabilita ninguna otra advertencia. Además, aunque se suprima la advertencia, en estas API obsoletas se seguirá iniciando una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.HMAC.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.AsymmetricAlgorithm.Create`
- `M:System.Security.Cryptography.HashAlgorithm.Create`
- `M:System.Security.Cryptography.HMAC.Create`
- `M:System.Security.Cryptography.KeyedHashAlgorithm.Create`
- `M:System.Security.Cryptography.SymmetricAlgorithm.Create`

### Category

- Cryptography

-->
