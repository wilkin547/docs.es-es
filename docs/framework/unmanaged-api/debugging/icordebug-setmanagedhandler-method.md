---
description: 'Más información acerca de: ICorDebug:: SetManagedHandler ((método)'
title: ICorDebug::SetManagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 5817bd39a2c4e7c71dc12ca8d2d9b1263d116ac8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754360"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="28666-103">ICorDebug::SetManagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="28666-103">ICorDebug::SetManagedHandler Method</span></span>

<span data-ttu-id="28666-104">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="28666-104">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28666-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28666-105">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28666-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28666-106">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="28666-107">de Un puntero a un objeto [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , que es el objeto del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="28666-107">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28666-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="28666-108">Remarks</span></span>  

 <span data-ttu-id="28666-109">`SetManagedHandler` se debe llamar al método en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="28666-109">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="28666-110">Si la `ICorDebugManagedCallback` implementación no contiene interfaces suficientes para controlar los eventos de depuración de la aplicación que se está depurando, `SetManagedHandler` devuelve un valor HRESULT de E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="28666-110">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28666-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28666-111">Requirements</span></span>  

 <span data-ttu-id="28666-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28666-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28666-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28666-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28666-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28666-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28666-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28666-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28666-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="28666-116">See also</span></span>

- [<span data-ttu-id="28666-117">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28666-117">ICorDebug Interface</span></span>](icordebug-interface.md)
