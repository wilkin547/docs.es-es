---
title: Interfaz ICorDebugAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 37b6bcb48681704e3db47f81a51a9d21f00dfb37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723199"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="1c610-102">Interfaz ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="1c610-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="1c610-103">Proporciona el `Next` método, que devuelve un número especificado de `ICorDebugAppDomainEnum` valores a partir de la siguiente ubicación de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="1c610-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="1c610-104">Esta interfaz es una subclase de "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="1c610-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c610-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c610-105">Methods</span></span>  
  
|<span data-ttu-id="1c610-106">Método</span><span class="sxs-lookup"><span data-stu-id="1c610-106">Method</span></span>|<span data-ttu-id="1c610-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c610-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c610-108">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="1c610-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="1c610-109">Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="1c610-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c610-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c610-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c610-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1c610-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c610-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c610-112">Requirements</span></span>  

 <span data-ttu-id="1c610-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c610-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c610-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c610-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c610-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c610-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c610-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c610-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c610-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c610-117">See also</span></span>

- [<span data-ttu-id="1c610-118">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c610-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="1c610-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1c610-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
