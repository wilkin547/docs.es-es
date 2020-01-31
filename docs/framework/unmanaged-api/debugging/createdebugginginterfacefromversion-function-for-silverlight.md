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
ms.openlocfilehash: 85b5a5a630f399d0e036de434365e2e4f8f02dea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793835"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="5288c-102">CreateDebuggingInterfaceFromVersion (Función para Silverlight)</span><span class="sxs-lookup"><span data-stu-id="5288c-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="5288c-103">Acepta una cadena de versión de Common Language Runtime (CLR) que se devuelve desde la [función createversionstringfrommodule (](createversionstringfrommodule-function.md)y devuelve una interfaz de depurador correspondiente (normalmente, [ICorDebug](icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="5288c-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5288c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5288c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5288c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5288c-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="5288c-106">de Cadena de versión de CLR en el código depurado de destino, devuelto por la [función createversionstringfrommodule (](createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="5288c-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="5288c-107">[out] Puntero a un puntero a un objeto COM (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="5288c-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="5288c-108">Este objeto se convertirá en un objeto [ICorDebug](icordebug-interface.md) antes de que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="5288c-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5288c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5288c-109">Return Value</span></span>  
 <span data-ttu-id="5288c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5288c-110">S_OK</span></span>  
 <span data-ttu-id="5288c-111">`ppCordb` hace referencia a un objeto válido que implementa la interfaz de [interfaz ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5288c-111">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="5288c-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5288c-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="5288c-113">`szDebuggeeVersion` o `ppCordb` es nulo.</span><span class="sxs-lookup"><span data-stu-id="5288c-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="5288c-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="5288c-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="5288c-115">Componente que es necesario para que no se pueda encontrar la depuración de CLR.</span><span class="sxs-lookup"><span data-stu-id="5288c-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="5288c-116">Esto significa que no se encontraron los archivos mscordbi.dll o mscordaccore.dll en el mismo directorio que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="5288c-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="5288c-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="5288c-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="5288c-118">Ni mscordbi.dll, ni mscordaccore.dll son la misma versión que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="5288c-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="5288c-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="5288c-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5288c-120">No se puede devolver una [interfaz ICorDebug](icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5288c-120">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5288c-121">Notas</span><span class="sxs-lookup"><span data-stu-id="5288c-121">Remarks</span></span>  
 <span data-ttu-id="5288c-122">La interfaz que se devuelve proporciona las funciones para adjuntar a CLR en un proceso de destino y depurar el código administrado que ejecuta CLR.</span><span class="sxs-lookup"><span data-stu-id="5288c-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5288c-123">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5288c-123">Requirements</span></span>  
 <span data-ttu-id="5288c-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5288c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5288c-125">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="5288c-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="5288c-126">**Biblioteca:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="5288c-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="5288c-127">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="5288c-127">**.NET Framework Versions:** 3.5 SP1</span></span>
