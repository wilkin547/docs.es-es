---
title: "Función BlessIWbemServices (referencia de API no administrada)"
description: "La función BlessIWbemServices indica si las credenciales de usuario permiten el acceso a una clase IWbemServices."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f384e8d045dd7a6f2f864f0991f8caf4a674408b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="blessiwbemservices-function"></a>BlessIWbemServices (función)
Indica si las credenciales de usuario permiten el acceso a la especificada [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) clase.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
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

`pIWbemServices`  
[in] Un puntero a la [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) para el que se requieren permisos de objeto.

`strUser`  
[in] El nombre de usuario.

`strPassword`  
[in] La contraseña asociada a `strUser`.

`strAuthority`[in] El nombre de dominio del usuario. Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.

`impLevel`[in] El nivel de suplantación.

`authnLevel`[in] El nivel de autorización.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WinError.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `E_INVALIDARG` | 0 x 80070057 | Uno o más argumentos no son válidos. |
| `E_POINTER` | 0 x 80004003 | El valor de `pIWbemServices` es `null`. | 
| `E_FAIL` | 0x80000008 | Se ha producido un error no especificado. |
| `E_OUTOFMEMORY` | 0x80000002 | Hay suficiente memoria disponible para realizar la operación. | 
| `S_OK` | 0 | La llamada de función tuvo éxito. | 

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
