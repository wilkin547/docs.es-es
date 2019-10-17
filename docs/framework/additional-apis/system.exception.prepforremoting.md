---
title: Exception. PrepForRemoting (método) (System)
author: mairaw
ms.author: mairaw
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 057390d64f70d3cb8eba7d4b29b94570fdca77e3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72405901"
---
# <a name="exceptionprepforremoting-method"></a>Exception. PrepForRemoting (método)

Conserva el seguimiento de la pila del servidor al anexarlo al mensaje antes de que se vuelva a producir la excepción en el sitio de llamada de cliente.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Valores devueltos

<xref:System.Exception>  
Esta instancia de <xref:System.Exception>.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `Exception.PrepForRemoting` es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System>

**Ensamblado:** mscorlib. dll (en mscorlib. dll)

**.NET Framework versiones:** Disponible desde 1,0.
