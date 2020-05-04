---
ms.openlocfilehash: becae23cd810623bbb33c693b707c2d4735aeece
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158490"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a><span data-ttu-id="525ca-101">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="525ca-101">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>

<span data-ttu-id="525ca-102">Cuando la clase <xref:System.Text.UTF8Encoding> encuentra una secuencia de bytes UTF-8 con formato incorrecto durante una operación de transcodificación de byte a carácter, reemplaza esa secuencia por un carácter "�" (CARÁCTER DE REEMPLAZO DE U+FFFD) en la cadena de salida.</span><span class="sxs-lookup"><span data-stu-id="525ca-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it replaces that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="525ca-103">.NET Core 3.0 se diferencia de las versiones anteriores de .NET Core y de .NET Framework en que sigue los procedimientos recomendados de Unicode para realizar este reemplazo durante la operación de transcodificación.</span><span class="sxs-lookup"><span data-stu-id="525ca-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="525ca-104">Esto forma parte de un trabajo mayor para mejorar el control de UTF-8 en .NET, que los nuevos tipos <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> y <xref:System.Text.Rune?displayProperty=nameWithType> incluyen.</span><span class="sxs-lookup"><span data-stu-id="525ca-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="525ca-105">Se asignó una mecánica de control de errores mejorada al tipo <xref:System.Text.UTF8Encoding> para que genere una salida coherente con los tipos recién incorporados.</span><span class="sxs-lookup"><span data-stu-id="525ca-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="525ca-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="525ca-106">Change description</span></span>

<span data-ttu-id="525ca-107">A partir de .NET Core 3.0, al transcodificar bytes en caracteres, la clase <xref:System.Text.UTF8Encoding> realiza la sustitución de caracteres en función de los procedimientos recomendados de Unicode.</span><span class="sxs-lookup"><span data-stu-id="525ca-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="525ca-108">El mecanismo de sustitución que se usa se describe en [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) en el apartado titulado _U+FFFD Substitution of Maximal Subparts_.</span><span class="sxs-lookup"><span data-stu-id="525ca-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="525ca-109">Este comportamiento _solo_ se aplica cuando la secuencia de bytes de entrada contiene datos UTF-8 con formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="525ca-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="525ca-110">Además, si la instancia de <xref:System.Text.UTF8Encoding> se ha construido con `throwOnInvalidBytes: true`, la instancia de `UTF8Encoding`continuará produciéndose en una entrada no válida en lugar de realizar el reemplazo de U+FFFD.</span><span class="sxs-lookup"><span data-stu-id="525ca-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true`, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span> <span data-ttu-id="525ca-111">Para obtener más información sobre el constructor `UTF8Encoding`, vea <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.</span><span class="sxs-lookup"><span data-stu-id="525ca-111">For more information about the `UTF8Encoding` constructor, see <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.</span></span>

<span data-ttu-id="525ca-112">En la siguiente tabla se muestra el impacto de este cambio con una entrada de 3 bytes no válida:</span><span class="sxs-lookup"><span data-stu-id="525ca-112">The following table illustrates the impact of this change with an invalid 3-byte input:</span></span>

| <span data-ttu-id="525ca-113">Entrada de 3 bytes con formato incorrecto</span><span class="sxs-lookup"><span data-stu-id="525ca-113">Ill-formed 3-byte input</span></span> | <span data-ttu-id="525ca-114">Salida antes de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="525ca-114">Output before .NET Core 3.0</span></span>          | <span data-ttu-id="525ca-115">Salida a partir de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="525ca-115">Output starting with .NET Core 3.0</span></span>        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | <span data-ttu-id="525ca-116">`[ FFFD FFFD ]` (salida de 2 caracteres)</span><span class="sxs-lookup"><span data-stu-id="525ca-116">`[ FFFD FFFD ]` (2-character output)</span></span> | <span data-ttu-id="525ca-117">`[ FFFD FFFD FFFD ]` (salida de 3 caracteres)</span><span class="sxs-lookup"><span data-stu-id="525ca-117">`[ FFFD FFFD FFFD ]` (3-character output)</span></span> |

<span data-ttu-id="525ca-118">La salida de 3 caracteres es la preferida, según la _tabla 3-9_ del PDF del estándar Unicode vinculado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="525ca-118">The 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="525ca-119">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="525ca-119">Version introduced</span></span>

<span data-ttu-id="525ca-120">3.0</span><span class="sxs-lookup"><span data-stu-id="525ca-120">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="525ca-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="525ca-121">Recommended action</span></span>

<span data-ttu-id="525ca-122">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="525ca-122">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="525ca-123">Categoría</span><span class="sxs-lookup"><span data-stu-id="525ca-123">Category</span></span>

<span data-ttu-id="525ca-124">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="525ca-124">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="525ca-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="525ca-125">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
