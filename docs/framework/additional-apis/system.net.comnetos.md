---
title: Clase comnetos (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990520"
---
# <a name="comnetos-class"></a>Clase comnetos

Proporciona información sobre el sistema operativo actual, como su tipo de instalación y versión (cliente o servidor). No se puede heredar esta clase.
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="iswin7orlater-field"></a>Campo IsWin7orLater

Especifica si la versión del sistema operativo es Windows 7 o posterior.

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
