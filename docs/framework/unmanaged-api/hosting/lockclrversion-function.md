---
title: "LockClrVersion (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LockClrVersion
helpviewer_keywords: LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a58d7e99f545026f6f133901ef35a1f9b9fabc7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="lockclrversion-function"></a>LockClrVersion (Función)
Permite al host determinar qué versión de common language runtime (CLR) que se utilizará en el proceso antes de inicializar el CLR de forma explícita.  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `hostCallback`  
 [in] La función que invocará el CLR en la inicialización.  
  
 `pBeginHostSetup`  
 [in] La función para ser llamado por el host para informar a CLR que la inicialización se está iniciando.  
  
 `pEndHostSetup`  
 [in] La función para ser llamado por el host para informar a CLR que la inicialización está completa.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error COM estándar, tal como se define en WinError.h, además de los valores siguientes.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_INVALIDARG|Uno o varios de los argumentos son null.|  
  
## <a name="remarks"></a>Comentarios  
 El host llama `LockClrVersion` antes de inicializar el CLR. `LockClrVersion`toma tres parámetros, todos los cuales son devoluciones de llamada de tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Este tipo se define como sigue.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Los pasos siguientes se producen cuando se inicializa el tiempo de ejecución:  
  
1.  El host llama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una de las demás funciones de inicialización en tiempo de ejecución. Como alternativa, el host puede inicializar el tiempo de ejecución mediante la activación de objetos COM.  
  
2.  El tiempo de ejecución llama a la función especificada por el `hostCallback` parámetro.  
  
3.  La función especificada por `hostCallback` , a continuación, realiza la siguiente secuencia de llamadas:  
  
    -   La función especificada por el `pBeginHostSetup` parámetro.  
  
    -   `CorBindToRuntimeEx`(o a otra función de inicialización en tiempo de ejecución).  
  
    -   [ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    -   [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    -   La función especificada por el `pEndHostSetup` parámetro.  
  
 Todas las llamadas de `pBeginHostSetup` a `pEndHostSetup` se debe producir en un único subproceso o fibra, con la misma pila lógica. Este subproceso puede ser diferente del subproceso en el que `hostCallback` se llama.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
