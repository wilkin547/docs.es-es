---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117109"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="ac0ab-101">Microsoft.VisualBasic.Constants.vbNewLine está obsoleto</span><span class="sxs-lookup"><span data-stu-id="ac0ab-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="ac0ab-102">La constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> está marcada con el atributo [Obsolete](xref:System.ObsoleteAttribute) en .NET Framework, pero faltaba el atributo en la biblioteca de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="ac0ab-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ac0ab-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ac0ab-103">Version introduced</span></span>

<span data-ttu-id="ac0ab-104">.NET Core 3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="ac0ab-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="ac0ab-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="ac0ab-105">Details</span></span>

<span data-ttu-id="ac0ab-106">A partir de .NET Core 3.0 (versión preliminar 8), se ha aplicado el atributo [Obsolete](xref:System.ObsoleteAttribute) a la constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> para ajustarse a la constante `vbNewLine` en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac0ab-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="ac0ab-107">El uso de la constante `vbNewLine` genera una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="ac0ab-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="ac0ab-108">En versiones anteriores de .NET Core, `vbNewLine` no producía una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="ac0ab-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ac0ab-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ac0ab-109">Recommended action</span></span>

<span data-ttu-id="ac0ab-110">El mensaje del atributo [Obsolete](xref:System.ObsoleteAttribute) para `vbNewLine` incluye la siguiente recomendación:</span><span class="sxs-lookup"><span data-stu-id="ac0ab-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="ac0ab-111">Para un retorno de carro y un avance de línea, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span><span class="sxs-lookup"><span data-stu-id="ac0ab-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="ac0ab-112">Para la nueva línea de la plataforma actual, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac0ab-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="ac0ab-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="ac0ab-113">Category</span></span>

<span data-ttu-id="ac0ab-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac0ab-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ac0ab-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ac0ab-115">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

