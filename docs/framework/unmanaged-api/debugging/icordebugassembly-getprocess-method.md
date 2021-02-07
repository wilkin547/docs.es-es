---
description: 'Más información acerca de: ICorDebugAssembly:: GetProcess (método)'
title: ICorDebugAssembly::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
ms.openlocfilehash: b121d7f892f6e2e2aa76290d4aee51767c72e9fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754156"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="26daf-103">ICorDebugAssembly::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="26daf-103">ICorDebugAssembly::GetProcess Method</span></span>

<span data-ttu-id="26daf-104">Obtiene un puntero de interfaz al proceso en el que se está ejecutando esta instancia de ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="26daf-104">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26daf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26daf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26daf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26daf-106">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="26daf-107">enuncia Puntero a una interfaz ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="26daf-107">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26daf-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26daf-108">Requirements</span></span>  

 <span data-ttu-id="26daf-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26daf-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26daf-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26daf-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26daf-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26daf-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26daf-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26daf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
