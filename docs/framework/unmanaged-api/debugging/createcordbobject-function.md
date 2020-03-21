---
title: CreateCordbObject (Función)
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179228"
---
# <a name="createcordbobject-function"></a>CreateCordbObject (Función)
Crea una interfaz de depurador ([ICorDebug](icordebug-interface.md)) que proporciona funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `iDebuggerVersion`  
 [in] Versión de depuración del proceso de destino. Este parámetro debe ser CorDebugVersion_2_0 para la depuración remota.  
  
 `ppCordb`  
 [fuera] Puntero a un puntero a un objeto que se convertirá a un [ICorDebug](icordebug-interface.md) interfaz y se devolverá.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.  
  
 E_INVALIDARG  
 `ppCordb` es nulo o `iDebuggerVersion` no es CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppCordb`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="remarks"></a>Observaciones  
 El [ICorDebug](icordebug-interface.md) interfaz `ppCordb` que se devuelve en es la interfaz de depuración de nivel superior para todos los servicios de depuración administrados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **Versiones de .NET Framework:** 3.5 SP1
