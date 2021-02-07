---
description: 'Más información sobre: ICorPublishProcess:: Getprocessid ((método)'
title: ICorPublishProcess::GetProcessID (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: f959a49330e0ef4ade2a878acfd287657b5086ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728826"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="f6bf1-103">ICorPublishProcess::GetProcessID (Método)</span><span class="sxs-lookup"><span data-stu-id="f6bf1-103">ICorPublishProcess::GetProcessID Method</span></span>

<span data-ttu-id="f6bf1-104">Obtiene el identificador del sistema operativo para este proceso.</span><span class="sxs-lookup"><span data-stu-id="f6bf1-104">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6bf1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6bf1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6bf1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6bf1-106">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="f6bf1-107">enuncia Puntero al identificador del proceso representado por este objeto [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f6bf1-107">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6bf1-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6bf1-108">Requirements</span></span>  

 <span data-ttu-id="f6bf1-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6bf1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6bf1-110">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f6bf1-110">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f6bf1-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6bf1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6bf1-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6bf1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6bf1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6bf1-113">See also</span></span>

- [<span data-ttu-id="f6bf1-114">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6bf1-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
