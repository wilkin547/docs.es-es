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
ms.openlocfilehash: a6b1a7c9be821890a3f15d8c3297273607f5bedd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709705"
---
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges (Método)

Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.  
  
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
 de Tamaño, en bytes, de los metadatos Delta.  
  
 `pbMetadata`  
 de Búfer que contiene los metadatos Delta. La dirección del búfer se devuelve desde el método [IMetaDataEmit2:: SaveDeltaToMemory (](../metadata/imetadataemit2-savedeltatomemory-method.md) .  
  
 Las direcciones virtuales relativas (RVA) en los metadatos deben ser relativas al inicio del código MSIL.  
  
 `cbIL`  
 de Tamaño, en bytes, del código MSIL Delta.  
  
 `pbIL`  
 de Búfer que contiene el código MSIL actualizado.  
  
## <a name="remarks"></a>Comentarios  

 El `pbMetadata` parámetro está en un formato de metadatos Delta especial (como el resultado de [IMetaDataEmit2:: SaveDeltaToMemory (](../metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` toma los metadatos anteriores como base y describe los cambios individuales que se aplican a esa base.  
  
 Por el contrario, el `pbIL[` parámetro] contiene el nuevo MSIL para el método actualizado y está pensado para reemplazar por completo el MSIL anterior para ese método  
  
 Cuando el MSIL Delta y los metadatos se han creado en la memoria del depurador, el depurador llama `ApplyChanges` a para enviar los cambios en el Common Language Runtime (CLR). El motor en tiempo de ejecución actualiza sus tablas de metadatos, coloca el nuevo MSIL en el proceso y configura una compilación Just-in-Time (JIT) del nuevo MSIL. Cuando se hayan aplicado los cambios, el depurador debe llamar a [IMetaDataEmit2:: ResetENCLog (](../metadata/imetadataemit2-resetenclog-method.md) para prepararse para la siguiente sesión de edición. Después, el depurador puede continuar el proceso.  
  
 Cada vez que el depurador llama a `ApplyChanges` en un módulo que tiene metadatos Delta, también debe llamar a [IMetaDataEmit:: applyeditandcontinue (](../metadata/imetadataemit-applyeditandcontinue-method.md) con los mismos metadatos Delta en todas sus copias de los metadatos de ese módulo excepto en la copia utilizada para emitir los cambios. Si una copia de los metadatos no se sincroniza de algún modo con los metadatos reales, el depurador siempre puede abandonar esa copia y obtener una nueva copia.  
  
 Si se `ApplyChanges` produce un error en el método, la sesión de depuración se encuentra en un estado no válido y debe reiniciarse.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
