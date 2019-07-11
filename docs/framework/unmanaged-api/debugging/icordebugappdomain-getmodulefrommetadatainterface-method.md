---
title: ICorDebugAppDomain::GetModuleFromMetaDataInterface (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48249bb634c301b7fda2c360c3b793e9206a759a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737904"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="19e6a-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="19e6a-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="19e6a-103">Obtiene el módulo que se corresponde con la interfaz de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="19e6a-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19e6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19e6a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19e6a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19e6a-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="19e6a-106">[in] Un puntero a un objeto que es uno de los [interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="19e6a-106">[in] A pointer to an object that is one of the [Metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="19e6a-107">[out] Un puntero a la dirección de un objeto ICorDebugModule que representa el módulo correspondiente a la interfaz de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="19e6a-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19e6a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19e6a-108">Requirements</span></span>  
 <span data-ttu-id="19e6a-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19e6a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19e6a-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19e6a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19e6a-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19e6a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19e6a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19e6a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
