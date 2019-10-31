---
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
ms.openlocfilehash: e23dfb86c2129a02a0ca95de8c89d8294e97ad81
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136835"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="6bd64-102">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="6bd64-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="6bd64-103">Crea un objeto [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) basado en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="6bd64-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="6bd64-104">Esta función está obsoleta en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6bd64-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="6bd64-105">En su lugar, para obtener una interfaz para el Common Language Runtime (CLR) 2,0, use el método [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="6bd64-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="6bd64-106">Para obtener una interfaz para CLR 4 o posterior, llame a la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="6bd64-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd64-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6bd64-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bd64-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6bd64-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="6bd64-109">de La versión de `ICorDebug` esperada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="6bd64-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="6bd64-110">Vea la enumeración [CorDebugInterfaceVersion (](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) para ver los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="6bd64-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="6bd64-111">de La versión Common Language Runtime asociada con la aplicación o el proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="6bd64-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="6bd64-112">Vea el método [GetVersionFromProcess (](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion (](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) para obtener información sobre cómo recuperar este valor.</span><span class="sxs-lookup"><span data-stu-id="6bd64-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="6bd64-113">enuncia Ubicación que recibe un puntero al objeto de `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="6bd64-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bd64-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6bd64-114">Return Value</span></span>  
 <span data-ttu-id="6bd64-115">Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="6bd64-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="6bd64-116">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="6bd64-116">Return code</span></span>|<span data-ttu-id="6bd64-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6bd64-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6bd64-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="6bd64-118">S_OK</span></span>|<span data-ttu-id="6bd64-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6bd64-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="6bd64-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6bd64-120">E_INVALIDARG</span></span>|<span data-ttu-id="6bd64-121">`szDebuggeeVersion` o `ppCordb` es null, o la cadena de versión es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="6bd64-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bd64-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6bd64-122">Remarks</span></span>  
 <span data-ttu-id="6bd64-123">El parámetro `szDebuggeeVersion` se asigna a la versión correspondiente de MSCorDbi. dll.</span><span class="sxs-lookup"><span data-stu-id="6bd64-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bd64-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6bd64-124">Requirements</span></span>  
 <span data-ttu-id="6bd64-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bd64-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd64-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6bd64-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bd64-127">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6bd64-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bd64-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd64-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd64-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bd64-129">See also</span></span>

- [<span data-ttu-id="6bd64-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="6bd64-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
