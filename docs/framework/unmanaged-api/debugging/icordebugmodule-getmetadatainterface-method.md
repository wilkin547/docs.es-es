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
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129543"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="df660-102">ICorDebugModule::GetMetaDataInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="df660-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="df660-103">Obtiene un objeto de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="df660-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df660-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df660-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df660-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df660-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="df660-106">de IDENTIFICADOR de referencia que especifica la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="df660-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="df660-107">enuncia Puntero a la dirección de un objeto `T:IUnknown` que es una de las [interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="df660-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df660-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df660-108">Remarks</span></span>  
 <span data-ttu-id="df660-109">El depurador puede utilizar el método `GetMetaDataInterface` para realizar una copia de los metadatos originales de un módulo, que debe hacer para poder editar ese módulo.</span><span class="sxs-lookup"><span data-stu-id="df660-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="df660-110">El depurador llama a `GetMetaDataInterface` para obtener un objeto de interfaz [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) para el módulo y, a continuación, llama a [IMetaDataEmit:: savetomemory (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) para guardar una copia de los metadatos del módulo en la memoria.</span><span class="sxs-lookup"><span data-stu-id="df660-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df660-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df660-111">Requirements</span></span>  
 <span data-ttu-id="df660-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df660-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df660-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df660-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df660-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df660-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df660-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df660-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df660-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="df660-116">See also</span></span>

- [<span data-ttu-id="df660-117">Metadatos</span><span class="sxs-lookup"><span data-stu-id="df660-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
