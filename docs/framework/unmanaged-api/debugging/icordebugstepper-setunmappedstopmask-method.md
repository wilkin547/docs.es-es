---
title: ICorDebugStepper::SetUnmappedStopMask (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474961"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask (Método)
Establece un valor que especifica el tipo de código no asignado en el que se detendrá la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mask`  
 [in] Un valor de la enumeración CorDebugUnmappedStop que especifica el tipo de código no asignado en el que el depurador detendrá la ejecución.  
  
 El valor predeterminado es STOP_OTHER_UNMAPPED. El valor STOP_UNMANAGED sólo es válido con la depuración de interoperabilidad.  
  
## <a name="remarks"></a>Comentarios  
 Cuando el depurador encuentra la compilación just-in-time (JIT) que no tiene ninguna asignación correspondiente al lenguaje intermedio de Microsoft (MSIL), detiene la ejecución si se ha establecido la marca que especifica ese tipo de código no asignado; en caso contrario, ejecución paso a paso de forma transparente continúa.  
  
 Si el depurador no usa un motor paso a paso para especificar un método, a continuación, no necesariamente recorrerá paso a través de código no asignado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
