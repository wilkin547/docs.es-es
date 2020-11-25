---
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
ms.openlocfilehash: 8f4b9e73e0d716561dd64bc0df702d835e0eee06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709965"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="e5bff-102">ICorDebugModule::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="e5bff-102">ICorDebugModule::GetProcess Method</span></span>

<span data-ttu-id="e5bff-103">Obtiene el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="e5bff-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5bff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5bff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5bff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5bff-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="e5bff-106">enuncia Puntero a la dirección de un objeto ICorDebugProcess que representa el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="e5bff-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5bff-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5bff-107">Requirements</span></span>  

 <span data-ttu-id="e5bff-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5bff-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5bff-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5bff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5bff-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5bff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5bff-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5bff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
