---
description: 'Más información acerca de: ICorDebugAppDomain:: Isattached ((método)'
title: ICorDebugAppDomain::IsAttached (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 79427d08be9ffea253695b67767d68589edf6979
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772391"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="fdeaa-103">ICorDebugAppDomain::IsAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="fdeaa-103">ICorDebugAppDomain::IsAttached Method</span></span>

<span data-ttu-id="fdeaa-104">Obtiene un valor que indica si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fdeaa-104">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdeaa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdeaa-105">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdeaa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdeaa-106">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="fdeaa-107">[out] `true` Si el depurador está asociado al dominio de aplicación; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="fdeaa-107">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdeaa-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fdeaa-108">Remarks</span></span>  

 <span data-ttu-id="fdeaa-109">Los métodos ICorDebugController no se pueden usar hasta que el depurador se asocie al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fdeaa-109">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdeaa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdeaa-110">Requirements</span></span>  

 <span data-ttu-id="fdeaa-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdeaa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdeaa-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdeaa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdeaa-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdeaa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdeaa-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdeaa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
