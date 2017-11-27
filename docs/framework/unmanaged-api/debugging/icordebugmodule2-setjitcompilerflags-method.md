---
title: "ICorDebugModule2::GetJITCompilerFlags (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42eea356214fedb22a2f60842f6007f3eb6a0e2a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="08fd8-102">ICorDebugModule2::GetJITCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="08fd8-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="08fd8-103">Establece las marcas que controlan la compilación just-in-time (JIT) de este ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="08fd8-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08fd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08fd8-104">Syntax</span></span>  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08fd8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08fd8-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="08fd8-106">[in] Una combinación bit a bit de los [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="08fd8-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08fd8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08fd8-107">Remarks</span></span>  
 <span data-ttu-id="08fd8-108">Si el `dwFlags` valor no es válido, el `SetJITCompilerFlags` método generará un error.</span><span class="sxs-lookup"><span data-stu-id="08fd8-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="08fd8-109">El `SetJITCompilerFlags` método puede llamarse solo desde el [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) devolución de llamada de este módulo.</span><span class="sxs-lookup"><span data-stu-id="08fd8-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="08fd8-110">Intenta llamar después a la `ICorDebugManagedCallback::LoadModule` devolución de llamada se ha entregado will producirá un error.</span><span class="sxs-lookup"><span data-stu-id="08fd8-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="08fd8-111">Editar y continuar no se admite en plataformas Win9x o de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="08fd8-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="08fd8-112">Por lo tanto, si se llama a la `SetJITCompilerFlags` método cualquiera de estas dos plataformas con el marcador CORDEBUG_JIT_ENABLE_ENC está establecido `dwFlags`, `SetJITCompilerFlags` método y todos los métodos específicos para editar y continuar, como [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="08fd8-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08fd8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08fd8-113">Requirements</span></span>  
 <span data-ttu-id="08fd8-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08fd8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08fd8-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08fd8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08fd8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08fd8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08fd8-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08fd8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
