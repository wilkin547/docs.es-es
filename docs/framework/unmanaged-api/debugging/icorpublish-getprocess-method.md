---
description: 'Más información acerca de: ICorPublish:: GetProcess (método)'
title: ICorPublish::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: d288a772274618cc99b63a68b37e84e543957b44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721988"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="d101e-103">ICorPublish::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="d101e-103">ICorPublish::GetProcess Method</span></span>

<span data-ttu-id="d101e-104">Obtiene una instancia de [ICorPublishProcess](icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="d101e-104">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d101e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d101e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d101e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d101e-106">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="d101e-107">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="d101e-107">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="d101e-108">enuncia Puntero a la dirección de una `ICorPublishProcess` instancia de que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="d101e-108">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d101e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d101e-109">Remarks</span></span>  

 <span data-ttu-id="d101e-110">`GetProcess` se produce un error si el proceso no existe o no es un proceso administrado que el usuario actual puede depurar.</span><span class="sxs-lookup"><span data-stu-id="d101e-110">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d101e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d101e-111">Requirements</span></span>  

 <span data-ttu-id="d101e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d101e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d101e-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="d101e-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d101e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d101e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d101e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d101e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d101e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d101e-116">See also</span></span>

- [<span data-ttu-id="d101e-117">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d101e-117">ICorPublish Interface</span></span>](icorpublish-interface.md)
