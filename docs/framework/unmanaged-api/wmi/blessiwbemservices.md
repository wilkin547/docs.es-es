---
title: BlessIWbemServices (función) (referencia de API no administrada)
description: BlessIWbemServices (función) indica si las credenciales de usuario permiten el acceso a una clase IWbemServices.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb83bc3c0c7724dbcd3133465d4e7ad3a9eea3a9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636506"
---
# <a name="blessiwbemservices-function"></a>Función BlessIWbemServices
Indica si las credenciales de usuario permiten el acceso a la especificada [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) clase.   
  
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

`pIWbemServices`\
[in] Un puntero a la [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) para el que se requieren permisos de objeto.

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

|Constante  |Valor  |Descripción  |
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
