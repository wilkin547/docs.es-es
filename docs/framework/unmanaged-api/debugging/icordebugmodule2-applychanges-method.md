---
title: ICorDebugModule2::ApplyChanges (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 860b87b09ee487f893a1bba2aaa34292c50ffcb7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764340"
---
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges (Método)
Aplica los cambios en los metadatos y los cambios en el código de lenguaje intermedio (MSIL) de Microsoft a los procesos en ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cbMetadata`  
 [in] Tamaño, en bytes, de los metadatos de delta.  
  
 `pbMetadata`  
 [in] Búfer que contiene los metadatos delta. La dirección del búfer se devuelve desde el [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) método.  
  
 Las direcciones virtuales relativas (RVA) en los metadatos deben ser relativo al inicio del código MSIL.  
  
 `cbIL`  
 [in] Tamaño, en bytes, del código MSIL delta.  
  
 `pbIL`  
 [in] Búfer que contiene el código MSIL actualizado.  
  
## <a name="remarks"></a>Comentarios  
 El `pbMetadata` parámetro está en un formato de metadatos delta especial (como salida por [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` toma los metadatos anteriores como base y se describen los cambios individuales que se aplican a esa base.  
  
 En cambio, el `pbIL[`] parámetro contiene el nuevo MSIL para el método actualizado y está pensado para reemplazar completamente el MSIL del método anterior  
  
 Cuando la diferencia de MSIL y los metadatos se han creado en la memoria del depurador, el depurador llama `ApplyChanges` para enviar los cambios en common language runtime (CLR). El tiempo de ejecución actualiza las tablas de metadatos, coloca el nuevo MSIL en el proceso y configura una compilación de just-in-time (JIT) del nuevo MSIL. Cuando se han aplicado los cambios, el depurador debe llamar a [Imetadataemit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) para prepararse para la siguiente sesión de edición. El depurador, a continuación, puede seguir el proceso.  
  
 Cada vez que el depurador llama `ApplyChanges` en un módulo que contiene los metadatos de delta, también debe llamar [ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) con los mismos metadatos delta en todas las copias de los metadatos de ese módulo excepto la copia se usa para emitir los cambios. Si una copia de los metadatos de algún modo deja fuera de sincronización con los metadatos reales, el depurador siempre puede deshacerse de esa copia y obtener una nueva copia.  
  
 Si el `ApplyChanges` método produce un error, la depuración sesión está en un estado no válido y debe reiniciarse.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
