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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985717"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="74be0-102">CreateDebuggingInterfaceFromVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="74be0-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="74be0-103">Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) objeto basándose en la información de versión especificada.</span><span class="sxs-lookup"><span data-stu-id="74be0-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="74be0-104">Esta función está obsoleta en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74be0-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="74be0-105">En su lugar, para obtener una interfaz de common language runtime (CLR) 2.0, use el [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) método y especifique el identificador de clase CLSID_CLRDebuggingLegacy y el identificador de interfaz IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="74be0-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="74be0-106">Para obtener una interfaz CLR 4 o versiones posteriores, llame a la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) función y especifique el identificador de clase CLSID_CLRDebugging y el identificador de interfaz IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="74be0-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74be0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74be0-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74be0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74be0-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="74be0-109">[in] La versión de `ICorDebug` que se espera que el depurador.</span><span class="sxs-lookup"><span data-stu-id="74be0-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="74be0-110">Consulte la [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeración para los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="74be0-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="74be0-111">[in] El lenguaje versión de common runtime asociada con la aplicación o proceso que se desea depurar.</span><span class="sxs-lookup"><span data-stu-id="74be0-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="74be0-112">Consulte la [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) o [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) método para obtener información sobre cómo recuperar este valor.</span><span class="sxs-lookup"><span data-stu-id="74be0-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="74be0-113">[out] La ubicación que recibe un puntero a la `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="74be0-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74be0-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74be0-114">Return Value</span></span>  
 <span data-ttu-id="74be0-115">Este método devuelve códigos de error COM estándar, tal como se define en el archivo WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="74be0-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="74be0-116">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="74be0-116">Return code</span></span>|<span data-ttu-id="74be0-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="74be0-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="74be0-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="74be0-118">S_OK</span></span>|<span data-ttu-id="74be0-119">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="74be0-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="74be0-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="74be0-120">E_INVALIDARG</span></span>|<span data-ttu-id="74be0-121">`szDebuggeeVersion` o `ppCordb` es null, o la versión de cadena no es correcta.</span><span class="sxs-lookup"><span data-stu-id="74be0-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74be0-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74be0-122">Remarks</span></span>  
 <span data-ttu-id="74be0-123">El `szDebuggeeVersion` parámetro se asigna a la versión correspondiente de MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="74be0-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74be0-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74be0-124">Requirements</span></span>  
 <span data-ttu-id="74be0-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74be0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74be0-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74be0-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74be0-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74be0-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74be0-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74be0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74be0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="74be0-129">See also</span></span>

- [<span data-ttu-id="74be0-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="74be0-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
