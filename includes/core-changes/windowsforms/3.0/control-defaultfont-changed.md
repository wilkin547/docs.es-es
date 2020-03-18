---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937004"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a><span data-ttu-id="01e40-101">Fuente de control predeterminada cambiada a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="01e40-101">Default control font changed to Segoe UI 9 pt</span></span>

#### <a name="change-description"></a><span data-ttu-id="01e40-102">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="01e40-102">Change description</span></span>

<span data-ttu-id="01e40-103">En .NET Framework, la propiedad <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> estaba establecida en `Microsoft Sans Serif 8 pt`.</span><span class="sxs-lookup"><span data-stu-id="01e40-103">In .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="01e40-104">En la imagen siguiente se muestra una ventana con la fuente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01e40-104">The following image shows a window that uses the default font.</span></span>

![Fuente de control predeterminada de .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="01e40-106">A partir de .NET Core 3.0, la fuente predeterminada está establecida en `Segoe UI 9 pt` (la misma fuente que <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="01e40-106">Starting in .NET Core 3.0, the default font is set to `Segoe UI 9 pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="01e40-107">Como resultado de este cambio, los formularios y los controles tienen un tamaño aproximadamente un 27 % mayor en razón del mayor tamaño de la nueva fuente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01e40-107">As a result of this change, forms and controls are sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="01e40-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="01e40-108">For example:</span></span>

![Fuente de control predeterminada de .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="01e40-110">Este cambio se ha realizado a fin de adaptarse a las [directrices para la experiencia de usuario de Windows](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span><span class="sxs-lookup"><span data-stu-id="01e40-110">This change was made to align with [Windows user experience (UX) guidelines](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="01e40-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="01e40-111">Version introduced</span></span>

<span data-ttu-id="01e40-112">3.0</span><span class="sxs-lookup"><span data-stu-id="01e40-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="01e40-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="01e40-113">Recommended action</span></span>

<span data-ttu-id="01e40-114">Debido al cambio en el tamaño de los formularios y controles, asegúrese de que la aplicación se representa correctamente.</span><span class="sxs-lookup"><span data-stu-id="01e40-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="01e40-115">Para conservar la fuente original, establezca la fuente predeterminada del formulario en `Microsoft Sans Serif 8 pt`.</span><span class="sxs-lookup"><span data-stu-id="01e40-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="01e40-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="01e40-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="01e40-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="01e40-117">Category</span></span>

- <span data-ttu-id="01e40-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01e40-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="01e40-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="01e40-119">Affected APIs</span></span>

<span data-ttu-id="01e40-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="01e40-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
