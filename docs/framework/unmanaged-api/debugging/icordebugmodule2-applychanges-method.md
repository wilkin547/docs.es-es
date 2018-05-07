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
ms.openlocfilehash: 5a406e945a67352bc7f126b40bd56f4a11dd693b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges (Método)
Aplica los cambios en los metadatos y los cambios en el código de lenguaje intermedio (MSIL) de Microsoft a los procesos en ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cbMetadata`  
 [in] Tamaño, en bytes, de los metadatos de delta.  
  
 `pbMetadata`  
 [in] Búfer que contiene los metadatos delta. La dirección del búfer se devuelve desde el [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) método.  
  
 Las direcciones virtuales relativas (RVA) en los metadatos deben ser relativas al inicio del código MSIL.  
  
 `cbIL`  
 [in] Tamaño, en bytes, del código delta de MSIL.  
  
 `pbIL`  
 [in] Búfer que contiene el código MSIL actualizado.  
  
## <a name="remarks"></a>Comentarios  
 El `pbMetadata` parámetro tiene un formato de metadatos delta especial (como salida por [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` toma los metadatos anteriores como base y describe los cambios individuales que se aplican a esa base.  
  
 En cambio, la `pbIL[`] parámetro contiene el nuevo MSIL para el método actualizado y está destinada a reemplazar completamente el MSIL del método anterior  
  
 Cuando la diferencia de MSIL y los metadatos se han creado en la memoria del depurador, el depurador llama `ApplyChanges` para enviar los cambios en common language runtime (CLR). El tiempo de ejecución actualiza las tablas de metadatos, coloca el nuevo MSIL en el proceso y configura una compilación de just-in-time (JIT) del nuevo MSIL. Si se han aplicado los cambios, el depurador debe llamar a [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) para prepararse para la siguiente sesión de edición. El depurador, a continuación, puede continuar con el proceso.  
  
 Cada vez que el depurador llama `ApplyChanges` en un módulo que contiene los metadatos de delta, también debe llamar [ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) con los mismos metadatos delta en todas las copias de los metadatos de ese módulo excepto la copia usado para emitir los cambios. Si una copia de los metadatos se convierte en algún modo fuera de sincronización con los metadatos reales, el depurador siempre puede deshacerse de esa copia y obtenga una nueva copia.  
  
 Si el `ApplyChanges` método produce un error, la depuración sesión está en un estado no válido y debe reiniciarse.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
