---
description: 'Más información acerca de: ICorDebugModule:: EnableJITDebugging ((método)'
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
ms.openlocfilehash: 30077bd586e1cb9cb8766290804e31f5999d9e72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722690"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>ICorDebugModule::EnableJITDebugging (Método)

Controla si el compilador Just-in-Time (JIT) conserva la información de depuración de los métodos de este módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `bTrackJITInfo`  
 de Establezca este valor en `true` para permitir que el compilador JIT conserve la información de asignación entre la versión del lenguaje intermedio de Microsoft (MSIL) y la versión compilada con JIT de cada método de este módulo.  
  
 `bAllowJitOpts`  
 de Establezca este valor en `true` para permitir que el compilador JIT genere código con ciertas optimizaciones específicas de JIT para la depuración.  
  
## <a name="remarks"></a>Observaciones  

 La depuración JIT está habilitada de forma predeterminada para todos los módulos que se cargan cuando el depurador está activo. La habilitación o deshabilitación de la configuración mediante programación invalida la configuración global.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
