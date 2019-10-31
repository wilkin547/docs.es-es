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
ms.openlocfilehash: f77ff394668a235dd63cf0cddf71ea418a28125b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141687"
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
de Contraseña asociada a `strUser`.

`strAuthority`\
de El nombre de dominio del usuario. Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

`impLevel`\
de Nivel de suplantación.

`authnLevel`\
de Nivel de autorización.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WinError. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Uno o varios argumentos no son válidos. |
| `E_POINTER` | 0x80004003 | El valor de `pIWbemServices` es `null`. | 
| `E_FAIL` | 0x80000008 | Se ha producido un error no especificado. |
| `E_OUTOFMEMORY` | 0x80000002 | No hay suficiente memoria disponible para realizar la operación. | 
| `S_OK` | 0 | La llamada de función se realizó correctamente. | 

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** WMINet_Utils. idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
