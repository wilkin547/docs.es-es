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
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616819"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="2bac8-102">ClrCreateManagedInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="2bac8-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="2bac8-103">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="2bac8-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="2bac8-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2bac8-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="2bac8-105">Use la activación COM para crear una instancia del tipo administrado o use el hospedaje (consulte [interfaces de hospedaje de CLR agregadas en los .NET Framework 4 y 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="2bac8-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bac8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bac8-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bac8-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bac8-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="2bac8-108">de Puntero al nombre del tipo de instancia que se va a solicitar.</span><span class="sxs-lookup"><span data-stu-id="2bac8-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="2bac8-109">de `IID`Del tipo de instancia que se solicita.</span><span class="sxs-lookup"><span data-stu-id="2bac8-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="2bac8-110">enuncia Un puntero a un puntero a una instancia del tipo administrado solicitado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2bac8-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bac8-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2bac8-111">Remarks</span></span>  
 <span data-ttu-id="2bac8-112">El Common Language Runtime debe estar ya cargado en un proceso.</span><span class="sxs-lookup"><span data-stu-id="2bac8-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="2bac8-113">Por ejemplo, se puede cargar mediante una llamada a la función [CorBindToRuntimeEx](corbindtoruntimeex-function.md) antes de que `ClrCreateManagedInstance` se llame a la función.</span><span class="sxs-lookup"><span data-stu-id="2bac8-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="2bac8-114">Si no se carga el tiempo de ejecución, `ClrCreateManagedInstance` primero intenta cargar v 1.0.3705 del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2bac8-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="2bac8-115">Si se produce un error, intenta cargar la versión más reciente del Runtime.</span><span class="sxs-lookup"><span data-stu-id="2bac8-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bac8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bac8-116">Requirements</span></span>  
 <span data-ttu-id="2bac8-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bac8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bac8-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2bac8-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bac8-119">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2bac8-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bac8-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bac8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bac8-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2bac8-121">See also</span></span>

- [<span data-ttu-id="2bac8-122">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="2bac8-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="2bac8-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="2bac8-123">Hosting</span></span>](index.md)
