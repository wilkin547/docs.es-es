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
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176453"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="241c4-102">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="241c4-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="241c4-103">Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basado en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="241c4-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="241c4-104">Esta función está obsoleta en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="241c4-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="241c4-105">En su lugar, para obtener una interfaz para Common Language Runtime (CLR) 2.0, utilice el método [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="241c4-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="241c4-106">Para obtener una interfaz para CLR 4 o posterior, llame a la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="241c4-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="241c4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="241c4-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="241c4-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="241c4-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="241c4-109">[en] El depurador `ICorDebug` espera la versión de ese.</span><span class="sxs-lookup"><span data-stu-id="241c4-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="241c4-110">Vea el [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeración para los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="241c4-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="241c4-111">[en] La versión de Common Language Runtime asociada a la aplicación o proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="241c4-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="241c4-112">Vea el [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) método para obtener información sobre cómo recuperar este valor.</span><span class="sxs-lookup"><span data-stu-id="241c4-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="241c4-113">[fuera] La ubicación que recibe un `ICorDebug` puntero al objeto.</span><span class="sxs-lookup"><span data-stu-id="241c4-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="241c4-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="241c4-114">Return Value</span></span>  
 <span data-ttu-id="241c4-115">Este método devuelve códigos de error COM estándar tal como se defineen en el archivo WinError.h además de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="241c4-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="241c4-116">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="241c4-116">Return code</span></span>|<span data-ttu-id="241c4-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="241c4-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="241c4-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="241c4-118">S_OK</span></span>|<span data-ttu-id="241c4-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="241c4-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="241c4-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="241c4-120">E_INVALIDARG</span></span>|<span data-ttu-id="241c4-121">`szDebuggeeVersion`o `ppCordb` es null, o la cadena de versión es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="241c4-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="241c4-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="241c4-122">Remarks</span></span>  
 <span data-ttu-id="241c4-123">El `szDebuggeeVersion` parámetro se asigna a la versión correspondiente de MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="241c4-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="241c4-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="241c4-124">Requirements</span></span>  
 <span data-ttu-id="241c4-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="241c4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="241c4-126">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="241c4-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="241c4-127">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="241c4-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="241c4-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="241c4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241c4-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="241c4-129">See also</span></span>

- [<span data-ttu-id="241c4-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="241c4-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
