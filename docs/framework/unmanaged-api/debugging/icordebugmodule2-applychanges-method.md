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
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="b075f-102">ICorDebugModule2::ApplyChanges (Método)</span><span class="sxs-lookup"><span data-stu-id="b075f-102">ICorDebugModule2::ApplyChanges Method</span></span>

<span data-ttu-id="b075f-103">Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b075f-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b075f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b075f-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b075f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b075f-105">Parameters</span></span>  

 `cbMetadata`  
 <span data-ttu-id="b075f-106">de Tamaño, en bytes, de los metadatos Delta.</span><span class="sxs-lookup"><span data-stu-id="b075f-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="b075f-107">de Búfer que contiene los metadatos Delta.</span><span class="sxs-lookup"><span data-stu-id="b075f-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="b075f-108">La dirección del búfer se devuelve desde el método [IMetaDataEmit2:: SaveDeltaToMemory (](../metadata/imetadataemit2-savedeltatomemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b075f-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="b075f-109">Las direcciones virtuales relativas (RVA) en los metadatos deben ser relativas al inicio del código MSIL.</span><span class="sxs-lookup"><span data-stu-id="b075f-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="b075f-110">de Tamaño, en bytes, del código MSIL Delta.</span><span class="sxs-lookup"><span data-stu-id="b075f-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="b075f-111">de Búfer que contiene el código MSIL actualizado.</span><span class="sxs-lookup"><span data-stu-id="b075f-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b075f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b075f-112">Remarks</span></span>  

 <span data-ttu-id="b075f-113">El `pbMetadata` parámetro está en un formato de metadatos Delta especial (como el resultado de [IMetaDataEmit2:: SaveDeltaToMemory (](../metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="b075f-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="b075f-114">`pbMetadata` toma los metadatos anteriores como base y describe los cambios individuales que se aplican a esa base.</span><span class="sxs-lookup"><span data-stu-id="b075f-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="b075f-115">Por el contrario, el `pbIL[` parámetro] contiene el nuevo MSIL para el método actualizado y está pensado para reemplazar por completo el MSIL anterior para ese método</span><span class="sxs-lookup"><span data-stu-id="b075f-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="b075f-116">Cuando el MSIL Delta y los metadatos se han creado en la memoria del depurador, el depurador llama `ApplyChanges` a para enviar los cambios en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b075f-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="b075f-117">El motor en tiempo de ejecución actualiza sus tablas de metadatos, coloca el nuevo MSIL en el proceso y configura una compilación Just-in-Time (JIT) del nuevo MSIL.</span><span class="sxs-lookup"><span data-stu-id="b075f-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="b075f-118">Cuando se hayan aplicado los cambios, el depurador debe llamar a [IMetaDataEmit2:: ResetENCLog (](../metadata/imetadataemit2-resetenclog-method.md) para prepararse para la siguiente sesión de edición.</span><span class="sxs-lookup"><span data-stu-id="b075f-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="b075f-119">Después, el depurador puede continuar el proceso.</span><span class="sxs-lookup"><span data-stu-id="b075f-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="b075f-120">Cada vez que el depurador llama a `ApplyChanges` en un módulo que tiene metadatos Delta, también debe llamar a [IMetaDataEmit:: applyeditandcontinue (](../metadata/imetadataemit-applyeditandcontinue-method.md) con los mismos metadatos Delta en todas sus copias de los metadatos de ese módulo excepto en la copia utilizada para emitir los cambios.</span><span class="sxs-lookup"><span data-stu-id="b075f-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="b075f-121">Si una copia de los metadatos no se sincroniza de algún modo con los metadatos reales, el depurador siempre puede abandonar esa copia y obtener una nueva copia.</span><span class="sxs-lookup"><span data-stu-id="b075f-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="b075f-122">Si se `ApplyChanges` produce un error en el método, la sesión de depuración se encuentra en un estado no válido y debe reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="b075f-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b075f-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b075f-123">Requirements</span></span>  

 <span data-ttu-id="b075f-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b075f-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b075f-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b075f-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b075f-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b075f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b075f-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b075f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
