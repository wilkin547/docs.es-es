---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065113"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a><span data-ttu-id="7af48-101">Transformación del bloque final solo durante el proceso de escritura mediante CryptoStream.Dispose</span><span class="sxs-lookup"><span data-stu-id="7af48-101">CryptoStream.Dispose transforms final block only when writing</span></span>

<span data-ttu-id="7af48-102">El método <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>, que se usa para finalizar operaciones `CryptoStream`, ya no intenta transformar el bloque final durante la lectura.</span><span class="sxs-lookup"><span data-stu-id="7af48-102">The <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> method, which is used to finish `CryptoStream` operations, no longer attempts to transform the final block when reading.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7af48-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7af48-103">Change description</span></span>

<span data-ttu-id="7af48-104">En versiones anteriores de .NET, si un usuario realizaba una lectura incompleta al usar <xref:System.Security.Cryptography.CryptoStream> en el modo <xref:System.Security.Cryptography.CryptoStreamMode.Read>, el método <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> podía producir una excepción (por ejemplo, al usar AES con espaciado interno).</span><span class="sxs-lookup"><span data-stu-id="7af48-104">In previous .NET versions, if a user performed an incomplete read when using <xref:System.Security.Cryptography.CryptoStream> in <xref:System.Security.Cryptography.CryptoStreamMode.Read> mode, the <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> method could throw an exception (for example, when using AES with padding).</span></span> <span data-ttu-id="7af48-105">Se producía la excepción porque se intentaba transformar el bloque final, pero los datos estaban incompletos.</span><span class="sxs-lookup"><span data-stu-id="7af48-105">The exception was thrown because the final block was attempted to be transformed but the data was incomplete.</span></span>

<span data-ttu-id="7af48-106">En .NET Core 3.0 y versiones posteriores, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> ya no intenta transformar el bloque final durante la lectura, lo que permite hacer lecturas incompletas.</span><span class="sxs-lookup"><span data-stu-id="7af48-106">In .NET Core 3.0 and later versions, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> no longer tries to transform the final block when reading, which allows for incomplete reads.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7af48-107">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7af48-107">Reason for change</span></span>

<span data-ttu-id="7af48-108">Este cambio permite las lecturas incompletas de la secuencia de cifrado cuando se cancela una operación de red sin necesidad de detectar una excepción.</span><span class="sxs-lookup"><span data-stu-id="7af48-108">This change enables incomplete reads from the crypto stream when a network operation is cancelled, without the need to catch an exception.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7af48-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7af48-109">Version introduced</span></span>

<span data-ttu-id="7af48-110">3.0</span><span class="sxs-lookup"><span data-stu-id="7af48-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7af48-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7af48-111">Recommended action</span></span>

<span data-ttu-id="7af48-112">La mayoría de las aplicaciones no se verán afectadas por este cambio.</span><span class="sxs-lookup"><span data-stu-id="7af48-112">Most apps should not be affected by this change.</span></span>

<span data-ttu-id="7af48-113">Si su aplicación detectaba anteriormente una excepción en caso de una lectura incompleta, puede eliminar ese bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="7af48-113">If your application previously caught an exception in case of an incomplete read, you can delete that `catch` block.</span></span>
<span data-ttu-id="7af48-114">Si su aplicación usaba la transformación del bloque final en operaciones hash, puede que tenga que asegurarse de que se lee toda la secuencia antes de eliminar el bloque.</span><span class="sxs-lookup"><span data-stu-id="7af48-114">If your app used transforming of the final block in hashing scenarios, you might need to ensure that the entire stream is read before it's disposed.</span></span>

#### <a name="category"></a><span data-ttu-id="7af48-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="7af48-115">Category</span></span>

<span data-ttu-id="7af48-116">Criptografía</span><span class="sxs-lookup"><span data-stu-id="7af48-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7af48-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7af48-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
