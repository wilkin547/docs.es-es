---
description: 'Más información acerca de: ICorDebug::D método ebugActiveProcess'
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
ms.openlocfilehash: 9c3a212adf962f96fd2c7345fe8b580b6af3b544
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801324"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="008b7-103">ICorDebug::DebugActiveProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="008b7-103">ICorDebug::DebugActiveProcess Method</span></span>

<span data-ttu-id="008b7-104">Asocia el depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="008b7-104">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="008b7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="008b7-105">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="008b7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="008b7-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="008b7-107">de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="008b7-107">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="008b7-108">de Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="008b7-108">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="008b7-109">enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="008b7-109">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="008b7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="008b7-110">Remarks</span></span>  

 <span data-ttu-id="008b7-111">No se admite la depuración de interoperabilidad en las plataformas Win9x y no x86, como las plataformas basadas en IA-64 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="008b7-111">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="008b7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="008b7-112">Requirements</span></span>  

 <span data-ttu-id="008b7-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="008b7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="008b7-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="008b7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="008b7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="008b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="008b7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="008b7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="008b7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="008b7-117">See also</span></span>

- [<span data-ttu-id="008b7-118">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="008b7-118">ICorDebug Interface</span></span>](icordebug-interface.md)
