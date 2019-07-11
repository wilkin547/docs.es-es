---
title: ICorDebugILFrame2::RemapFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdcc2eccbb24a92643415db8e5d267033ac1ca0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758751"
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction (Método)
Reasigna una función editada especificando el nuevo desplazamiento de lenguaje intermedio (MSIL) de Microsoft  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `newILOffset`  
 [in] Nuevo desplazamiento de MSIL del marco de pila en el que se debe colocar el puntero de instrucción. Este valor debe ser un punto de secuencia.  
  
 Es responsabilidad del llamador para garantizar la validez de este valor. Por ejemplo, el desplazamiento MSIL no es válido si se encuentra fuera de los límites de la función.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se ha editado la función de un marco, el depurador puede llamar a la `RemapFunction` método intercambiar en la versión más reciente de la función del marco, por lo que se puede ejecutar. Se iniciará la ejecución del código en el desplazamiento dado de MSIL.  
  
> [!NOTE]
>  Una llamada a `RemapFunction`, como una llamada a [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), inmediatamente se invalidarán todas las interfaces de depuración que están relacionados con la generación de un seguimiento de pila del subproceso. Estas interfaces incluyen [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame y ICorDebugNativeFrame.  
  
 El `RemapFunction` método puede llamarse únicamente en el contexto del fotograma actual y sólo en uno de los casos siguientes:  
  
- Después de recibir un [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) devolución de llamada que todavía no ha continuado.  
  
- Mientras se detiene la ejecución de código debido un [EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) eventos para este marco.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
