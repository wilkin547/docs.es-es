---
description: 'Más información sobre: ICorDebugModule2:: Setjitcompilerflags ((método)'
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
ms.openlocfilehash: 72139c2fefc0eab7e76e38d07558e4386b47bc34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801077"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="c4ced-103">ICorDebugModule2::GetJITCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="c4ced-103">ICorDebugModule2::SetJITCompilerFlags Method</span></span>

<span data-ttu-id="c4ced-104">Establece las marcas que controlan la compilación Just-in-Time (JIT) de este ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="c4ced-104">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4ced-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4ced-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4ced-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4ced-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="c4ced-107">de Combinación bit a bit de los valores de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="c4ced-107">[in] A bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4ced-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4ced-108">Remarks</span></span>  

 <span data-ttu-id="c4ced-109">Si el `dwFlags` valor no es válido, `SetJITCompilerFlags` se producirá un error en el método.</span><span class="sxs-lookup"><span data-stu-id="c4ced-109">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="c4ced-110">`SetJITCompilerFlags`Solo se puede llamar al método desde dentro de la devolución de llamada [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) para este módulo.</span><span class="sxs-lookup"><span data-stu-id="c4ced-110">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="c4ced-111">Se producirá un error al intentar llamarlo después de que se haya `ICorDebugManagedCallback::LoadModule` entregado la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="c4ced-111">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="c4ced-112">No se admite editar y continuar en plataformas de 64 bits o Win9x.</span><span class="sxs-lookup"><span data-stu-id="c4ced-112">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="c4ced-113">Por consiguiente, si se llama al `SetJITCompilerFlags` método en cualquiera de estas dos plataformas con la marca CORDEBUG_JIT_ENABLE_ENC establecida en `dwFlags` , el `SetJITCompilerFlags` método y todos los métodos específicos para editar y continuar, como [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), producirán un error.</span><span class="sxs-lookup"><span data-stu-id="c4ced-113">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4ced-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4ced-114">Requirements</span></span>  

 <span data-ttu-id="c4ced-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4ced-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4ced-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4ced-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4ced-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4ced-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4ced-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4ced-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
