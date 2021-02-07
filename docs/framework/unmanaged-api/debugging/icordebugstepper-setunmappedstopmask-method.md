---
description: 'Más información acerca de: ICorDebugStepper:: Setunmappedstopmask ((método)'
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
ms.openlocfilehash: 60b8fd4b74e1eeb76868fc6cdac308ff805e44db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717723"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask (Método)

Establece un valor que especifica el tipo de código no asignado en el que se detendrá la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mask`  
 de Un valor de la enumeración Cordebugunmappedstop (que especifica el tipo de código no asignado en el que el depurador detendrá la ejecución.  
  
 El valor predeterminado es STOP_OTHER_UNMAPPED. El valor STOP_UNMANAGED solo es válido con la depuración de interoperabilidad.  
  
## <a name="remarks"></a>Observaciones  

 Cuando el depurador encuentra una compilación Just-in-Time (JIT) que no tiene ninguna asignación correspondiente al lenguaje intermedio de Microsoft (MSIL), detiene la ejecución si se ha establecido la marca que especifica el tipo de código no asignado; de lo contrario, la ejecución continuará de forma transparente.  
  
 Si el depurador no usa un stepper para entrar en un método, no tendrá que pasar por el código sin asignar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
