---
title: "ICorDebugModule2::ApplyChanges (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4855b7a42d471304d000465a0437f29bdff05494
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="6d99f-102">ICorDebugModule2::ApplyChanges (Método)</span><span class="sxs-lookup"><span data-stu-id="6d99f-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="6d99f-103">Aplica los cambios en los metadatos y los cambios en el código de lenguaje intermedio (MSIL) de Microsoft a los procesos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d99f-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d99f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d99f-104">Syntax</span></span>  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d99f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d99f-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="6d99f-106">[in] Tamaño, en bytes, de los metadatos de delta.</span><span class="sxs-lookup"><span data-stu-id="6d99f-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="6d99f-107">[in] Búfer que contiene los metadatos delta.</span><span class="sxs-lookup"><span data-stu-id="6d99f-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="6d99f-108">La dirección del búfer se devuelve desde el [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6d99f-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="6d99f-109">Las direcciones virtuales relativas (RVA) en los metadatos deben ser relativas al inicio del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="6d99f-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="6d99f-110">[in] Tamaño, en bytes, del código delta de MSIL.</span><span class="sxs-lookup"><span data-stu-id="6d99f-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="6d99f-111">[in] Búfer que contiene el código MSIL actualizado.</span><span class="sxs-lookup"><span data-stu-id="6d99f-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d99f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d99f-112">Remarks</span></span>  
 <span data-ttu-id="6d99f-113">El `pbMetadata` parámetro tiene un formato de metadatos delta especial (como salida por [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="6d99f-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="6d99f-114">`pbMetadata`toma los metadatos anteriores como base y describe los cambios individuales que se aplican a esa base.</span><span class="sxs-lookup"><span data-stu-id="6d99f-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="6d99f-115">En cambio, la `pbIL[`] parámetro contiene el nuevo MSIL para el método actualizado y está destinada a reemplazar completamente el MSIL del método anterior</span><span class="sxs-lookup"><span data-stu-id="6d99f-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="6d99f-116">Cuando la diferencia de MSIL y los metadatos se han creado en la memoria del depurador, el depurador llama `ApplyChanges` para enviar los cambios en common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6d99f-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="6d99f-117">El tiempo de ejecución actualiza las tablas de metadatos, coloca el nuevo MSIL en el proceso y configura una compilación de just-in-time (JIT) del nuevo MSIL.</span><span class="sxs-lookup"><span data-stu-id="6d99f-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="6d99f-118">Si se han aplicado los cambios, el depurador debe llamar a [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) para prepararse para la siguiente sesión de edición.</span><span class="sxs-lookup"><span data-stu-id="6d99f-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="6d99f-119">El depurador, a continuación, puede continuar con el proceso.</span><span class="sxs-lookup"><span data-stu-id="6d99f-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="6d99f-120">Cada vez que el depurador llama `ApplyChanges` en un módulo que contiene los metadatos de delta, también debe llamar [ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) con los mismos metadatos delta en todas las copias de los metadatos de ese módulo excepto la copia usado para emitir los cambios.</span><span class="sxs-lookup"><span data-stu-id="6d99f-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="6d99f-121">Si una copia de los metadatos se convierte en algún modo fuera de sincronización con los metadatos reales, el depurador siempre puede deshacerse de esa copia y obtenga una nueva copia.</span><span class="sxs-lookup"><span data-stu-id="6d99f-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="6d99f-122">Si el `ApplyChanges` método produce un error, la depuración sesión está en un estado no válido y debe reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="6d99f-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d99f-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d99f-123">Requirements</span></span>  
 <span data-ttu-id="6d99f-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d99f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d99f-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d99f-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d99f-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d99f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d99f-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d99f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
