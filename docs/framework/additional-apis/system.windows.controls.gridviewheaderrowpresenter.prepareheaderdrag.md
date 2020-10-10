---
title: Método PrepareHeaderDrag (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Obtenga información sobre el método privado de WPF llamado PrepareHeaderDrag.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877793"
---
# <a name="prepareheaderdrag-method"></a><span data-ttu-id="d44ed-103">Método PrepareHeaderDrag</span><span class="sxs-lookup"><span data-stu-id="d44ed-103">PrepareHeaderDrag method</span></span>

<span data-ttu-id="d44ed-104">Prepara el encabezado de columna especificado para la reordenación.</span><span class="sxs-lookup"><span data-stu-id="d44ed-104">Prepares the specified column header for reordering.</span></span>

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> <span data-ttu-id="d44ed-105">Este método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="d44ed-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d44ed-106">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="d44ed-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="d44ed-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="d44ed-107">Parameters</span></span>

<span data-ttu-id="d44ed-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span><span class="sxs-lookup"><span data-stu-id="d44ed-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span></span>\
<span data-ttu-id="d44ed-109">Encabezado de columna que se va a preparar para la reordenación.</span><span class="sxs-lookup"><span data-stu-id="d44ed-109">The column header to prepare for reordering.</span></span>

<span data-ttu-id="d44ed-110">`pos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="d44ed-110">`pos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="d44ed-111">Posición, relativa a <xref:System.Windows.Controls.GridViewHeaderRowPresenter> , donde comienza el arrastre.</span><span class="sxs-lookup"><span data-stu-id="d44ed-111">The position, relative to <xref:System.Windows.Controls.GridViewHeaderRowPresenter>, where the dragging starts.</span></span>

<span data-ttu-id="d44ed-112">`relativePos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="d44ed-112">`relativePos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="d44ed-113">Posición, relativa a `header` , donde comienza el arrastre.</span><span class="sxs-lookup"><span data-stu-id="d44ed-113">The position, relative to `header`, where the dragging starts.</span></span>

<span data-ttu-id="d44ed-114">`cancelInvoke` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="d44ed-114">`cancelInvoke` <xref:System.Boolean></span></span>\
<span data-ttu-id="d44ed-115">`true` para cancelar la reordenación; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="d44ed-115">`true` to cancel the reordering; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d44ed-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d44ed-116">Requirements</span></span>

<span data-ttu-id="d44ed-117">**Espacio de nombres:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="d44ed-117">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="d44ed-118">**Ensamblado:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="d44ed-118">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="d44ed-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d44ed-119">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
