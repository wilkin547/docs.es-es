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
# <a name="findheaderbycolumn-method"></a>Método FindHeaderByColumn

Busca el encabezado de columna para la columna especificada en el árbol visual.

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> Este método es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="parameters"></a>Parameters

`column` <xref:System.Windows.Controls.GridViewColumn>\
Columna cuyo encabezado se debe buscar y devolver.

## <a name="return-value"></a>Valor devuelto

<xref:System.Windows.Controls.GridViewColumnHeader>\
El encabezado de la columna especificada, o `null` si la columna especificada no existe.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Windows.Controls>

**Ensamblado:** PresentationFramework.dll

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
