---
ms.openlocfilehash: 7682eae5a28d4ef87d6622b775e0f2f9408bcbae
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117119"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a><span data-ttu-id="fa1c6-101">EnvelopedCms utiliza de forma predeterminada el cifrado AES-256</span><span class="sxs-lookup"><span data-stu-id="fa1c6-101">EnvelopedCms defaults to AES-256 encryption</span></span>

<span data-ttu-id="fa1c6-102">El algoritmo de cifrado simétrico predeterminado que utiliza `EnvelopedCms` ha cambiado de TripleDES a AES-256</span><span class="sxs-lookup"><span data-stu-id="fa1c6-102">The default symmetric encryption algorithm used by `EnvelopedCms` has changed from TripleDES to AES-256</span></span>

#### <a name="details"></a><span data-ttu-id="fa1c6-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa1c6-103">Details</span></span>

<span data-ttu-id="fa1c6-104">En la versión preliminar 7 de .NET Core y versiones anteriores, cuando se usa <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> para cifrar datos sin especificar un algoritmo de cifrado simétrico a través de una sobrecarga de constructor, los datos se cifran con el algoritmo TripleDES/3DES/3DEA/DES3-EDE.</span><span class="sxs-lookup"><span data-stu-id="fa1c6-104">In .NET Core Preview 7 and earlier versions, when <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> is used to encrypt data without specifying a symmetric encryption algorithm via a constructor overload, the data was encrypted with the TripleDES/3DES/3DEA/DES3-EDE algorithm.</span></span>

<span data-ttu-id="fa1c6-105">A partir de la versión preliminar 8 de .NET Core 3.0 (a través de la versión 4.6.0 del paquete NuGet [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/)), el algoritmo predeterminado se ha cambiado a AES-256 para la modernización de algoritmos y para mejorar la seguridad de opciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="fa1c6-105">Starting with .NET Core 3.0 Preview 8 (via version 4.6.0 of the [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet package), the default algorithm has been changed to AES-256 for algorithm modernization and to improve the security of default options.</span></span> <span data-ttu-id="fa1c6-106">Si el certificado del destinatario de un mensaje tiene una clave pública Diffie-Hellman (no de cliente de empresa), es posible que se produzca un error <xref:System.Security.Cryptography.CryptographicException> en la operación de cifrado debido a limitaciones de la plataforma subyacente.</span><span class="sxs-lookup"><span data-stu-id="fa1c6-106">If a message recipient certificate has a (non-EC) Diffie-Hellman public key, the encryption operation may fail with a <xref:System.Security.Cryptography.CryptographicException> due to limitations in the underlying platform.</span></span>

<span data-ttu-id="fa1c6-107">En el siguiente código de ejemplo, los datos se cifran con TripleDES si se ejecutan en la versión preliminar 7 de .NET Core 3.0 o en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="fa1c6-107">In the following sample code, the data is encrypted with TripleDES if running on .NET Core 3.0 Preview 7 or earlier.</span></span> <span data-ttu-id="fa1c6-108">Si se ejecuta en la versión preliminar 8 de .NET Core 3.0 o versiones posteriores, se cifra con AES-256.</span><span class="sxs-lookup"><span data-stu-id="fa1c6-108">If running on .NET Core 3.0 Preview 8 or later, it is encrypted with AES-256.</span></span>

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a><span data-ttu-id="fa1c6-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="fa1c6-109">Version introduced</span></span>

<span data-ttu-id="fa1c6-110">3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="fa1c6-110">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fa1c6-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="fa1c6-111">Recommended action</span></span>

<span data-ttu-id="fa1c6-112">Si el cambio le afecta negativamente, puede restaurar el cifrado TripleDES especificando explícitamente el identificador del algoritmo de cifrado en un constructor de <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> que incluya un parámetro del tipo <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fa1c6-112">If you are negatively impacted by the change, you can restore TripleDES encryption by explicitly specifying the encryption algorithm identifier in an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> constructor that includes a parameter of type <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, such as:</span></span>

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a><span data-ttu-id="fa1c6-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="fa1c6-113">Category</span></span>

<span data-ttu-id="fa1c6-114">Criptografía</span><span class="sxs-lookup"><span data-stu-id="fa1c6-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fa1c6-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fa1c6-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->