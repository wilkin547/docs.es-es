---
title: LockClrVersion (Función)
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133773"
---
# <a name="lockclrversion-function"></a>LockClrVersion (Función)
Permite al host determinar qué versión de Common Language Runtime (CLR) se utilizará en el proceso antes de inicializar explícitamente CLR.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `hostCallback`  
 de Función a la que llamará CLR al inicializarse.  
  
 `pBeginHostSetup`  
 de Función a la que llamará el host para informar al CLR de que se está iniciando la inicialización.  
  
 `pEndHostSetup`  
 de Función a la que llamará el host para informar al CLR de que la inicialización se ha completado.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|Uno o varios argumentos son NULL.|  
  
## <a name="remarks"></a>Comentarios  
 El host llama a `LockClrVersion` antes de inicializar el CLR. `LockClrVersion` toma tres parámetros, todos ellos son devoluciones de llamada de tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Este tipo se define como se indica a continuación.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Los siguientes pasos se producen tras la inicialización del tiempo de ejecución:  
  
1. El host llama a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o a una de las otras funciones de inicialización en tiempo de ejecución. Como alternativa, el host podría inicializar el tiempo de ejecución mediante la activación de objetos COM.  
  
2. El Runtime llama a la función especificada por el parámetro `hostCallback`.  
  
3. A continuación, la función especificada por `hostCallback` realiza la siguiente secuencia de llamadas:  
  
    - Función especificada por el parámetro `pBeginHostSetup`.  
  
    - `CorBindToRuntimeEx` (u otra función de inicialización en tiempo de ejecución).  
  
    - [ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    - Función especificada por el parámetro `pEndHostSetup`.  
  
 Todas las llamadas de `pBeginHostSetup` a `pEndHostSetup` deben producirse en un único subproceso o fibra, con la misma pila lógica. Este subproceso puede ser diferente del subproceso en el que se llama a `hostCallback`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
