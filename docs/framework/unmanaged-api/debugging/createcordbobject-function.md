---
title: "CreateCordbObject (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCoredbObject
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06e08148e5526d65d82eca52ffe8db66a4e7df6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="createcordbobject-function"></a>CreateCordbObject (Función)
Crea una interfaz de depurador ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) que proporciona la funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `iDebuggerVersion`  
 [in] Versión de depuración del proceso de destino. Este parámetro debe ser CorDebugVersion_2_0 para la depuración remota.  
  
 `ppCordb`  
 [out] Puntero a un puntero a un objeto que se convertirán a un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaz y devuelve.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.  
  
 E_INVALIDARG  
 `ppCordb` es nulo o `iDebuggerVersion` no es CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppCordb`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="remarks"></a>Comentarios  
 El [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaz que se devuelve en `ppCordb` es la interfaz de depuración de nivel superior para todos los servicios de depuración administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **Versiones de .NET framework:** 3.5 SP1
