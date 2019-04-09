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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d1c49e8762d00e3e154c598c2542c4a76b9b28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107502"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="d7fca-102">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="d7fca-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="d7fca-103">Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basándose en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="d7fca-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="d7fca-104">Esta función está obsoleta en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7fca-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="d7fca-105">En su lugar, para obtener una interfaz de common language runtime (CLR) 2.0, use el [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="d7fca-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="d7fca-106">Para obtener una interfaz CLR 4 o versiones posteriores, llame a la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) función y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="d7fca-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7fca-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7fca-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7fca-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7fca-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="d7fca-109">[in] La versión de `ICorDebug` que se espera que el depurador.</span><span class="sxs-lookup"><span data-stu-id="d7fca-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="d7fca-110">Consulte la [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeración para los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="d7fca-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="d7fca-111">[in] El lenguaje versión de common runtime asociada con la aplicación o proceso que se desea depurar.</span><span class="sxs-lookup"><span data-stu-id="d7fca-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="d7fca-112">Consulte la [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) método para obtener información sobre cómo recuperar este valor.</span><span class="sxs-lookup"><span data-stu-id="d7fca-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="d7fca-113">[out] La ubicación que recibe un puntero a la `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="d7fca-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7fca-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d7fca-114">Return Value</span></span>  
 <span data-ttu-id="d7fca-115">Este método devuelve códigos de error COM estándar, tal como se define en el archivo WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="d7fca-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="d7fca-116">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="d7fca-116">Return code</span></span>|<span data-ttu-id="d7fca-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7fca-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d7fca-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7fca-118">S_OK</span></span>|<span data-ttu-id="d7fca-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d7fca-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="d7fca-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d7fca-120">E_INVALIDARG</span></span>|`szDebuggeeVersion` <span data-ttu-id="d7fca-121">o `ppCordb` es null, o la versión de cadena no es correcta.</span><span class="sxs-lookup"><span data-stu-id="d7fca-121">or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7fca-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7fca-122">Remarks</span></span>  
 <span data-ttu-id="d7fca-123">El `szDebuggeeVersion` parámetro se asigna a la versión correspondiente de MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="d7fca-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7fca-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7fca-124">Requirements</span></span>  
 <span data-ttu-id="d7fca-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7fca-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7fca-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7fca-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7fca-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7fca-127">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d7fca-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d7fca-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7fca-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7fca-129">See also</span></span>

- [<span data-ttu-id="d7fca-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d7fca-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
