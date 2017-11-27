---
title: "ICorDebugILFrame2::RemapFunction (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2.RemapFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4def20bc51d1b01b1c05b81a89fc3c983b4d1219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction (Método)
Reasigna una función editada especificando el nuevo desplazamiento de lenguaje intermedio (MSIL) de Microsoft  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `newILOffset`  
 [in] Nuevo desplazamiento de MSIL del marco de pila en el que se debe colocar el puntero de instrucción. Este valor debe ser un punto de secuencia.  
  
 Es responsabilidad del llamador para garantizar la validez de este valor. Por ejemplo, el desplazamiento MSIL no es válido si está fuera de los límites de la función.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se ha editado la función de un marco, el depurador puede llamar a la `RemapFunction` método intercambiar en la versión más reciente de la función del marco para que se pueda ejecutar. Se iniciará la ejecución del código en el desplazamiento dado de MSIL.  
  
> [!NOTE]
>  Al llamar a `RemapFunction`, como una llamada a [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), inmediatamente se invalidarán todas las interfaces de depuración que están relacionados con la generación de un seguimiento de pila para el subproceso. Estas interfaces incluyen [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame y ICorDebugNativeFrame.  
  
 El `RemapFunction` método puede llamarse únicamente en el contexto del fotograma actual y sólo en uno de los siguientes casos:  
  
-   Después de recibir un [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) devolución de llamada que todavía no ha continuado.  
  
-   Aunque la ejecución de código se detiene debido un [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) eventos de este fotograma.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
