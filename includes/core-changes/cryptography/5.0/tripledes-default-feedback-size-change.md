---
ms.openlocfilehash: 2599e1f65720c25695f1fb5cfa39cabb842efc1d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888621"
---
### <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a>Cambio del valor FeedbackSize predeterminado para las instancias creadas por TripleDES.Create

El valor predeterminado de la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> en la instancia de <xref:System.Security.Cryptography.TripleDES> devuelta desde <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> ha cambiado de 64 a 8 para facilitar la migración de .NET Framework. Esta propiedad, a menos que se use directamente en el código del autor de la llamada, solo se utiliza cuando la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> es <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.

La compatibilidad con el modo <xref:System.Security.Cryptography.CipherMode.CFB> se agregó por primera vez a .NET para la versión 5.0 RC1, por lo que solo las aplicaciones de .NET 5.0 RC1 y .NET 5.0 RC2 se verán afectadas por este cambio.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core y versiones preliminares anteriores de .NET 5.0, `TripleDES.Create().FeedbackSize` tiene un valor predeterminado de 64. A partir de la versión RTM de .NET 5.0, `TripleDES.Create().FeedbackSize` tiene un valor predeterminado de 8.

#### <a name="reason-for-change"></a>Motivo del cambio

En .NET Framework, la clase base <xref:System.Security.Cryptography.TripleDES> establece de forma predeterminada el valor de <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> en 64, pero la clase <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> lo sobrescribe en 8. Cuando la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> se agregó a .NET Core en la versión 2.0, se conservó este mismo comportamiento. Pero en .NET Framework, <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> devuelve una instancia de <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>, por lo que el valor predeterminado del generador de algoritmos es 8. En .NET Core, y .NET 5 y versiones posteriores, el generador de algoritmos devuelve una implementación no pública que, hasta ahora, ha tenido un valor predeterminado de 64.

Al cambiar el valor <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> de la clase de implementación <xref:System.Security.Cryptography.TripleDES> a 8, las aplicaciones escritas para .NET Framework en las que se ha especificado el modo de cifrado como <xref:System.Security.Cryptography.CipherMode.CFB>, pero en las que no se ha asignado explícitamente la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>, pueden seguir funcionando en .NET 5.

#### <a name="version-introduced"></a>Versión introducida

5.0 RTM

#### <a name="recommended-action"></a>Acción recomendada

Las aplicaciones que cifran o descifran datos en las versiones RC1 o RC2 de .NET 5.0 lo hacen con CFB64, cuando se cumplen las condiciones siguientes:

- Con una instancia de <xref:System.Security.Cryptography.TripleDES> a partir de <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>.
- Con el valor predeterminado para <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.
- Con la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> establecida en <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.

Para mantener este comportamiento, asigne la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> a `64`.

No todas las implementaciones de `TripleDES` usan el mismo valor predeterminado para <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>. Se recomienda que, si usa el modo de cifrado <xref:System.Security.Cryptography.CipherMode.CFB> en las instancias de <xref:System.Security.Cryptography.TripleDES>, siempre asigne de forma explícita el valor de la propiedad <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

#### <a name="category"></a>Categoría

- Criptografía

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

-->
