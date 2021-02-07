---
description: 'Más información acerca de: CreateDebuggingInterfaceFromVersion ((función)'
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
ms.openlocfilehash: 163ada49f028071b48c93ee3c565152a773782ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760638"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion (Función)

Crea un objeto [ICorDebug](../debugging/icordebug-interface.md) basado en la información de versión especificada.  
  
 Esta función está obsoleta en el .NET Framework 4. En su lugar, para obtener una interfaz para el Common Language Runtime (CLR) 2,0, use el método [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug. Para obtener una interfaz para CLR 4 o posterior, llame a la función [CLRCreateInstance](clrcreateinstance-function.md) y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.  
  
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
 de La versión Common Language Runtime asociada con la aplicación o el proceso que se va a depurar. Vea el método [GetVersionFromProcess (](getversionfromprocess-function.md) o [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md) para obtener información sobre cómo recuperar este valor.  
  
 `ppCordb`  
 enuncia Ubicación que recibe un puntero al `ICorDebug` objeto.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|`szDebuggeeVersion` o `ppCordb` es null, o la cadena de versión es incorrecta.|  
  
## <a name="remarks"></a>Observaciones  

 El `szDebuggeeVersion` parámetro se asigna a la versión correspondiente de MSCorDbi.dll.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
