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
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a375ea586bacc2d3dafe53d493a7467730fae889
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432326"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="aac5e-102">ClrCreateManagedInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="aac5e-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="aac5e-103">Crea una instancia del tipo administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="aac5e-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="aac5e-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aac5e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="aac5e-105">Utilizar la activación de COM para crear una instancia del tipo administrado o utilizar el hospedaje (consulte [de hospedaje de CLR agregadas Interfaces en .NET Framework 4 y 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="aac5e-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac5e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aac5e-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aac5e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aac5e-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="aac5e-108">[in] Un puntero al nombre del tipo de instancia que se solicita.</span><span class="sxs-lookup"><span data-stu-id="aac5e-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="aac5e-109">[in] El `IID` del tipo de instancia que se solicita.</span><span class="sxs-lookup"><span data-stu-id="aac5e-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="aac5e-110">[out] Un puntero a un puntero a una instancia del tipo administrado que se solicitó el llamador.</span><span class="sxs-lookup"><span data-stu-id="aac5e-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aac5e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aac5e-111">Remarks</span></span>  
 <span data-ttu-id="aac5e-112">Common language runtime debe estar ya cargado en un proceso.</span><span class="sxs-lookup"><span data-stu-id="aac5e-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="aac5e-113">Por ejemplo, se puede cargar mediante el uso de una llamada a la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funcionen antes de la `ClrCreateManagedInstance` función se invoca.</span><span class="sxs-lookup"><span data-stu-id="aac5e-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="aac5e-114">Si el tiempo de ejecución no está cargado, `ClrCreateManagedInstance` primero intenta cargar v1.0.3705 del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aac5e-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="aac5e-115">Si se produce un error, intenta cargar la versión más reciente del runtime.</span><span class="sxs-lookup"><span data-stu-id="aac5e-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aac5e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aac5e-116">Requirements</span></span>  
 <span data-ttu-id="aac5e-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aac5e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aac5e-118">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aac5e-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aac5e-119">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aac5e-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aac5e-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac5e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac5e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="aac5e-121">See Also</span></span>  
 [<span data-ttu-id="aac5e-122">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="aac5e-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="aac5e-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="aac5e-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
