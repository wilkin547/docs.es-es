---
title: ICorDebugThread::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad2dd4cded6800ce016d821f8e3ffe01dcb6264b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418264"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="88aaf-102">ICorDebugThread::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="88aaf-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="88aaf-103">Obtiene un puntero de interfaz para el subproceso de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="88aaf-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88aaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88aaf-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88aaf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88aaf-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="88aaf-106">[out] Un puntero a la dirección de un objeto de interfaz de ICorDebugValue que representa el subproceso de CLR.</span><span class="sxs-lookup"><span data-stu-id="88aaf-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88aaf-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88aaf-107">Requirements</span></span>  
 <span data-ttu-id="88aaf-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88aaf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88aaf-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88aaf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88aaf-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88aaf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88aaf-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88aaf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88aaf-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="88aaf-112">See Also</span></span>  
 <xref:System.Threading.Thread>
