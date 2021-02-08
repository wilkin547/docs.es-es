---
description: 'Más información acerca de: ClrCreateManagedInstance ((función)'
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
ms.openlocfilehash: b6d3b014f54dd563e53cd8a4c48907d01945015f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799935"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="3abcb-103">ClrCreateManagedInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="3abcb-103">ClrCreateManagedInstance Function</span></span>

<span data-ttu-id="3abcb-104">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="3abcb-104">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="3abcb-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3abcb-105">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="3abcb-106">Use la activación COM para crear una instancia del tipo administrado o use el hospedaje (consulte [interfaces de hospedaje de CLR agregadas en los .NET Framework 4 y 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="3abcb-106">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3abcb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3abcb-107">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3abcb-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3abcb-108">Parameters</span></span>  

 `pTypeName`  
 <span data-ttu-id="3abcb-109">de Puntero al nombre del tipo de instancia que se va a solicitar.</span><span class="sxs-lookup"><span data-stu-id="3abcb-109">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="3abcb-110">de `IID` Del tipo de instancia que se solicita.</span><span class="sxs-lookup"><span data-stu-id="3abcb-110">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="3abcb-111">enuncia Un puntero a un puntero a una instancia del tipo administrado solicitado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3abcb-111">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3abcb-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3abcb-112">Remarks</span></span>  

 <span data-ttu-id="3abcb-113">El Common Language Runtime debe estar ya cargado en un proceso.</span><span class="sxs-lookup"><span data-stu-id="3abcb-113">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="3abcb-114">Por ejemplo, se puede cargar mediante una llamada a la función [CorBindToRuntimeEx](corbindtoruntimeex-function.md) antes de que `ClrCreateManagedInstance` se llame a la función.</span><span class="sxs-lookup"><span data-stu-id="3abcb-114">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="3abcb-115">Si no se carga el tiempo de ejecución, `ClrCreateManagedInstance` primero intenta cargar v 1.0.3705 del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3abcb-115">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="3abcb-116">Si se produce un error, intenta cargar la versión más reciente del Runtime.</span><span class="sxs-lookup"><span data-stu-id="3abcb-116">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3abcb-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3abcb-117">Requirements</span></span>  

 <span data-ttu-id="3abcb-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3abcb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3abcb-119">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3abcb-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3abcb-120">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3abcb-120">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3abcb-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3abcb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abcb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3abcb-122">See also</span></span>

- [<span data-ttu-id="3abcb-123">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="3abcb-123">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="3abcb-124">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3abcb-124">Hosting</span></span>](index.md)
