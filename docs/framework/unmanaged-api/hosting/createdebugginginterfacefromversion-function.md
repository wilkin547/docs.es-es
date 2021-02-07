---
description: 'Más información acerca de: CreateDebuggingInterfaceFromVersion ((función)'
title: CreateDebuggingInterfaceFromVersion (Función)
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: 163ada49f028071b48c93ee3c565152a773782ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760638"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="21bbf-103">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="21bbf-103">CreateDebuggingInterfaceFromVersion Function</span></span>

<span data-ttu-id="21bbf-104">Crea un objeto [ICorDebug](../debugging/icordebug-interface.md) basado en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="21bbf-104">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="21bbf-105">Esta función está obsoleta en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="21bbf-105">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="21bbf-106">En su lugar, para obtener una interfaz para el Common Language Runtime (CLR) 2,0, use el método [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="21bbf-106">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="21bbf-107">Para obtener una interfaz para CLR 4 o posterior, llame a la función [CLRCreateInstance](clrcreateinstance-function.md) y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="21bbf-107">To get an interface for CLR 4 or later, call the [CLRCreateInstance](clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21bbf-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21bbf-108">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21bbf-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21bbf-109">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="21bbf-110">de Versión de `ICorDebug` esperada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="21bbf-110">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="21bbf-111">Vea la enumeración [CorDebugInterfaceVersion (](../debugging/cordebuginterfaceversion-enumeration.md) para ver los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="21bbf-111">See the [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="21bbf-112">de La versión Common Language Runtime asociada con la aplicación o el proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="21bbf-112">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="21bbf-113">Vea el método [GetVersionFromProcess (](getversionfromprocess-function.md) o [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md) para obtener información sobre cómo recuperar este valor.</span><span class="sxs-lookup"><span data-stu-id="21bbf-113">See the [GetVersionFromProcess](getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="21bbf-114">enuncia Ubicación que recibe un puntero al `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="21bbf-114">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21bbf-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21bbf-115">Return Value</span></span>  

 <span data-ttu-id="21bbf-116">Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="21bbf-116">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="21bbf-117">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="21bbf-117">Return code</span></span>|<span data-ttu-id="21bbf-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="21bbf-118">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="21bbf-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="21bbf-119">S_OK</span></span>|<span data-ttu-id="21bbf-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="21bbf-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="21bbf-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="21bbf-121">E_INVALIDARG</span></span>|<span data-ttu-id="21bbf-122">`szDebuggeeVersion` o `ppCordb` es null, o la cadena de versión es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="21bbf-122">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21bbf-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="21bbf-123">Remarks</span></span>  

 <span data-ttu-id="21bbf-124">El `szDebuggeeVersion` parámetro se asigna a la versión correspondiente de MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="21bbf-124">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21bbf-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21bbf-125">Requirements</span></span>  

 <span data-ttu-id="21bbf-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21bbf-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21bbf-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="21bbf-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21bbf-128">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21bbf-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21bbf-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21bbf-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bbf-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="21bbf-130">See also</span></span>

- [<span data-ttu-id="21bbf-131">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="21bbf-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
