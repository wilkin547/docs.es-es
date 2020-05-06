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
ms.openlocfilehash: c83bdcca4fab75b4ae94500ceb785b6000cd802a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860866"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="2293d-102">CreateDebuggingInterfaceFromVersion (Función para Silverlight)</span><span class="sxs-lookup"><span data-stu-id="2293d-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="2293d-103">Acepta una cadena de versión de Common Language Runtime (CLR) que se devuelve desde la [función createversionstringfrommodule (](createversionstringfrommodule-function.md)y devuelve una interfaz de depurador correspondiente (normalmente, [ICorDebug](icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="2293d-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2293d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2293d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2293d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2293d-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="2293d-106">de Cadena de versión de CLR en el código depurado de destino, devuelto por la [función createversionstringfrommodule (](createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="2293d-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="2293d-107">[out] Puntero a un puntero a un objeto COM (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="2293d-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="2293d-108">Este objeto se convertirá en un objeto [ICorDebug](icordebug-interface.md) antes de que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="2293d-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2293d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2293d-109">Return Value</span></span>  
 <span data-ttu-id="2293d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2293d-110">S_OK</span></span>  
 <span data-ttu-id="2293d-111">`ppCordb`hace referencia a un objeto válido que implementa la interfaz de [interfaz ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2293d-111">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="2293d-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2293d-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="2293d-113">`szDebuggeeVersion` o `ppCordb` es nulo.</span><span class="sxs-lookup"><span data-stu-id="2293d-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="2293d-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="2293d-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="2293d-115">Componente que es necesario para que no se pueda encontrar la depuración de CLR.</span><span class="sxs-lookup"><span data-stu-id="2293d-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="2293d-116">Esto significa que no se encontraron los archivos mscordbi.dll o mscordaccore.dll en el mismo directorio que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="2293d-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="2293d-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="2293d-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="2293d-118">Ni mscordbi.dll, ni mscordaccore.dll son la misma versión que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="2293d-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="2293d-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="2293d-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2293d-120">No se puede devolver una [interfaz ICorDebug](icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2293d-120">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2293d-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2293d-121">Remarks</span></span>  
 <span data-ttu-id="2293d-122">La interfaz que se devuelve proporciona las funciones para adjuntar a CLR en un proceso de destino y depurar el código administrado que ejecuta CLR.</span><span class="sxs-lookup"><span data-stu-id="2293d-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2293d-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2293d-123">Requirements</span></span>  
 <span data-ttu-id="2293d-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2293d-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2293d-125">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="2293d-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="2293d-126">**Biblioteca:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="2293d-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="2293d-127">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="2293d-127">**.NET Framework Versions:** 3.5 SP1</span></span>
