---
title: CreateCordbObject (Función)
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f546d7707c40f7f26a46177ae972a988e54e1e45
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487868"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="935e9-102">CreateCordbObject (Función)</span><span class="sxs-lookup"><span data-stu-id="935e9-102">CreateCordbObject Function</span></span>
<span data-ttu-id="935e9-103">Crea una interfaz de depurador ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) que proporciona la funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.</span><span class="sxs-lookup"><span data-stu-id="935e9-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="935e9-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="935e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="935e9-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="935e9-106">[in] Versión de depuración del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="935e9-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="935e9-107">Este parámetro debe ser CorDebugVersion_2_0 para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="935e9-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="935e9-108">[out] Puntero a un puntero a un objeto que se convertirá a un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaz y devuelve.</span><span class="sxs-lookup"><span data-stu-id="935e9-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="935e9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="935e9-109">Return Value</span></span>  
 <span data-ttu-id="935e9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="935e9-110">S_OK</span></span>  
 <span data-ttu-id="935e9-111">Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="935e9-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="935e9-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="935e9-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="935e9-113">`ppCordb` es nulo o `iDebuggerVersion` no es CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="935e9-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="935e9-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="935e9-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="935e9-115">No se puede asignar memoria suficiente para `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="935e9-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="935e9-116">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="935e9-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="935e9-117">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="935e9-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="935e9-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="935e9-118">Remarks</span></span>  
 <span data-ttu-id="935e9-119">El [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaz que se devuelve en `ppCordb` es la interfaz de depuración de nivel superior para todos los servicios de depuración administrada.</span><span class="sxs-lookup"><span data-stu-id="935e9-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="935e9-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="935e9-120">Requirements</span></span>  
 <span data-ttu-id="935e9-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="935e9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="935e9-122">**Encabezado**: CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="935e9-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="935e9-123">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="935e9-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="935e9-124">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="935e9-124">**.NET Framework Versions:** 3.5 SP1</span></span>
