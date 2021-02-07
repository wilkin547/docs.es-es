---
description: 'Más información acerca de: ICorDebugModule:: Getassembly ((método)'
title: ICorDebugModule::GetAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
ms.openlocfilehash: 88bda923cd4c3ebfa5da6b3343e1cead4cebbad9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722624"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="c042f-103">ICorDebugModule::GetAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="c042f-103">ICorDebugModule::GetAssembly Method</span></span>

<span data-ttu-id="c042f-104">Obtiene el ensamblado contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="c042f-104">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c042f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c042f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c042f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c042f-106">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="c042f-107">enuncia Un puntero a un objeto ICorDebugAssembly que representa el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="c042f-107">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c042f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c042f-108">Requirements</span></span>  

 <span data-ttu-id="c042f-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c042f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c042f-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c042f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c042f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c042f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c042f-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c042f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
