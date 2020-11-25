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
ms.openlocfilehash: 2ff08ec8f194ccc9e968b3a7ee017afe788f4b03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704947"
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

 El host llama a `LockClrVersion` antes de inicializar el CLR. `LockClrVersion` toma tres parámetros, todos ellos son devoluciones de llamada de tipo [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md). Este tipo se define como se indica a continuación.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Los siguientes pasos se producen tras la inicialización del tiempo de ejecución:  
  
1. El host llama a [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o a una de las otras funciones de inicialización en tiempo de ejecución. Como alternativa, el host podría inicializar el tiempo de ejecución mediante la activación de objetos COM.  
  
2. El Runtime llama a la función especificada por el `hostCallback` parámetro.  
  
3. La función especificada por `hostCallback` entonces realiza la siguiente secuencia de llamadas:  
  
    - Función especificada por el `pBeginHostSetup` parámetro.  
  
    - `CorBindToRuntimeEx` (u otra función de inicialización en tiempo de ejecución).  
  
    - [ICLRRuntimeHost:: SetHostControl](iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).  
  
    - Función especificada por el `pEndHostSetup` parámetro.  
  
 Todas las llamadas de `pBeginHostSetup` a `pEndHostSetup` deben producirse en un único subproceso o fibra, con la misma pila lógica. Este subproceso puede ser diferente del subproceso en el que `hostCallback` se llama a.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
