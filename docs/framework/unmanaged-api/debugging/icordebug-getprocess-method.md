---
description: 'Más información acerca de: ICorDebug:: GetProcess (método)'
title: ICorDebug::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
ms.openlocfilehash: a24bb0ec645a337b1202b954c165a76bcf8fad9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801311"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="cf2b0-103">ICorDebug::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="cf2b0-103">ICorDebug::GetProcess Method</span></span>

<span data-ttu-id="cf2b0-104">Obtiene un puntero a la instancia de "ICorDebugProcess" para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="cf2b0-104">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf2b0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf2b0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf2b0-106">Parameters</span></span>  

 `dwProcessId`  
 <span data-ttu-id="cf2b0-107">de IDENTIFICADOR del proceso.</span><span class="sxs-lookup"><span data-stu-id="cf2b0-107">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="cf2b0-108">enuncia Puntero a la dirección de una `ICorDebugProcess` instancia para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="cf2b0-108">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf2b0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf2b0-109">Requirements</span></span>  

 <span data-ttu-id="cf2b0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf2b0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf2b0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf2b0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf2b0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf2b0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf2b0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf2b0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2b0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf2b0-114">See also</span></span>

- [<span data-ttu-id="cf2b0-115">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf2b0-115">ICorDebug Interface</span></span>](icordebug-interface.md)
