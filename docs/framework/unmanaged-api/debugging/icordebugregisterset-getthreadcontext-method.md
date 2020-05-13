---
title: ICorDebugRegisterSet::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: 04ae3c4dd663351eaf1a58646e24e8ae95aeb9ad
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378279"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="b1761-102">ICorDebugRegisterSet::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="b1761-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="b1761-103">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="b1761-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1761-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1761-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1761-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1761-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="b1761-106">de Tamaño, en bytes, de la `context` matriz.</span><span class="sxs-lookup"><span data-stu-id="b1761-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="b1761-107">[in, out] Matriz de bytes que componen la `CONTEXT` estructura de Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="b1761-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1761-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b1761-108">Remarks</span></span>  
 <span data-ttu-id="b1761-109">El depurador debe llamar a esta función en lugar de a la función de Win32 `GetThreadContext` , ya que el subproceso puede estar en un estado "secuestrado" donde su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="b1761-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="b1761-110">Los datos devueltos son una `CONTEXT` estructura Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="b1761-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="b1761-111">En el caso de los marcos no hoja, los clientes deben comprobar qué registros son válidos mediante [ICorDebugRegisterSet:: getregistersavailable (](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="b1761-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1761-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1761-112">Requirements</span></span>  
 <span data-ttu-id="b1761-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1761-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1761-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1761-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1761-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1761-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1761-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1761-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1761-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1761-117">See also</span></span>

- [<span data-ttu-id="b1761-118">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1761-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="b1761-119">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1761-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
