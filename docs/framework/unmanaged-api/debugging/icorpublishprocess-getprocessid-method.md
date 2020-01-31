---
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
ms.openlocfilehash: 4cc6bbde2c7367c1109ca73e66f2670a56b2cdbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790553"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="3c1fb-102">ICorPublishProcess::GetProcessID (Método)</span><span class="sxs-lookup"><span data-stu-id="3c1fb-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="3c1fb-103">Obtiene el identificador del sistema operativo para este proceso.</span><span class="sxs-lookup"><span data-stu-id="3c1fb-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c1fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c1fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c1fb-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3c1fb-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="3c1fb-106">enuncia Puntero al identificador del proceso representado por este objeto [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3c1fb-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c1fb-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3c1fb-107">Requirements</span></span>  
 <span data-ttu-id="3c1fb-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c1fb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c1fb-109">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="3c1fb-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3c1fb-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c1fb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c1fb-111">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c1fb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1fb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c1fb-112">See also</span></span>

- [<span data-ttu-id="3c1fb-113">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c1fb-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
