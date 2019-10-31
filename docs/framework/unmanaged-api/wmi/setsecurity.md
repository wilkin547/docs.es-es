---
title: Función SetSecurity (referencia de la API no administrada)
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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120226"
---
# <a name="setsecurity-function"></a>SetSecurity función)

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
enuncia Cuando la función devuelve un, contiene un puntero a un `boolean` que indica si el token se debe restablecer mediante una llamada a la función [ResetSecurity](resetsecurity.md) .

`token`\
enuncia Cuando la función devuelve un objeto, contiene un puntero al identificador del token de suplantación asociado al subproceso actual. Su valor puede ser `null` si no hay ningún token asociado al subproceso actual. 

## <a name="return-value"></a>Valor devuelto

Si la función se ejecuta correctamente, el valor devuelto es `S_OK` (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero. Para obtener información de error extendida, llame a la función [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** WMINet_Utils. idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
