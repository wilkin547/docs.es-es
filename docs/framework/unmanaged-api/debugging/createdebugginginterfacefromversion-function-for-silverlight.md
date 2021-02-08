---
description: 'Más información sobre: función CreateDebuggingInterfaceFromVersion (para Silverlight'
title: CreateDebuggingInterfaceFromVersion (Función para Silverlight)
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 8c61593f2e912260ecca65efce9f905ce56e88dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801454"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="ed489-103">CreateDebuggingInterfaceFromVersion (Función para Silverlight)</span><span class="sxs-lookup"><span data-stu-id="ed489-103">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>

<span data-ttu-id="ed489-104">Acepta una cadena de versión de Common Language Runtime (CLR) que se devuelve desde la [función createversionstringfrommodule (](createversionstringfrommodule-function.md)y devuelve una interfaz de depurador correspondiente (normalmente, [ICorDebug](icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="ed489-104">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed489-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed489-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed489-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed489-106">Parameters</span></span>  

 `szDebuggeeVersion`\
 <span data-ttu-id="ed489-107">de Cadena de versión de CLR en el código depurado de destino, devuelto por la [función createversionstringfrommodule (](createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="ed489-107">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`\
 <span data-ttu-id="ed489-108">[out] Puntero a un puntero a un objeto COM (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="ed489-108">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="ed489-109">Este objeto se convertirá en un objeto [ICorDebug](icordebug-interface.md) antes de que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="ed489-109">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed489-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed489-110">Return Value</span></span>

 `S_OK`\
 <span data-ttu-id="ed489-111">`ppCordb` hace referencia a un objeto válido que implementa la interfaz de [interfaz ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ed489-111">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 `E_INVALIDARG`\
 <span data-ttu-id="ed489-112">`szDebuggeeVersion` o `ppCordb` es nulo.</span><span class="sxs-lookup"><span data-stu-id="ed489-112">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 <span data-ttu-id="ed489-113">Componente que es necesario para que no se pueda encontrar la depuración de CLR.</span><span class="sxs-lookup"><span data-stu-id="ed489-113">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="ed489-114">No se encontró _mscordbi.dll_ o _mscordaccore.dll_ en el mismo directorio que el CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="ed489-114">Either _mscordbi.dll_ or _mscordaccore.dll_ was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 <span data-ttu-id="ed489-115">Ni mscordbi.dll, ni mscordaccore.dll son la misma versión que CoreCLR.dll de destino.</span><span class="sxs-lookup"><span data-stu-id="ed489-115">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="ed489-116">`E_FAIL` (u otros `E_` códigos de retorno) </span><span class="sxs-lookup"><span data-stu-id="ed489-116">`E_FAIL` (or other `E_` return codes)</span></span>\
 <span data-ttu-id="ed489-117">No se puede devolver una [interfaz ICorDebug](icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ed489-117">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed489-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ed489-118">Remarks</span></span>

 <span data-ttu-id="ed489-119">La interfaz que se devuelve proporciona las funciones para adjuntar a CLR en un proceso de destino y depurar el código administrado que ejecuta CLR.</span><span class="sxs-lookup"><span data-stu-id="ed489-119">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed489-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed489-120">Requirements</span></span>

 <span data-ttu-id="ed489-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed489-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed489-122">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="ed489-122">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="ed489-123">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="ed489-123">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="ed489-124">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="ed489-124">**.NET Framework Versions:** 3.5 SP1</span></span>
