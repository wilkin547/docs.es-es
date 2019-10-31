---
title: CreateDebuggingInterfaceFromVersion (Función)
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: e23dfb86c2129a02a0ca95de8c89d8294e97ad81
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136835"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion (Función)
Crea un objeto [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) basado en la información de versión especificada.  
  
 Esta función está obsoleta en el .NET Framework 4. En su lugar, para obtener una interfaz para el Common Language Runtime (CLR) 2,0, use el método [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug. Para obtener una interfaz para CLR 4 o posterior, llame a la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `iDebuggerVersion`  
 de La versión de `ICorDebug` esperada por el depurador. Vea la enumeración [CorDebugInterfaceVersion (](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) para ver los valores válidos.  
  
 `szDebuggeeVersion`  
 de La versión Common Language Runtime asociada con la aplicación o el proceso que se va a depurar. Vea el método [GetVersionFromProcess (](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion (](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) para obtener información sobre cómo recuperar este valor.  
  
 `ppCordb`  
 enuncia Ubicación que recibe un puntero al objeto de `ICorDebug`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szDebuggeeVersion` o `ppCordb` es null, o la cadena de versión es incorrecta.|  
  
## <a name="remarks"></a>Comentarios  
 El parámetro `szDebuggeeVersion` se asigna a la versión correspondiente de MSCorDbi. dll.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
