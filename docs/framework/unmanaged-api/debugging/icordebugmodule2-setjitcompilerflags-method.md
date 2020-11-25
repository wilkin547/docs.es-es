---
title: ICorDebugModule2::GetJITCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: 11ff430c426c93f1c2a5c0582495e089a33995fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709809"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="4a12b-102">ICorDebugModule2::GetJITCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="4a12b-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>

<span data-ttu-id="4a12b-103">Establece las marcas que controlan la compilación Just-in-Time (JIT) de este ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="4a12b-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a12b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a12b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a12b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a12b-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="4a12b-106">de Combinación bit a bit de los valores de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4a12b-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a12b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a12b-107">Remarks</span></span>  

 <span data-ttu-id="4a12b-108">Si el `dwFlags` valor no es válido, `SetJITCompilerFlags` se producirá un error en el método.</span><span class="sxs-lookup"><span data-stu-id="4a12b-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="4a12b-109">`SetJITCompilerFlags`Solo se puede llamar al método desde dentro de la devolución de llamada [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) para este módulo.</span><span class="sxs-lookup"><span data-stu-id="4a12b-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="4a12b-110">Se producirá un error al intentar llamarlo después de que se haya `ICorDebugManagedCallback::LoadModule` entregado la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4a12b-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="4a12b-111">No se admite editar y continuar en plataformas de 64 bits o Win9x.</span><span class="sxs-lookup"><span data-stu-id="4a12b-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="4a12b-112">Por consiguiente, si se llama al `SetJITCompilerFlags` método en cualquiera de estas dos plataformas con la marca CORDEBUG_JIT_ENABLE_ENC establecida en `dwFlags` , el `SetJITCompilerFlags` método y todos los métodos específicos para editar y continuar, como [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), producirán un error.</span><span class="sxs-lookup"><span data-stu-id="4a12b-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a12b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a12b-113">Requirements</span></span>  

 <span data-ttu-id="4a12b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a12b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a12b-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a12b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a12b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a12b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a12b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a12b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
