---
title: ICorDebugProcess3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ccc45482f691d9950c641ef126a657052a280e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213643"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="0ad13-102">ICorDebugProcess3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ad13-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="0ad13-103">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0ad13-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ad13-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0ad13-104">Methods</span></span>  
  
|<span data-ttu-id="0ad13-105">Método</span><span class="sxs-lookup"><span data-stu-id="0ad13-105">Method</span></span>|<span data-ttu-id="0ad13-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad13-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ad13-107">Método SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="0ad13-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="0ad13-108">Habilita y deshabilita las notificaciones del depurador personalizados del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="0ad13-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ad13-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ad13-109">Remarks</span></span>  
 <span data-ttu-id="0ad13-110">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess y ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="0ad13-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ad13-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="0ad13-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad13-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ad13-112">Requirements</span></span>  
 <span data-ttu-id="0ad13-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad13-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad13-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ad13-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ad13-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad13-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0ad13-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0ad13-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ad13-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ad13-117">See also</span></span>

- [<span data-ttu-id="0ad13-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0ad13-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0ad13-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="0ad13-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
