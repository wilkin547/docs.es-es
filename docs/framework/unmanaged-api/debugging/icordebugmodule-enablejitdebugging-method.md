---
title: ICorDebugModule::EnableJITDebugging (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71722293bfb80a7e57393916560f922d970ea2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>ICorDebugModule::EnableJITDebugging (Método)
Controla si el compilador de just-in-time (JIT) conserva la información de depuración para los métodos de este módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `bTrackJITInfo`  
 [in] Establezca este valor en `true` para permitir que el compilador JIT conservar la información de asignación entre la versión de lenguaje intermedio (MSIL) de Microsoft y la versión de compilación JIT de cada método en este módulo.  
  
 `bAllowJitOpts`  
 [in] Establezca este valor en `true` para permitir que el compilador JIT generar el código con ciertas optimizaciones específicas de JIT para la depuración.  
  
## <a name="remarks"></a>Comentarios  
 Depuración JIT está habilitada de forma predeterminada para todos los módulos que se cargan cuando el depurador está activo. Habilitar o deshabilitar a la configuración mediante programación reemplaza la configuración global.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
