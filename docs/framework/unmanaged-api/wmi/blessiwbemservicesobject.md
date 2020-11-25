---
title: Función BlessIWbemServicesObject (referencia de la API no administrada)
description: La función BlessIWbemServicesObject indica si las credenciales de usuario permiten el acceso a un objeto IWbemServices
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1aab2076f57f938715a3e65481a3540dc52279c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719754"
---
# <a name="blessiwbemservicesobject-function"></a>Función BlessIWbemServicesObject

Indica si las credenciales de usuario permiten el acceso a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) especificado.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a>Parámetros

`pIWbemServices`\
de Un puntero a un objeto de servicio WMI.

`strUser`\
de El nombre de usuario.

`strPassword`\
de La contraseña asociada a `strUser` .

`strAuthority`\
de El nombre de dominio del usuario. Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

`impLevel`\
de Nivel de suplantación.

`authnLevel`\
de Nivel de autorización.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WinError. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Uno o varios argumentos no son válidos. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` es `null`. |
| `E_FAIL` | 0x80000008 | Error no especificado. |
| `E_OUTOFMEMORY` | 0x80000002 | No hay suficiente memoria disponible para realizar la operación. |
| `S_OK` | 0 | La llamada de función se realizó correctamente. |

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** WMINet_Utils. idl

 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
