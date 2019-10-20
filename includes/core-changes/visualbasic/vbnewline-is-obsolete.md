---
ms.openlocfilehash: 86cdb845c436f424bbcc70e0736568031143b204
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522699"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="cc2b4-101">Microsoft.VisualBasic.Constants.vbNewLine está obsoleto</span><span class="sxs-lookup"><span data-stu-id="cc2b4-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="cc2b4-102">La constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> está marcada con el atributo [Obsolete](xref:System.ObsoleteAttribute) a partir de .NET Core 3.0 (versión preliminar 8).</span><span class="sxs-lookup"><span data-stu-id="cc2b4-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cc2b4-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="cc2b4-103">Version introduced</span></span>

<span data-ttu-id="cc2b4-104">3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="cc2b4-104">3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="cc2b4-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="cc2b4-105">Change description</span></span>

<span data-ttu-id="cc2b4-106">A partir de .NET Core 3.0 (versión preliminar 8), se ha aplicado el atributo [Obsolete](xref:System.ObsoleteAttribute) a la constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="cc2b4-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="cc2b4-107">El uso de la constante genera una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="cc2b4-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="cc2b4-108">En versiones anteriores de .NET Core y .NET Framework, no estaba marcada como “Obsolete”.</span><span class="sxs-lookup"><span data-stu-id="cc2b4-108">In previous releases of both .NET Core and .NET Framework, it was not marked as obsolete.</span></span>

<span data-ttu-id="cc2b4-109">Este cambio se realizó para admitir Visual Basic como lenguaje para el desarrollo multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="cc2b4-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="cc2b4-110">La constante `vbNewLine` equivale a `\r\n`, la secuencia de caracteres de nueva línea en Windows.</span><span class="sxs-lookup"><span data-stu-id="cc2b4-110">The `vbNewLine` constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="cc2b4-111">En los sistemas basados en Unix, el carácter de nueva línea es `\n`.</span><span class="sxs-lookup"><span data-stu-id="cc2b4-111">On Unix-based systems, the newline character is `\n`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cc2b4-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="cc2b4-112">Recommended action</span></span>

<span data-ttu-id="cc2b4-113">El mensaje del atributo [Obsolete](xref:System.ObsoleteAttribute) para `vbNewLine` incluye la siguiente recomendación:</span><span class="sxs-lookup"><span data-stu-id="cc2b4-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="cc2b4-114">Para un retorno de carro y un avance de línea, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span><span class="sxs-lookup"><span data-stu-id="cc2b4-114">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="cc2b4-115">Para la nueva línea de la plataforma actual, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cc2b4-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="cc2b4-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="cc2b4-116">Category</span></span>

<span data-ttu-id="cc2b4-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc2b4-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cc2b4-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cc2b4-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
