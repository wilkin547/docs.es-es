---
title: ICorDebug::DebugActiveProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 3630e25b6c24edaa366f1b0fae088e760e851fa4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895406"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="5ab87-102">ICorDebug::DebugActiveProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="5ab87-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="5ab87-103">Asocia el depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="5ab87-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ab87-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ab87-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="5ab87-106">de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="5ab87-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="5ab87-107">de Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="5ab87-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="5ab87-108">enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="5ab87-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ab87-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5ab87-109">Remarks</span></span>  
 <span data-ttu-id="5ab87-110">No se admite la depuración de interoperabilidad en las plataformas Win9x y no x86, como las plataformas basadas en IA-64 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="5ab87-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab87-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ab87-111">Requirements</span></span>  
 <span data-ttu-id="5ab87-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ab87-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab87-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ab87-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ab87-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ab87-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ab87-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab87-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab87-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="5ab87-116">See also</span></span>

- [<span data-ttu-id="5ab87-117">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ab87-117">ICorDebug Interface</span></span>](icordebug-interface.md)
