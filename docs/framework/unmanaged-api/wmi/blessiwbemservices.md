---
title: Función BlessIWbemServices (Referencia de API no administrada)
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
ms.openlocfilehash: 4b15af840cc00b3ec261604db4f3625c6b975d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176869"
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
[en] Puntero al objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) para el que se requieren permisos.

`strUser`\
[en] El nombre de usuario.

`strPassword`\
[en] La contraseña `strUser`asociada a .

`strAuthority`\
[en] El nombre de dominio del usuario. Consulte la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.

`impLevel`\
[en] El nivel de suplantación.

`authnLevel`\
[en] El nivel de autorización.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WinError.h* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Uno o más argumentos no son válidos. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` es `null`. |
| `E_FAIL` | 0x80000008 | Error no especificado. |
| `E_OUTOFMEMORY` | 0x80000002 | Hay suficiente memoria disponible para realizar la operación. |
| `S_OK` | 0 | La llamada de función se realizó correctamente. |

## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
