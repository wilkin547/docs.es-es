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
ms.openlocfilehash: 0e1395229b67c4054df62935375a4136edf63078
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616494"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion (Función)
Crea un objeto [ICorDebug](../debugging/icordebug-interface.md) basado en la información de versión especificada.  
  
 Esta función está obsoleta en el .NET Framework 4. En su lugar, para obtener una interfaz para el Common Language Runtime (CLR) 2,0, use el método [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug. Para obtener una interfaz para CLR 4 o posterior, llame a la función [CLRCreateInstance](clrcreateinstance-function.md) y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.  
  
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
 de Versión de `ICorDebug` esperada por el depurador. Vea la enumeración [CorDebugInterfaceVersion (](../debugging/cordebuginterfaceversion-enumeration.md) para ver los valores válidos.  
  
 `szDebuggeeVersion`  
 de La versión Common Language Runtime asociada con la aplicación o el proceso que se va a depurar. Vea el método [GetVersionFromProcess (](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md) para obtener información sobre cómo recuperar este valor.  
  
 `ppCordb`  
 enuncia Ubicación que recibe un puntero al `ICorDebug` objeto.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.  
  
|Código de retorno|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szDebuggeeVersion`o `ppCordb` es null, o la cadena de versión es incorrecta.|  
  
## <a name="remarks"></a>Observaciones  
 El `szDebuggeeVersion` parámetro se asigna a la versión correspondiente de MSCorDbi. dll.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
