---
title: ICorDebugThread::GetActiveChain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: 70e79378ad8eb2599199a1f7bc57cf530c9b4dd3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379695"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="05fe1-102">ICorDebugThread::GetActiveChain (Método)</span><span class="sxs-lookup"><span data-stu-id="05fe1-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="05fe1-103">Obtiene un puntero de interfaz a la cadena de pila activa (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="05fe1-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05fe1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05fe1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05fe1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05fe1-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="05fe1-106">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena de pila.</span><span class="sxs-lookup"><span data-stu-id="05fe1-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05fe1-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="05fe1-107">Remarks</span></span>  
 <span data-ttu-id="05fe1-108">El `ppChain` parámetro es NULL si no hay ninguna cadena de pila activa actualmente.</span><span class="sxs-lookup"><span data-stu-id="05fe1-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05fe1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05fe1-109">Requirements</span></span>  
 <span data-ttu-id="05fe1-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05fe1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05fe1-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05fe1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05fe1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05fe1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05fe1-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05fe1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
