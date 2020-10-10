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
# <a name="prepareheaderdrag-method"></a>Método PrepareHeaderDrag

Prepara el encabezado de columna especificado para la reordenación.

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> Este método es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="parameters"></a>Parameters

`header` <xref:System.Windows.Controls.GridViewColumnHeader>\
Encabezado de columna que se va a preparar para la reordenación.

`pos` <xref:System.Windows.Point>\
Posición, relativa a <xref:System.Windows.Controls.GridViewHeaderRowPresenter> , donde comienza el arrastre.

`relativePos` <xref:System.Windows.Point>\
Posición, relativa a `header` , donde comienza el arrastre.

`cancelInvoke` <xref:System.Boolean>\
`true` para cancelar la reordenación; en caso contrario, `false` .

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Windows.Controls>

**Ensamblado:** PresentationFramework.dll

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
