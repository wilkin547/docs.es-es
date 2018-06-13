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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: add7239feb1cf6dab0fabe12e178336921211190
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414211"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="da91c-102">ICorDebugModule::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="da91c-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="da91c-103">Obtiene el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="da91c-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da91c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da91c-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da91c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da91c-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="da91c-106">[out] Un puntero a la dirección de un objeto ICorDebugProcess que representa el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="da91c-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da91c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da91c-107">Requirements</span></span>  
 <span data-ttu-id="da91c-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da91c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da91c-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da91c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da91c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da91c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da91c-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da91c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
