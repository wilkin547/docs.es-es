---
title: Interfaz ICorDebugILFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
ms.openlocfilehash: c5fa0a67309e23c02393b70d849af3884dfd0adf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788538"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="4492a-102">Interfaz ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="4492a-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="4492a-103">Extensión lógica de la interfaz ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="4492a-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4492a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4492a-104">Methods</span></span>  
  
|<span data-ttu-id="4492a-105">Método</span><span class="sxs-lookup"><span data-stu-id="4492a-105">Method</span></span>|<span data-ttu-id="4492a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4492a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4492a-107">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="4492a-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="4492a-108">Obtiene un objeto ICorDebugTypeEnum que contiene los parámetros de <xref:System.Type> de este marco.</span><span class="sxs-lookup"><span data-stu-id="4492a-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="4492a-109">RemapFunction (método)</span><span class="sxs-lookup"><span data-stu-id="4492a-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="4492a-110">Vuelve a asignar una función editada especificando el nuevo desplazamiento de MSIL.</span><span class="sxs-lookup"><span data-stu-id="4492a-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4492a-111">Notas</span><span class="sxs-lookup"><span data-stu-id="4492a-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4492a-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4492a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4492a-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4492a-113">Requirements</span></span>  
 <span data-ttu-id="4492a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4492a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4492a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4492a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4492a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4492a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4492a-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4492a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4492a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4492a-118">See also</span></span>

- [<span data-ttu-id="4492a-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4492a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
