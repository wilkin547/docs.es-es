---
description: 'Más información sobre: clase de comnetos'
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
ms.openlocfilehash: 7376fe4a5e02818907cb71573451fffb3a3667cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802533"
---
# <a name="comnetos-class"></a>Clase ComNetOS

Proporciona información sobre el sistema operativo actual, como su tipo de instalación y versión (cliente o servidor). Esta clase no puede heredarse.
  
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
