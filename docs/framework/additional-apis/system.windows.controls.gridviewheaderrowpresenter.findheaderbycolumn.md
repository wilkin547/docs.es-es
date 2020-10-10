---
title: Método FindHeaderByColumn (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Obtenga información sobre el método privado de WPF llamado FindHeaderByColumn.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877799"
---
# <a name="findheaderbycolumn-method"></a><span data-ttu-id="06d6c-103">Método FindHeaderByColumn</span><span class="sxs-lookup"><span data-stu-id="06d6c-103">FindHeaderByColumn method</span></span>

<span data-ttu-id="06d6c-104">Busca el encabezado de columna para la columna especificada en el árbol visual.</span><span class="sxs-lookup"><span data-stu-id="06d6c-104">Finds the column header for the specified column in the visual tree.</span></span>

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> <span data-ttu-id="06d6c-105">Este método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="06d6c-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="06d6c-106">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="06d6c-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="06d6c-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="06d6c-107">Parameters</span></span>

<span data-ttu-id="06d6c-108">`column` <xref:System.Windows.Controls.GridViewColumn></span><span class="sxs-lookup"><span data-stu-id="06d6c-108">`column` <xref:System.Windows.Controls.GridViewColumn></span></span>\
<span data-ttu-id="06d6c-109">Columna cuyo encabezado se debe buscar y devolver.</span><span class="sxs-lookup"><span data-stu-id="06d6c-109">The column whose header should be found and returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="06d6c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="06d6c-110">Return value</span></span>

<xref:System.Windows.Controls.GridViewColumnHeader>\
<span data-ttu-id="06d6c-111">El encabezado de la columna especificada, o `null` si la columna especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="06d6c-111">The header of the specified column, or `null` if the specified column doesn't exist.</span></span>

## <a name="requirements"></a><span data-ttu-id="06d6c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06d6c-112">Requirements</span></span>

<span data-ttu-id="06d6c-113">**Espacio de nombres:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="06d6c-113">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="06d6c-114">**Ensamblado:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="06d6c-114">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="06d6c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06d6c-115">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
