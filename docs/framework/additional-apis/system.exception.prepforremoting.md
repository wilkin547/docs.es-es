---
title: Exception. PrepForRemoting (método) (System)
description: Revise el método Exception. PrepForRemoting en .NET. El método agrega el seguimiento de la pila del servidor al mensaje antes de que se vuelva a producir la excepción en el cliente.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105259"
---
# <a name="exceptionprepforremoting-method"></a>Método Exception.PrepForRemoting

Conserva el seguimiento de la pila del servidor al anexarlo al mensaje antes de que se vuelva a producir la excepción en el sitio de llamada de cliente.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Valores devueltos

<xref:System.Exception>  
Esta instancia de <xref:System.Exception>.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El `Exception.PrepForRemoting` método es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System>

**Ensamblado:** mscorlib.dll (en mscorlib.dll)

**.NET Framework versiones:** Disponible desde 1,0.
