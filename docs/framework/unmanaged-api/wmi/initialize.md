---
title: Función Initialize (referencia de la API no administrada)
description: La función Initialize realiza la inicialización de WMI.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127391"
---
# <a name="initialize-function"></a>Initialize (función)

Realiza la inicialización de la WMI.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a>Parámetros

`bAllowIManagementObjectQI`

[in] `true` para indicar que se permiten llamadas a QueryInterface en objetos WMI; de lo contrario `false`.

## <a name="return-value"></a>Valor devuelto

La función siempre devuelve `S_OK` (0).

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. def

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
