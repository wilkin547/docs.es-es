---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614981"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a><span data-ttu-id="d2dee-101">La selección de texto de TextBox y PasswordBox de WPF no sigue los colores del sistema</span><span class="sxs-lookup"><span data-stu-id="d2dee-101">WPF TextBox/PasswordBox Text Selection Does Not Follow System Colors</span></span>

#### <a name="details"></a><span data-ttu-id="d2dee-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d2dee-102">Details</span></span>

<span data-ttu-id="d2dee-103">En .NET Framework 4.7.1 y versiones anteriores, `System.Windows.Controls.TextBox` y `System.Windows.Controls.PasswordBox` de WPF solo podían representar una selección de texto en la capa de adornos.</span><span class="sxs-lookup"><span data-stu-id="d2dee-103">In .NET Framework 4.7.1 and earlier versions, WPF `System.Windows.Controls.TextBox` and `System.Windows.Controls.PasswordBox` could only render a text selection in the Adorner layer.</span></span> <span data-ttu-id="d2dee-104">En algunos temas del sistema, esto tapaba el texto, y resultaba difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="d2dee-104">In some system themes this would occlude text, making it hard to read.</span></span>  <span data-ttu-id="d2dee-105">En .NET Framework 4.7.2 y versiones posteriores, los desarrolladores tienen una opción de habilitar un esquema de representación de la selección que no se basa en los adornos y que alivia este problema.</span><span class="sxs-lookup"><span data-stu-id="d2dee-105">In .NET Framework 4.7.2 and later, developers have an option of enabling a non-Adorner-based selection rendering scheme that alleviates this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d2dee-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d2dee-106">Suggestion</span></span>

<span data-ttu-id="d2dee-107">Un desarrollador que quiera usar este cambio debe establecer correctamente la marca de AppContext siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2dee-107">A developer who wants to utilize this change must set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="d2dee-108">Para usar esta característica, la versión instalada de .NET Framework debe ser 4.7.2 o posterior. Para habilitar la selección no basada en los adornos, use la marca de AppContext siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2dee-108">To utilize this feature, the installed .NET Framework version must be 4.7.2 or greater.To enabled the non-adorner-based selection, use the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="d2dee-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d2dee-109">Name</span></span>    | <span data-ttu-id="d2dee-110">Valor</span><span class="sxs-lookup"><span data-stu-id="d2dee-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d2dee-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d2dee-111">Scope</span></span>   | <span data-ttu-id="d2dee-112">Borde</span><span class="sxs-lookup"><span data-stu-id="d2dee-112">Edge</span></span>        |
| <span data-ttu-id="d2dee-113">Versión</span><span class="sxs-lookup"><span data-stu-id="d2dee-113">Version</span></span> | <span data-ttu-id="d2dee-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d2dee-114">4.7.2</span></span>       |
| <span data-ttu-id="d2dee-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="d2dee-115">Type</span></span>    | <span data-ttu-id="d2dee-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="d2dee-116">Retargeting</span></span> |
