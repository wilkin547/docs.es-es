---
title: ClrCreateManagedInstance (Función)
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176544"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="96e7e-102">ClrCreateManagedInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="96e7e-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="96e7e-103">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="96e7e-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="96e7e-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="96e7e-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="96e7e-105">Use la activación COM para crear una instancia del tipo administrado o use el hospedaje (consulte Interfaces de [hospedaje de CLR agregadas en .NET Framework 4 y 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="96e7e-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e7e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96e7e-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96e7e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96e7e-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="96e7e-108">[en] Puntero al nombre del tipo de instancia que se solicita.</span><span class="sxs-lookup"><span data-stu-id="96e7e-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="96e7e-109">[en] El `IID` tipo de instancia que se solicita.</span><span class="sxs-lookup"><span data-stu-id="96e7e-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="96e7e-110">[fuera] Puntero a un puntero a una instancia del tipo administrado solicitado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="96e7e-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96e7e-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="96e7e-111">Remarks</span></span>  
 <span data-ttu-id="96e7e-112">Common Language Runtime ya debe cargarse en un proceso.</span><span class="sxs-lookup"><span data-stu-id="96e7e-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="96e7e-113">Por ejemplo, se puede cargar mediante una llamada a la `ClrCreateManagedInstance` [función CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) antes de llamar a la función.</span><span class="sxs-lookup"><span data-stu-id="96e7e-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="96e7e-114">Si no se carga `ClrCreateManagedInstance` el tiempo de ejecución, primero intenta cargar v1.0.3705 del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="96e7e-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="96e7e-115">Si se produce un error, intenta cargar la versión más reciente del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="96e7e-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96e7e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96e7e-116">Requirements</span></span>  
 <span data-ttu-id="96e7e-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96e7e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96e7e-118">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="96e7e-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96e7e-119">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="96e7e-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96e7e-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e7e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e7e-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96e7e-121">See also</span></span>

- [<span data-ttu-id="96e7e-122">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="96e7e-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="96e7e-123">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="96e7e-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
