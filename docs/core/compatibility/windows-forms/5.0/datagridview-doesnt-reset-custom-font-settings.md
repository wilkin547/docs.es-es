---
title: 'Cambio importante: DataGridView ya no restablece las fuentes para los estilos de celda personalizados'
description: Obtenga información sobre el cambio importante en .NET 5 donde DataGridView ya no restablece las fuentes predeterminadas de estilo de celda para que coincidan con la fuente ambiente si se ha personalizado la fuente del estilo de celda.
ms.date: 10/18/2020
ms.openlocfilehash: fd28fb5a0b508157289dde1b720522ed49163e31
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256135"
---
# <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a><span data-ttu-id="d9bb8-103">DataGridView ya no restablece las fuentes para los estilos de celda personalizados</span><span class="sxs-lookup"><span data-stu-id="d9bb8-103">DataGridView no longer resets fonts for customized cell styles</span></span>

<span data-ttu-id="d9bb8-104">Cuando la fuente ambiente cambia, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> ya no restablece las fuentes predeterminadas de estilo de celda para que coincidan con la fuente ambiente si se ha personalizado la fuente del estilo de celda.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-104">When the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> no longer resets default cell style fonts to match the ambient font if the cell style font has been customized.</span></span>

## <a name="change-description"></a><span data-ttu-id="d9bb8-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d9bb8-105">Change description</span></span>

<span data-ttu-id="d9bb8-106">En versiones anteriores de .NET, si la fuente ambiente cambia, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> restablece e invalida las fuentes definidas por el usuario en las propiedades <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-106">In previous .NET versions, if the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resets and overrides user-defined fonts in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties.</span></span>

<span data-ttu-id="d9bb8-107">A partir de .NET 5, si se configuran las opciones de fuente en las propiedades <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle>, esas opciones se conservan incluso cuando cambia la fuente ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-107">Starting in .NET 5, if you configure font settings in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties, those settings are retained even when the ambient font changes.</span></span> <span data-ttu-id="d9bb8-108">Para cualquiera de estas propiedades en las que no se personalice la fuente, la fuente cambiará para que coincida con la configuración de la fuente ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-108">For any of these properties that you don't customize the font, the font will change to match the ambient font settings.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d9bb8-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d9bb8-109">Reason for change</span></span>

<span data-ttu-id="d9bb8-110">Con el [cambio de la fuente predeterminada en .NET Core 3.0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt), también cambian los valores de fuente predeterminados para los distintos estilos de celda.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-110">With the [change of the default font in .NET Core 3.0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt), the default font settings for the various cell styles also changed.</span></span> <span data-ttu-id="d9bb8-111">Este comportamiento no es el deseado para las aplicaciones que se basan en el estilo personalizado en sus controles <xref:System.Windows.Forms.DataGridViewElement.DataGridView> y ha impedido la migración de estas aplicaciones de .NET Framework a .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-111">This behavior is undesirable for apps that rely on custom styling in their <xref:System.Windows.Forms.DataGridViewElement.DataGridView> controls, and impeded the migration of these apps from .NET Framework to .NET 5.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d9bb8-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d9bb8-112">Version introduced</span></span>

<span data-ttu-id="d9bb8-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d9bb8-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d9bb8-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d9bb8-114">Recommended action</span></span>

<span data-ttu-id="d9bb8-115">No es necesario que realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-115">No action is required on your part.</span></span> <span data-ttu-id="d9bb8-116">Pero si ha personalizado la fuente en las propiedades <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle>, y quiere que la fuente coincida con la fuente ambiente, establezca <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> en `null` para cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9bb8-116">However, if you've customized the font in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties and want the font to match the ambient font, set <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> to `null` for each property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d9bb8-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d9bb8-117">Affected APIs</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

### Category

- Windows Forms

-->
