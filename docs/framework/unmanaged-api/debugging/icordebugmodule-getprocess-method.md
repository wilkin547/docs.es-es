---
description: 'Más información acerca de: ICorDebugModule:: GetProcess (método)'
title: ICorDebugModule::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
ms.openlocfilehash: eb8497ac8ec6913fe079d6f5f148d3769bf6633a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691632"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="7a438-103">ICorDebugModule::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="7a438-103">ICorDebugModule::GetProcess Method</span></span>

<span data-ttu-id="7a438-104">Obtiene el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="7a438-104">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a438-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a438-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a438-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a438-106">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="7a438-107">enuncia Puntero a la dirección de un objeto ICorDebugProcess que representa el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="7a438-107">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a438-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a438-108">Requirements</span></span>  

 <span data-ttu-id="7a438-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a438-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a438-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a438-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a438-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a438-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a438-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a438-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
