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
ms.openlocfilehash: 37710fbb7acc50b80d7acebe4194b019c0b64660
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994856"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="9a9c2-102">ICorDebugModule::GetMetaDataInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="9a9c2-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="9a9c2-103">Obtiene un objeto de interfaz de metadatos que puede usarse para examinar los metadatos para el módulo.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a9c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a9c2-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a9c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a9c2-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="9a9c2-106">[in] El identificador de referencia que especifica la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="9a9c2-107">[out] Un puntero a la dirección de un `T:IUnknown` objeto que es uno de los [interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c2-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a9c2-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a9c2-108">Remarks</span></span>  
 <span data-ttu-id="9a9c2-109">Puede usar el depurador el `GetMetaDataInterface` método para realizar una copia de los metadatos originales para un módulo, lo que es necesario para poder editar ese módulo.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="9a9c2-110">El depurador llama `GetMetaDataInterface` para obtener un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) objeto de interfaz del módulo, a continuación, llama a [SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) para guardar una copia de los metadatos del módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="9a9c2-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a9c2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a9c2-111">Requirements</span></span>  
 <span data-ttu-id="9a9c2-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a9c2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a9c2-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a9c2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a9c2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a9c2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a9c2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a9c2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9c2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a9c2-116">See also</span></span>

- [<span data-ttu-id="9a9c2-117">Metadatos</span><span class="sxs-lookup"><span data-stu-id="9a9c2-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
