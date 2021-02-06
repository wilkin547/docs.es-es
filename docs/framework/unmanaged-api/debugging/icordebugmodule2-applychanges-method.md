---
description: 'Más información acerca de: ICorDebugModule2:: ApplyChanges (método)'
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
ms.openlocfilehash: 09cbc395c8d656d1dc27de86305432b26308c885
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660081"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="0136f-103">ICorDebugModule2::ApplyChanges (Método)</span><span class="sxs-lookup"><span data-stu-id="0136f-103">ICorDebugModule2::ApplyChanges Method</span></span>

<span data-ttu-id="0136f-104">Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0136f-104">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0136f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0136f-105">Syntax</span></span>  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0136f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0136f-106">Parameters</span></span>  

 `cbMetadata`  
 <span data-ttu-id="0136f-107">de Tamaño, en bytes, de los metadatos Delta.</span><span class="sxs-lookup"><span data-stu-id="0136f-107">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="0136f-108">de Búfer que contiene los metadatos Delta.</span><span class="sxs-lookup"><span data-stu-id="0136f-108">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="0136f-109">La dirección del búfer se devuelve desde el método [IMetaDataEmit2:: SaveDeltaToMemory (](../metadata/imetadataemit2-savedeltatomemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0136f-109">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="0136f-110">Las direcciones virtuales relativas (RVA) en los metadatos deben ser relativas al inicio del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="0136f-110">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="0136f-111">de Tamaño, en bytes, del código MSIL Delta.</span><span class="sxs-lookup"><span data-stu-id="0136f-111">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="0136f-112">de Búfer que contiene el código MSIL actualizado.</span><span class="sxs-lookup"><span data-stu-id="0136f-112">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0136f-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0136f-113">Remarks</span></span>  

 <span data-ttu-id="0136f-114">El `pbMetadata` parámetro está en un formato de metadatos Delta especial (como el resultado de [IMetaDataEmit2:: SaveDeltaToMemory (](../metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="0136f-114">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="0136f-115">`pbMetadata` toma los metadatos anteriores como base y describe los cambios individuales que se aplican a esa base.</span><span class="sxs-lookup"><span data-stu-id="0136f-115">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="0136f-116">Por el contrario, el `pbIL[` parámetro] contiene el nuevo MSIL para el método actualizado y está pensado para reemplazar por completo el MSIL anterior para ese método</span><span class="sxs-lookup"><span data-stu-id="0136f-116">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="0136f-117">Cuando el MSIL Delta y los metadatos se han creado en la memoria del depurador, el depurador llama `ApplyChanges` a para enviar los cambios en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0136f-117">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="0136f-118">El motor en tiempo de ejecución actualiza sus tablas de metadatos, coloca el nuevo MSIL en el proceso y configura una compilación Just-in-Time (JIT) del nuevo MSIL.</span><span class="sxs-lookup"><span data-stu-id="0136f-118">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="0136f-119">Cuando se hayan aplicado los cambios, el depurador debe llamar a [IMetaDataEmit2:: ResetENCLog (](../metadata/imetadataemit2-resetenclog-method.md) para prepararse para la siguiente sesión de edición.</span><span class="sxs-lookup"><span data-stu-id="0136f-119">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="0136f-120">Después, el depurador puede continuar el proceso.</span><span class="sxs-lookup"><span data-stu-id="0136f-120">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="0136f-121">Cada vez que el depurador llama a `ApplyChanges` en un módulo que tiene metadatos Delta, también debe llamar a [IMetaDataEmit:: applyeditandcontinue (](../metadata/imetadataemit-applyeditandcontinue-method.md) con los mismos metadatos Delta en todas sus copias de los metadatos de ese módulo excepto en la copia utilizada para emitir los cambios.</span><span class="sxs-lookup"><span data-stu-id="0136f-121">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="0136f-122">Si una copia de los metadatos no se sincroniza de algún modo con los metadatos reales, el depurador siempre puede abandonar esa copia y obtener una nueva copia.</span><span class="sxs-lookup"><span data-stu-id="0136f-122">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="0136f-123">Si se `ApplyChanges` produce un error en el método, la sesión de depuración se encuentra en un estado no válido y debe reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="0136f-123">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0136f-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0136f-124">Requirements</span></span>  

 <span data-ttu-id="0136f-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0136f-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0136f-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0136f-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0136f-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0136f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0136f-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0136f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
