---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496748"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="ee05b-101">Se llama repetidas veces a PreviewLostKeyboardFocus si su controlador muestra un cuadro de mensaje de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee05b-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="ee05b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ee05b-102">Details</span></span>

<span data-ttu-id="ee05b-103">A partir de .NET Framework 4.5, si se llama a <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> desde un controlador de <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>, se volverá a activar el controlador al cerrar el cuadro de mensaje, lo que podría generar un bucle infinito de cuadros de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ee05b-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ee05b-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ee05b-104">Suggestion</span></span>

<span data-ttu-id="ee05b-105">Hay dos opciones para solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="ee05b-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="ee05b-106">Se puede evitar llamando a <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> en lugar de a <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee05b-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="ee05b-107">Se puede evitar mostrando el cuadro de mensaje desde un controlador de eventos <xref:System.Windows.UIElement.LostKeyboardFocus> (en contraposición a un controlador de eventos <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="ee05b-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="ee05b-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ee05b-108">Name</span></span>    | <span data-ttu-id="ee05b-109">Valor</span><span class="sxs-lookup"><span data-stu-id="ee05b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ee05b-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ee05b-110">Scope</span></span>   |<span data-ttu-id="ee05b-111">Borde</span><span class="sxs-lookup"><span data-stu-id="ee05b-111">Edge</span></span>|
|<span data-ttu-id="ee05b-112">Versión</span><span class="sxs-lookup"><span data-stu-id="ee05b-112">Version</span></span>|<span data-ttu-id="ee05b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="ee05b-113">4.5</span></span>|
|<span data-ttu-id="ee05b-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee05b-114">Type</span></span>|<span data-ttu-id="ee05b-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ee05b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ee05b-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ee05b-116">Affected APIs</span></span>

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
