---
title: Exception. PrepForRemoting (método) (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214896"
---
# <a name="exceptionprepforremoting-method"></a>Método Exception.PrepForRemoting

Conserva el seguimiento de la pila del servidor al anexarlo al mensaje antes de que se vuelva a producir la excepción en el sitio de llamada de cliente.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Devuelve

<xref:System.Exception>  
Esta instancia de <xref:System.Exception>.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El método `Exception.PrepForRemoting` es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System>

**Ensamblado:** mscorlib. dll (en mscorlib. dll)

**.NET Framework versiones:** Disponible desde 1,0.
