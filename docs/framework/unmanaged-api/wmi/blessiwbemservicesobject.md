---
title: BlessIWbemServicesObject (función) (referencia de API no administrada)
description: BlessIWbemServicesObject (función) indica si las credenciales de usuario permiten el acceso a un objeto IWbemServices
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7f24606e3b021b0df5bdbaab795e4f672f724fa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761716"
---
# <a name="blessiwbemservicesobject-function"></a>Función BlessIWbemServicesObject
Indica si las credenciales de usuario permiten el acceso a un determinado [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) objeto. 

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
[in] Un puntero a un objeto de servicio WMI.

`strUser`\
[in] El nombre de usuario.

`strPassword`\
[in] La contraseña asociada con `strUser`.

`strAuthority`\
[in] El nombre de dominio del usuario. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

`impLevel`\
[in] El nivel de suplantación.

`authnLevel`\
[in] El nivel de autorización.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WinError.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Uno o más argumentos no son válidos. |
| `E_POINTER` | 0x80004003 | El valor de `pIWbemServices` es `null`. | 
| `E_FAIL` | 0x80000008 | Se ha producido un error no especificado. |
| `E_OUTOFMEMORY` | 0x80000002 | No hay memoria suficiente está disponible para realizar la operación. | 
| `S_OK` | 0 | La llamada de función fue correcta. | 

## <a name="requirements"></a>Requisitos

 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Encabezado**: WMINet_Utils.idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
