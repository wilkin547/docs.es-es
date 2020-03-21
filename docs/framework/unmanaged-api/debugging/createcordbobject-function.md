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
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179228"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="fefbb-102">CreateCordbObject (Función)</span><span class="sxs-lookup"><span data-stu-id="fefbb-102">CreateCordbObject Function</span></span>
<span data-ttu-id="fefbb-103">Crea una interfaz de depurador ([ICorDebug](icordebug-interface.md)) que proporciona funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.</span><span class="sxs-lookup"><span data-stu-id="fefbb-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fefbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fefbb-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fefbb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fefbb-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="fefbb-106">[in] Versión de depuración del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="fefbb-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="fefbb-107">Este parámetro debe ser CorDebugVersion_2_0 para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="fefbb-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="fefbb-108">[fuera] Puntero a un puntero a un objeto que se convertirá a un [ICorDebug](icordebug-interface.md) interfaz y se devolverá.</span><span class="sxs-lookup"><span data-stu-id="fefbb-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fefbb-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fefbb-109">Return Value</span></span>  
 <span data-ttu-id="fefbb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fefbb-110">S_OK</span></span>  
 <span data-ttu-id="fefbb-111">Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="fefbb-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="fefbb-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fefbb-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="fefbb-113">`ppCordb` es nulo o `iDebuggerVersion` no es CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="fefbb-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="fefbb-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fefbb-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="fefbb-115">No se puede asignar memoria suficiente para `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="fefbb-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="fefbb-116">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="fefbb-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="fefbb-117">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="fefbb-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fefbb-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fefbb-118">Remarks</span></span>  
 <span data-ttu-id="fefbb-119">El [ICorDebug](icordebug-interface.md) interfaz `ppCordb` que se devuelve en es la interfaz de depuración de nivel superior para todos los servicios de depuración administrados.</span><span class="sxs-lookup"><span data-stu-id="fefbb-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fefbb-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fefbb-120">Requirements</span></span>  
 <span data-ttu-id="fefbb-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fefbb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fefbb-122">**Encabezado:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="fefbb-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="fefbb-123">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="fefbb-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="fefbb-124">**Versiones de .NET Framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="fefbb-124">**.NET Framework Versions:** 3.5 SP1</span></span>
