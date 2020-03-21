---
title: Función SetSecurity (Referencia de API no administrada)
description: La función SetSecurity recupera el token de suplantación del subproceso actual.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176739"
---
# <a name="setsecurity-function"></a>Función SetSecurity

Recupera el token de suplantación asociado al subproceso actual.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a>Parámetros

`pNeedToReset`\
[fuera] Cuando se devuelve la función, contiene un puntero a un `boolean` que indica si el token se debe restablecer mediante una llamada a la [ResetSecurity](resetsecurity.md) función.

`token`\
[fuera] Cuando se devuelve la función, contiene un puntero al identificador del token de suplantación asociado al subproceso actual. Su valor `null` puede ser si no hay ningún token asociado con el subproceso actual.

## <a name="return-value"></a>Valor devuelto

Si la función se realiza `S_OK` correctamente, el valor devuelto es (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero. Para obtener información de error extendida, llame a la [función GetErrorInfo.](geterrorinfo.md)

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** WMINet_Utils.idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
