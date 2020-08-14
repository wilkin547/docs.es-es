---
ms.openlocfilehash: 54ef49755dc0b9d1b821ae7999ab218626d455e1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556347"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a><span data-ttu-id="19cd7-101">No se puede recurrir de formar recursiva a las instancias personalizadas de EncoderFallbackBuffer</span><span class="sxs-lookup"><span data-stu-id="19cd7-101">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>

<span data-ttu-id="19cd7-102">No se puede recurrir de formar recursiva a las instancias personalizadas de <xref:System.Text.EncoderFallbackBuffer>.</span><span class="sxs-lookup"><span data-stu-id="19cd7-102">Custom <xref:System.Text.EncoderFallbackBuffer> instances cannot fall back recursively.</span></span> <span data-ttu-id="19cd7-103">La implementación de <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> debe traducirse en una secuencia de caracteres que se pueda convertir a la codificación de destino.</span><span class="sxs-lookup"><span data-stu-id="19cd7-103">The implementation of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must result in a character sequence that is convertible to the destination encoding.</span></span> <span data-ttu-id="19cd7-104">De lo contrario, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="19cd7-104">Otherwise, an exception occurs.</span></span>

#### <a name="change-description"></a><span data-ttu-id="19cd7-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="19cd7-105">Change description</span></span>

<span data-ttu-id="19cd7-106">Durante una operación de transcodificación de caracteres a bytes, el runtime detecta secuencias UTF-16 de formato incorrecto o no convertibles y proporciona esos caracteres al método <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="19cd7-106">During a character-to-byte transcoding operation, the runtime detects ill-formed or nonconvertible UTF-16 sequences and provides those characters to the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="19cd7-107">El método `Fallback` determina los caracteres que han de sustituirse por los datos originales no convertibles y estos caracteres se drenan llamando a <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> en un bucle.</span><span class="sxs-lookup"><span data-stu-id="19cd7-107">The `Fallback` method determines which characters should be substituted for the original nonconvertible data, and these characters are drained by calling <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in a loop.</span></span>

<span data-ttu-id="19cd7-108">El runtime intenta luego transcodificar estos caracteres de sustitución en la codificación de destino.</span><span class="sxs-lookup"><span data-stu-id="19cd7-108">The runtime then attempts to transcode these substitution characters to the target encoding.</span></span> <span data-ttu-id="19cd7-109">Si esta operación se realiza correctamente, el runtime continúa con la transcodificación desde donde se quedó en la cadena de entrada original.</span><span class="sxs-lookup"><span data-stu-id="19cd7-109">If this operation succeeds, the runtime continues transcoding from where it left off in the original input string.</span></span>

<span data-ttu-id="19cd7-110">Antes, las implementaciones personalizadas de <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> pueden devolver secuencias de caracteres que no se pueden convertir en la codificación de destino.</span><span class="sxs-lookup"><span data-stu-id="19cd7-110">Previously, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> can return character sequences that are not convertible to the destination encoding.</span></span> <span data-ttu-id="19cd7-111">Si los caracteres sustituidos no se pueden transcodificar en la codificación de destino, el runtime vuelve a invocar el método <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> con los caracteres de sustitución, esperando que el método <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> devuelva una nueva secuencia de sustitución.</span><span class="sxs-lookup"><span data-stu-id="19cd7-111">If the substituted characters cannot be transcoded to the target encoding, the runtime invokes the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method once again with the substitution characters, expecting the <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> method to return a new substitution sequence.</span></span> <span data-ttu-id="19cd7-112">Este proceso continúa hasta que el runtime ve finalmente una sustitución convertible de formato correcto o hasta que se alcanza un número máximo de repeticiones.</span><span class="sxs-lookup"><span data-stu-id="19cd7-112">This process continues until the runtime eventually sees a well-formed, convertible substitution, or until a maximum recursion count is reached.</span></span>

<span data-ttu-id="19cd7-113">A partir de .NET Core 3.0, las implementaciones personalizadas de <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> deben devolver secuencias de caracteres que se pueden convertir en la codificación de destino.</span><span class="sxs-lookup"><span data-stu-id="19cd7-113">Starting with .NET Core 3.0, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must return character sequences that are convertible to the destination encoding.</span></span> <span data-ttu-id="19cd7-114">Si los caracteres sustituidos no se pueden transcodificar en la codificación de destino, se produce una <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="19cd7-114">If the substituted characters cannot be transcoded to the target encoding, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="19cd7-115">El runtime ya no realizará llamadas recursivas a la instancia de <xref:System.Text.EncoderFallbackBuffer>.</span><span class="sxs-lookup"><span data-stu-id="19cd7-115">The runtime will no longer make recursive calls into the <xref:System.Text.EncoderFallbackBuffer> instance.</span></span>

<span data-ttu-id="19cd7-116">Este comportamiento solo se aplica cuando se cumplen las tres condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="19cd7-116">This behavior only applies when all three of the following conditions are met:</span></span>

- <span data-ttu-id="19cd7-117">El runtime detecta una secuencia UTF-16 de formato incorrecto o una secuencia UTF-16 que no se puede convertir en la codificación de destino.</span><span class="sxs-lookup"><span data-stu-id="19cd7-117">The runtime detects an ill-formed UTF-16 sequence or a UTF-16 sequence that cannot be converted to the target encoding.</span></span>
- <span data-ttu-id="19cd7-118">Se ha especificado un <xref:System.Text.EncoderFallback> personalizado.</span><span class="sxs-lookup"><span data-stu-id="19cd7-118">A custom <xref:System.Text.EncoderFallback> has been specified.</span></span>
- <span data-ttu-id="19cd7-119">El <xref:System.Text.EncoderFallback> personalizado intenta sustituir una nueva secuencia UTF-16 con formato incorrecto o no convertible.</span><span class="sxs-lookup"><span data-stu-id="19cd7-119">The custom <xref:System.Text.EncoderFallback> attempts to substitute a new ill-formed or nonconvertible UTF-16 sequence.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="19cd7-120">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="19cd7-120">Version introduced</span></span>

<span data-ttu-id="19cd7-121">3.0</span><span class="sxs-lookup"><span data-stu-id="19cd7-121">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="19cd7-122">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="19cd7-122">Recommended action</span></span>

<span data-ttu-id="19cd7-123">La mayoría de los desarrolladores no tienen que realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="19cd7-123">Most developers needn't take any action.</span></span>

<span data-ttu-id="19cd7-124">Si una aplicación usa un objeto <xref:System.Text.EncoderFallback> personalizado con una clase <xref:System.Text.EncoderFallbackBuffer>, asegúrese de que la implementación de <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> rellena el búfer de reserva con datos UTF-16 de formato correcto que se puedan convertir directamente en la codificación de destino cuando el runtime invoque por primera vez el método <xref:System.Text.EncoderFallbackBuffer.Fallback%2A>.</span><span class="sxs-lookup"><span data-stu-id="19cd7-124">If an application uses a custom <xref:System.Text.EncoderFallback> and <xref:System.Text.EncoderFallbackBuffer> class, ensure the implementation of <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> populates the fallback buffer with well-formed UTF-16 data that is directly convertible to the target encoding when the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> method is first invoked by the runtime.</span></span>

#### <a name="category"></a><span data-ttu-id="19cd7-125">Categoría</span><span class="sxs-lookup"><span data-stu-id="19cd7-125">Category</span></span>

<span data-ttu-id="19cd7-126">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="19cd7-126">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="19cd7-127">API afectadas</span><span class="sxs-lookup"><span data-stu-id="19cd7-127">Affected APIs</span></span>

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
