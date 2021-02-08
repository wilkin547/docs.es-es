---
description: 'Más información sobre: ICorPublishProcessEnum (:: Next (método)'
title: ICorPublishProcessEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 14b4f815aff986b23a22ed3d5736c37128d3d7e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790482"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="22561-103">ICorPublishProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="22561-103">ICorPublishProcessEnum::Next Method</span></span>

<span data-ttu-id="22561-104">Obtiene el número especificado de procesos de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="22561-104">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22561-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22561-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22561-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22561-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="22561-107">de El número de procesos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="22561-107">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="22561-108">enuncia Puntero a la matriz de objetos [ICorPublishProcess](icorpublishprocess-interface.md) recuperados, cada uno de los cuales representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="22561-108">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="22561-109">enuncia Puntero al número de procesos devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="22561-109">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="22561-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="22561-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22561-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22561-111">Requirements</span></span>  

 <span data-ttu-id="22561-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22561-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22561-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="22561-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="22561-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22561-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22561-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22561-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22561-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="22561-116">See also</span></span>

- [<span data-ttu-id="22561-117">ICorPublishProcessEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22561-117">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
