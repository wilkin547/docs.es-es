---
description: 'Más información acerca de: función LockClrVersion'
title: LockClrVersion (Función)
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 268c08cdd24a826ba92cc8865dfd036f544febcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679932"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="ca947-103">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="ca947-103">LockClrVersion Function</span></span>

<span data-ttu-id="ca947-104">Permite al host determinar qué versión de Common Language Runtime (CLR) se utilizará en el proceso antes de inicializar explícitamente CLR.</span><span class="sxs-lookup"><span data-stu-id="ca947-104">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="ca947-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ca947-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca947-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca947-106">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca947-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca947-107">Parameters</span></span>  

 `hostCallback`  
 <span data-ttu-id="ca947-108">de Función a la que llamará CLR al inicializarse.</span><span class="sxs-lookup"><span data-stu-id="ca947-108">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="ca947-109">de Función a la que llamará el host para informar al CLR de que se está iniciando la inicialización.</span><span class="sxs-lookup"><span data-stu-id="ca947-109">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="ca947-110">de Función a la que llamará el host para informar al CLR de que la inicialización se ha completado.</span><span class="sxs-lookup"><span data-stu-id="ca947-110">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca947-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca947-111">Return Value</span></span>  

 <span data-ttu-id="ca947-112">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="ca947-112">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="ca947-113">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="ca947-113">Return code</span></span>|<span data-ttu-id="ca947-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca947-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ca947-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca947-115">S_OK</span></span>|<span data-ttu-id="ca947-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca947-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="ca947-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ca947-117">E_INVALIDARG</span></span>|<span data-ttu-id="ca947-118">Uno o varios argumentos son NULL.</span><span class="sxs-lookup"><span data-stu-id="ca947-118">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca947-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ca947-119">Remarks</span></span>  

 <span data-ttu-id="ca947-120">El host llama a `LockClrVersion` antes de inicializar el CLR.</span><span class="sxs-lookup"><span data-stu-id="ca947-120">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="ca947-121">`LockClrVersion` toma tres parámetros, todos ellos son devoluciones de llamada de tipo [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="ca947-121">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="ca947-122">Este tipo se define como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="ca947-122">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="ca947-123">Los siguientes pasos se producen tras la inicialización del tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="ca947-123">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="ca947-124">El host llama a [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o a una de las otras funciones de inicialización en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ca947-124">The host calls [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="ca947-125">Como alternativa, el host podría inicializar el tiempo de ejecución mediante la activación de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="ca947-125">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="ca947-126">El Runtime llama a la función especificada por el `hostCallback` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ca947-126">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="ca947-127">La función especificada por `hostCallback` entonces realiza la siguiente secuencia de llamadas:</span><span class="sxs-lookup"><span data-stu-id="ca947-127">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="ca947-128">Función especificada por el `pBeginHostSetup` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ca947-128">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="ca947-129">`CorBindToRuntimeEx` (u otra función de inicialización en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="ca947-129">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="ca947-130">[ICLRRuntimeHost:: SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="ca947-130">[ICLRRuntimeHost::SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="ca947-131">[ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="ca947-131">[ICLRRuntimeHost::Start](iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="ca947-132">Función especificada por el `pEndHostSetup` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ca947-132">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="ca947-133">Todas las llamadas de `pBeginHostSetup` a `pEndHostSetup` deben producirse en un único subproceso o fibra, con la misma pila lógica.</span><span class="sxs-lookup"><span data-stu-id="ca947-133">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="ca947-134">Este subproceso puede ser diferente del subproceso en el que `hostCallback` se llama a.</span><span class="sxs-lookup"><span data-stu-id="ca947-134">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca947-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca947-135">Requirements</span></span>  

 <span data-ttu-id="ca947-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca947-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca947-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca947-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca947-138">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca947-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca947-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca947-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca947-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca947-140">See also</span></span>

- [<span data-ttu-id="ca947-141">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ca947-141">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
