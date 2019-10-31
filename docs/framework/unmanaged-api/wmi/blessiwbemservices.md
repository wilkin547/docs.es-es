---
title: Función BlessIWbemServices (referencia de la API no administrada)
description: La función BlessIWbemServices indica si las credenciales de usuario permiten el acceso a una clase IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 946d29892052ea69c2a8a3bf11e7be7a1b2d7068
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138780"
---
# <a name="blessiwbemservices-function"></a>Función BlessIWbemServices
Indica si las credenciales de usuario permiten el acceso a la clase [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) especificada.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a>Parámetros

`pIWbemServices`\
de Puntero al objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) para el que se requieren permisos.

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
