---
title: ICorDebugModule::GetMetaDataInterface (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: 8f3cc16054d4b5340c9460e9c3fbcba6e563567a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212560"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="f0a84-102">ICorDebugModule::GetMetaDataInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="f0a84-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="f0a84-103">Obtiene un objeto de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="f0a84-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0a84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0a84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0a84-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="f0a84-106">de IDENTIFICADOR de referencia que especifica la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f0a84-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="f0a84-107">enuncia Puntero a la dirección de un `T:IUnknown` objeto que es una de las [interfaces de metadatos](../metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="f0a84-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0a84-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0a84-108">Remarks</span></span>  
 <span data-ttu-id="f0a84-109">El depurador puede utilizar el `GetMetaDataInterface` método para realizar una copia de los metadatos originales de un módulo, que debe hacer para editar ese módulo.</span><span class="sxs-lookup"><span data-stu-id="f0a84-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="f0a84-110">El depurador llama `GetMetaDataInterface` a para obtener un objeto de interfaz [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) para el módulo y, a continuación, llama a [IMetaDataEmit:: savetomemory (](../metadata/imetadataemit-savetomemory-method.md) para guardar una copia de los metadatos del módulo en la memoria.</span><span class="sxs-lookup"><span data-stu-id="f0a84-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a84-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0a84-111">Requirements</span></span>  
 <span data-ttu-id="f0a84-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0a84-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a84-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0a84-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0a84-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0a84-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0a84-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a84-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a84-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0a84-116">See also</span></span>

- [<span data-ttu-id="f0a84-117">Metadatos</span><span class="sxs-lookup"><span data-stu-id="f0a84-117">Metadata</span></span>](../metadata/index.md)
