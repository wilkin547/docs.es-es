---
ms.openlocfilehash: 2aa6603e2ed77ffa94fbc6325cd5db50985bda6a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620680"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="04626-101">Se llama repetidas veces a PreviewLostKeyboardFocus si su controlador muestra un cuadro de mensaje de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="04626-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="04626-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="04626-102">Details</span></span>

<span data-ttu-id="04626-103">A partir de .NET Framework 4.5, si se llama a <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> desde un controlador de <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>, se volverá a activar el controlador al cerrar el cuadro de mensaje, lo que podría generar un bucle infinito de cuadros de mensaje.</span><span class="sxs-lookup"><span data-stu-id="04626-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="04626-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="04626-104">Suggestion</span></span>

<span data-ttu-id="04626-105">Hay dos opciones para solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="04626-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="04626-106">Se puede evitar llamando a <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> en lugar de a <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04626-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="04626-107">Se puede evitar mostrando el cuadro de mensaje desde un controlador de eventos <xref:System.Windows.UIElement.LostKeyboardFocus> (en contraposición a un controlador de eventos <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="04626-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="04626-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="04626-108">Name</span></span>    | <span data-ttu-id="04626-109">Valor</span><span class="sxs-lookup"><span data-stu-id="04626-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="04626-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="04626-110">Scope</span></span>   |<span data-ttu-id="04626-111">Borde</span><span class="sxs-lookup"><span data-stu-id="04626-111">Edge</span></span>|
|<span data-ttu-id="04626-112">Versión</span><span class="sxs-lookup"><span data-stu-id="04626-112">Version</span></span>|<span data-ttu-id="04626-113">4.5</span><span class="sxs-lookup"><span data-stu-id="04626-113">4.5</span></span>|
|<span data-ttu-id="04626-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="04626-114">Type</span></span>|<span data-ttu-id="04626-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="04626-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="04626-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="04626-116">Affected APIs</span></span>

-<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
