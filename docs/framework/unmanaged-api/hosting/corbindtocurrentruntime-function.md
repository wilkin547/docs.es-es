---
title: CorBindToCurrentRuntime (Función)
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3667ac5a19664507b767ee6c5421a5e93f6cdfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433261"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="f6b30-102">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="f6b30-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="f6b30-103">Carga common language runtime (CLR) en un proceso usando la información de versión almacenada en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="f6b30-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="f6b30-104">El formato del archivo XML se modela después del archivo de configuración de aplicación estándar.</span><span class="sxs-lookup"><span data-stu-id="f6b30-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="f6b30-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="f6b30-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="f6b30-106">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6b30-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="f6b30-107">Vea [cargar Common Language Runtime en un proceso](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span><span class="sxs-lookup"><span data-stu-id="f6b30-107">See [Loading the Common Language Runtime into a Process](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b30-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6b30-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6b30-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6b30-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="f6b30-110">[in] El nombre de un archivo de configuración que especifica la versión de CLR que se debe cargar.</span><span class="sxs-lookup"><span data-stu-id="f6b30-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="f6b30-111">Si el nombre de archivo no está completo, se supone que en el mismo directorio que el ejecutable que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="f6b30-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="f6b30-112">La versión de runtime que se va a cargar se describe mediante el atributo de versión en la [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f6b30-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="f6b30-113">Si no se especifica ninguna versión, o si la `<requiredRuntime>` no se encuentra el elemento, se cargará la versión más reciente de CLR que está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f6b30-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="f6b30-114">[in] El `CLSID` de la coclase que implementa la [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="f6b30-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="f6b30-115">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="f6b30-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="f6b30-116">[in] El `IID` de la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="f6b30-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="f6b30-117">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="f6b30-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="f6b30-118">[out] El puntero de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="f6b30-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b30-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6b30-119">Requirements</span></span>  
 <span data-ttu-id="f6b30-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6b30-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b30-121">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6b30-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6b30-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6b30-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6b30-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b30-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b30-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6b30-124">See Also</span></span>  
 [<span data-ttu-id="f6b30-125">CorBindToRuntime (función)</span><span class="sxs-lookup"><span data-stu-id="f6b30-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="f6b30-126">CorBindToRuntimeByCfg (función)</span><span class="sxs-lookup"><span data-stu-id="f6b30-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="f6b30-127">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="f6b30-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="f6b30-128">CorBindToRuntimeHost (función)</span><span class="sxs-lookup"><span data-stu-id="f6b30-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="f6b30-129">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6b30-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="f6b30-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f6b30-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
