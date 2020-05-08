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
ms.openlocfilehash: f317eb1b3d91fc005d59d6a06bad329a5f68aa11
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895225"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="95f50-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="95f50-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="95f50-103">Obtiene el módulo que corresponde a la interfaz de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="95f50-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95f50-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95f50-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95f50-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="95f50-106">de Un puntero a un objeto que es una de las [interfaces de metadatos](../metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="95f50-106">[in] A pointer to an object that is one of the [Metadata interfaces](../metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="95f50-107">enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo correspondiente a la interfaz de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="95f50-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f50-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95f50-108">Requirements</span></span>  
 <span data-ttu-id="95f50-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95f50-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f50-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95f50-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95f50-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95f50-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95f50-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f50-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
