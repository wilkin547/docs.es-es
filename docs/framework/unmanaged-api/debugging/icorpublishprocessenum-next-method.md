---
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
ms.openlocfilehash: 084af87acd73ef65739ba69ef2bd66d10d7c27c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790512"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="8199c-102">ICorPublishProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="8199c-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="8199c-103">Obtiene el número especificado de procesos de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="8199c-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8199c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8199c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8199c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8199c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8199c-106">de El número de procesos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="8199c-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="8199c-107">enuncia Puntero a la matriz de objetos [ICorPublishProcess](icorpublishprocess-interface.md) recuperados, cada uno de los cuales representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="8199c-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8199c-108">enuncia Puntero al número de procesos devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="8199c-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="8199c-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="8199c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8199c-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8199c-110">Requirements</span></span>  
 <span data-ttu-id="8199c-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8199c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8199c-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="8199c-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8199c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8199c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8199c-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8199c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8199c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8199c-115">See also</span></span>

- [<span data-ttu-id="8199c-116">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8199c-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
