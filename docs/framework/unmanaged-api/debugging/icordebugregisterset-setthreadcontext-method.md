---
description: 'Más información acerca de: ICorDebugRegisterSet:: SetThreadContext (método)'
title: ICorDebugRegisterSet::SetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 8d874b1864e85e477260632ad6012dbbf10aefb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637695"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="7f389-103">ICorDebugRegisterSet::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="7f389-103">ICorDebugRegisterSet::SetThreadContext Method</span></span>

<span data-ttu-id="7f389-104">`SetThreadContext` no se implementa en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="7f389-104">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7f389-105">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="7f389-105">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f389-106">Use la operación de nivel superior [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md) para establecer el contexto de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="7f389-106">Use the higher-level operation [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f389-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f389-107">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7f389-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f389-108">Requirements</span></span>  

 <span data-ttu-id="7f389-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f389-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f389-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f389-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f389-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f389-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f389-112">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="7f389-112">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f389-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f389-113">See also</span></span>

- [<span data-ttu-id="7f389-114">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f389-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="7f389-115">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f389-115">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
