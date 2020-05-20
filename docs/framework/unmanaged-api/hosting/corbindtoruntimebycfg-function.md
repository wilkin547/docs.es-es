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
ms.openlocfilehash: 9326484c6a9f96d245e3c61a0ac3e3465a8a6dcd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616650"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="83a34-102">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="83a34-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="83a34-103">Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión que se lee de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="83a34-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="83a34-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="83a34-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a34-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83a34-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83a34-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83a34-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="83a34-107">de Un puntero a un `IStream` objeto que lee el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="83a34-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="83a34-108">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="83a34-108">[in] Reserved for future use.</span></span> <span data-ttu-id="83a34-109">Use 0 (cero) como valor.</span><span class="sxs-lookup"><span data-stu-id="83a34-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="83a34-110">de Un valor de la enumeración [STARTUP_FLAGS](startup-flags-enumeration.md) que especifica el comportamiento de inicio de CLR.</span><span class="sxs-lookup"><span data-stu-id="83a34-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="83a34-111">de `CLSID`De la coclase que implementa la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="83a34-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="83a34-112">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="83a34-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="83a34-113">de `IID`De la `ICorRuntimeHost` `ICLRRuntimeHost` interfaz o.</span><span class="sxs-lookup"><span data-stu-id="83a34-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="83a34-114">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="83a34-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="83a34-115">enuncia Puntero a la dirección de la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="83a34-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83a34-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83a34-116">Remarks</span></span>  
 <span data-ttu-id="83a34-117">El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar.</span><span class="sxs-lookup"><span data-stu-id="83a34-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="83a34-118">Para obtener más información acerca de los archivos XML, vea [esquema del archivo de configuración](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="83a34-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83a34-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83a34-119">Requirements</span></span>  
 <span data-ttu-id="83a34-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83a34-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83a34-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="83a34-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83a34-122">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83a34-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83a34-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83a34-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a34-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="83a34-124">See also</span></span>

- [<span data-ttu-id="83a34-125">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="83a34-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="83a34-126">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="83a34-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="83a34-127">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="83a34-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="83a34-128">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="83a34-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="83a34-129">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83a34-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="83a34-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="83a34-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
