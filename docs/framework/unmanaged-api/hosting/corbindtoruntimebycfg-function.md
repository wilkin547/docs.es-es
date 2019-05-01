---
title: CorBindToRuntimeByCfg (Función)
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbba208296dd2099c9da58c81ff66fddc78fdc86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985873"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="a8f1d-102">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="a8f1d-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="a8f1d-103">Carga common language runtime (CLR) en un proceso mediante el uso de información de versión que se lee desde un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="a8f1d-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8f1d-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8f1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8f1d-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8f1d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8f1d-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="a8f1d-107">[in] Un puntero a un `IStream` objeto que lee el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="a8f1d-108">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-108">[in] Reserved for future use.</span></span> <span data-ttu-id="a8f1d-109">Use 0 (cero) como valor.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="a8f1d-110">[in] Un valor de la [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeración que especifica el comportamiento de inicio de CLR.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="a8f1d-111">[in] El `CLSID` de la coclase que implementa el [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="a8f1d-112">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="a8f1d-113">[in] El `IID` de uno de ellos la `ICorRuntimeHost` o `ICLRRuntimeHost` interfaz.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="a8f1d-114">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="a8f1d-115">[out] Un puntero a la dirección de la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8f1d-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8f1d-116">Remarks</span></span>  
 <span data-ttu-id="a8f1d-117">El formato del archivo XML se modela después del archivo de configuración de aplicación estándar.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="a8f1d-118">Para obtener más información acerca de los archivos XML, vea [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="a8f1d-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8f1d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8f1d-119">Requirements</span></span>  
 <span data-ttu-id="a8f1d-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8f1d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8f1d-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a8f1d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8f1d-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8f1d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8f1d-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8f1d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f1d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8f1d-124">See also</span></span>

- [<span data-ttu-id="a8f1d-125">CorBindToCurrentRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="a8f1d-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="a8f1d-126">CorBindToRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="a8f1d-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="a8f1d-127">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="a8f1d-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="a8f1d-128">CorBindToRuntimeHost (función)</span><span class="sxs-lookup"><span data-stu-id="a8f1d-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="a8f1d-129">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8f1d-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="a8f1d-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="a8f1d-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
