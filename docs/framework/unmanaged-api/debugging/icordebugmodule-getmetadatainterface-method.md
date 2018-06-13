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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fef23f2b128b1e5393c5104b6e33758882b34882
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420887"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="fe242-102">ICorDebugModule::GetMetaDataInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="fe242-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="fe242-103">Obtiene un objeto de interfaz de metadatos que puede usarse para examinar los metadatos para el módulo.</span><span class="sxs-lookup"><span data-stu-id="fe242-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe242-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe242-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe242-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe242-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="fe242-106">[in] El identificador de referencia que especifica la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fe242-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="fe242-107">[out] Un puntero a la dirección de un `T:IUnknown` objeto que es uno de los [interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="fe242-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe242-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe242-108">Remarks</span></span>  
 <span data-ttu-id="fe242-109">El depurador puede utilizar el `GetMetaDataInterface` método para realizar una copia de los metadatos originales para un módulo, lo que es necesario para editar ese módulo.</span><span class="sxs-lookup"><span data-stu-id="fe242-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="fe242-110">El depurador llama `GetMetaDataInterface` para obtener un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) objeto de interfaz para el módulo, a continuación, llama a [SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) para guardar una copia de los metadatos del módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="fe242-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe242-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe242-111">Requirements</span></span>  
 <span data-ttu-id="fe242-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe242-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe242-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe242-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe242-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe242-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe242-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe242-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe242-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe242-116">See Also</span></span>  
 [<span data-ttu-id="fe242-117">Metadatos</span><span class="sxs-lookup"><span data-stu-id="fe242-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
