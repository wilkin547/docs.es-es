---
title: CreateDebuggingInterfaceFromVersion (Función para Silverlight)
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 438af9f191f48a86207c3b343ba428eef2c1fabc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132200"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="80ad8-102">CreateDebuggingInterfaceFromVersion (Función para Silverlight)</span><span class="sxs-lookup"><span data-stu-id="80ad8-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="80ad8-103">Acepta una cadena de versión de Common Language Runtime (CLR) que se devuelve desde la [función createversionstringfrommodule (](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)y devuelve una interfaz de depurador correspondiente (normalmente, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="80ad8-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ad8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80ad8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80ad8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80ad8-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="80ad8-106">de Cadena de versión de CLR en el código depurado de destino, devuelto por la [función createversionstringfrommodule (](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="80ad8-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="80ad8-107">[out] Puntero a un puntero a un objeto COM (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="80ad8-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="80ad8-108">Este objeto se convertirá en un objeto [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) antes de que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="80ad8-108">This object will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80ad8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80ad8-109">Return Value</span></span>  
 <span data-ttu-id="80ad8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="80ad8-110">S_OK</span></span>  
 <span data-ttu-id="80ad8-111">`ppCordb` hace referencia a un objeto válido que implementa la interfaz de [interfaz ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="80ad8-111">`ppCordb` references a valid object that implements the [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="80ad8-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="80ad8-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="80ad8-113">`szDebuggeeVersion` o `ppCordb` es nulo.</span><span class="sxs-lookup"><span data-stu-id="80ad8-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="80ad8-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="80ad8-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="80ad8-115">Componente que es necesario para que no se pueda encontrar la depuración de CLR.</span><span class="sxs-lookup"><span data-stu-id="80ad8-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="80ad8-116">Esto significa que no se encontraron los archivos mscordbi.dll o mscordaccore.dll en el mismo directorio que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="80ad8-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="80ad8-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="80ad8-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="80ad8-118">Ni mscordbi.dll, ni mscordaccore.dll son la misma versión que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="80ad8-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="80ad8-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="80ad8-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="80ad8-120">No se puede devolver una [interfaz ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="80ad8-120">Unable to return an [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80ad8-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80ad8-121">Remarks</span></span>  
 <span data-ttu-id="80ad8-122">La interfaz que se devuelve proporciona las funciones para adjuntar a CLR en un proceso de destino y depurar el código administrado que ejecuta CLR.</span><span class="sxs-lookup"><span data-stu-id="80ad8-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ad8-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80ad8-123">Requirements</span></span>  
 <span data-ttu-id="80ad8-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80ad8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ad8-125">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="80ad8-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="80ad8-126">**Biblioteca:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="80ad8-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="80ad8-127">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="80ad8-127">**.NET Framework Versions:** 3.5 SP1</span></span>
