---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568073"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a><span data-ttu-id="d9c09-101">.NET Core 3.0 sigue los procedimientos recomendados de Unicode al reemplazar secuencias de bytes UTF-8 con formato incorrecto</span><span class="sxs-lookup"><span data-stu-id="d9c09-101">.NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>

<span data-ttu-id="d9c09-102">Cuando la clase <xref:System.Text.UTF8Encoding> encuentra una secuencia de bytes UTF-8 con formato incorrecto durante una operación de transcodificación de byte a carácter, reemplazará esa secuencia por un carácter "�" (CARÁCTER DE REEMPLAZO DE U+FFFD) en la cadena de salida.</span><span class="sxs-lookup"><span data-stu-id="d9c09-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it will replace that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="d9c09-103">.NET Core 3.0 se diferencia de las versiones anteriores de .NET Core y de .NET Framework en que sigue los procedimientos recomendados de Unicode para realizar este reemplazo durante la operación de transcodificación.</span><span class="sxs-lookup"><span data-stu-id="d9c09-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="d9c09-104">Esto forma parte de un trabajo mayor para mejorar el control de UTF-8 en .NET, que los nuevos tipos <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> y <xref:System.Text.Rune?displayProperty=nameWithType> incluyen.</span><span class="sxs-lookup"><span data-stu-id="d9c09-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="d9c09-105">Se asignó una mecánica de control de errores mejorada al tipo <xref:System.Text.UTF8Encoding> para que genere una salida coherente con los tipos recién incorporados.</span><span class="sxs-lookup"><span data-stu-id="d9c09-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d9c09-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d9c09-106">Change description</span></span>

<span data-ttu-id="d9c09-107">A partir de .NET Core 3.0, al transcodificar bytes en caracteres, la clase <xref:System.Text.UTF8Encoding> realiza la sustitución de caracteres en función de los procedimientos recomendados de Unicode.</span><span class="sxs-lookup"><span data-stu-id="d9c09-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="d9c09-108">El mecanismo de sustitución que se usa se describe en [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) en el apartado titulado _U+FFFD Substitution of Maximal Subparts_.</span><span class="sxs-lookup"><span data-stu-id="d9c09-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="d9c09-109">Este comportamiento _solo_ se aplica cuando la secuencia de bytes de entrada contiene datos UTF-8 con formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="d9c09-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="d9c09-110">Además, si la instancia de <xref:System.Text.UTF8Encoding> se ha construido con `throwOnInvalidBytes: true` (consulte la [documentación del constructor de UTF8Encoding]) <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, la instancia de `UTF8Encoding`continuará produciéndose en una entrada no válida en lugar de realizar el reemplazo de U+FFFD.</span><span class="sxs-lookup"><span data-stu-id="d9c09-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true` (see the [UTF8Encoding constructor documentation](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span>

<span data-ttu-id="d9c09-111">A continuación se muestra el impacto de este cambio con una entrada de 3 bytes no válida:</span><span class="sxs-lookup"><span data-stu-id="d9c09-111">The following illustrates the impact of this change with an invalid 3-byte input:</span></span>

|<span data-ttu-id="d9c09-112">Entrada de 3 bytes con formato incorrecto</span><span class="sxs-lookup"><span data-stu-id="d9c09-112">Ill-formed 3-byte input</span></span>|<span data-ttu-id="d9c09-113">Salida antes de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d9c09-113">Output before .NET Core 3.0</span></span>|<span data-ttu-id="d9c09-114">Salida a partir de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d9c09-114">Output starting with .NET Core 3.0</span></span>|
|---|---|---|
| `[ ED A0 90 ]` | <span data-ttu-id="d9c09-115">`[ FFFD FFFD ]` (salida de 2 caracteres)</span><span class="sxs-lookup"><span data-stu-id="d9c09-115">`[ FFFD FFFD ]` (2-character output)</span></span>| <span data-ttu-id="d9c09-116">`[ FFFD FFFD FFFD ]` (salida de 3 caracteres)</span><span class="sxs-lookup"><span data-stu-id="d9c09-116">`[ FFFD FFFD FFFD ]` (3-character output)</span></span>|

<span data-ttu-id="d9c09-117">Esta salida de 3 caracteres es la salida preferida, según la _tabla 3-9_ del PDF del estándar Unicode vinculado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d9c09-117">This 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9c09-118">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d9c09-118">Version introduced</span></span>

<span data-ttu-id="d9c09-119">3.0</span><span class="sxs-lookup"><span data-stu-id="d9c09-119">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9c09-120">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d9c09-120">Recommended action</span></span>

<span data-ttu-id="d9c09-121">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="d9c09-121">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="d9c09-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="d9c09-122">Category</span></span>

<span data-ttu-id="d9c09-123">CoreFX</span><span class="sxs-lookup"><span data-stu-id="d9c09-123">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9c09-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d9c09-124">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
