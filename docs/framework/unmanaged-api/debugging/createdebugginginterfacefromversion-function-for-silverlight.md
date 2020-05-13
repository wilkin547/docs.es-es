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
ms.openlocfilehash: f40345b09cae164660711b987f62130518736518
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208629"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="36773-102">CreateDebuggingInterfaceFromVersion (Función para Silverlight)</span><span class="sxs-lookup"><span data-stu-id="36773-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>

<span data-ttu-id="36773-103">Acepta una cadena de versión de Common Language Runtime (CLR) que se devuelve desde la [función createversionstringfrommodule (](createversionstringfrommodule-function.md)y devuelve una interfaz de depurador correspondiente (normalmente, [ICorDebug](icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="36773-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36773-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36773-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36773-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36773-105">Parameters</span></span>  

 `szDebuggeeVersion`\
 <span data-ttu-id="36773-106">de Cadena de versión de CLR en el código depurado de destino, devuelto por la [función createversionstringfrommodule (](createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="36773-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`\
 <span data-ttu-id="36773-107">[out] Puntero a un puntero a un objeto COM (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="36773-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="36773-108">Este objeto se convertirá en un objeto [ICorDebug](icordebug-interface.md) antes de que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="36773-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36773-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36773-109">Return Value</span></span>

 `S_OK`\
 <span data-ttu-id="36773-110">`ppCordb`hace referencia a un objeto válido que implementa la interfaz de [interfaz ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="36773-110">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 `E_INVALIDARG`\
 <span data-ttu-id="36773-111">`szDebuggeeVersion` o `ppCordb` es nulo.</span><span class="sxs-lookup"><span data-stu-id="36773-111">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 <span data-ttu-id="36773-112">Componente que es necesario para que no se pueda encontrar la depuración de CLR.</span><span class="sxs-lookup"><span data-stu-id="36773-112">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="36773-113">No se encontró _mscordbi. dll_ o _mscordaccore. dll_ en el mismo directorio que el archivo CoreCLR. dll de destino.</span><span class="sxs-lookup"><span data-stu-id="36773-113">Either _mscordbi.dll_ or _mscordaccore.dll_ was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 <span data-ttu-id="36773-114">Ni mscordbi.dll, ni mscordaccore.dll son la misma versión que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="36773-114">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="36773-115">`E_FAIL`(u otros `E_` códigos de retorno) </span><span class="sxs-lookup"><span data-stu-id="36773-115">`E_FAIL` (or other `E_` return codes)</span></span>\
 <span data-ttu-id="36773-116">No se puede devolver una [interfaz ICorDebug](icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="36773-116">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36773-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36773-117">Remarks</span></span>

 <span data-ttu-id="36773-118">La interfaz que se devuelve proporciona las funciones para adjuntar a CLR en un proceso de destino y depurar el código administrado que ejecuta CLR.</span><span class="sxs-lookup"><span data-stu-id="36773-118">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36773-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36773-119">Requirements</span></span>

 <span data-ttu-id="36773-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36773-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36773-121">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="36773-121">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="36773-122">**Biblioteca:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="36773-122">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="36773-123">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="36773-123">**.NET Framework Versions:** 3.5 SP1</span></span>
