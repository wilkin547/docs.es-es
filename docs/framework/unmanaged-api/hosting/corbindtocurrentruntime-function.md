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
ms.openlocfilehash: 348ca9d157a668dcd180076475f1fe9861197174
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616683"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="e194d-102">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="e194d-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="e194d-103">Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e194d-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="e194d-104">El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar.</span><span class="sxs-lookup"><span data-stu-id="e194d-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="e194d-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="e194d-105">For more information about configuration files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="e194d-106">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e194d-106">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="e194d-107">Vea [cargar Common Language Runtime en un proceso](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e194d-107">See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e194d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e194d-108">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e194d-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e194d-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="e194d-110">de Nombre de un archivo de configuración de la aplicación que especifica la versión de CLR que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="e194d-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="e194d-111">Si el nombre de archivo no es completo, se supone que está en el mismo directorio que el ejecutable que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="e194d-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="e194d-112">La versión del tiempo de ejecución que se va a cargar se describe mediante el atributo version del elemento [ \< requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e194d-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="e194d-113">Si no se especifica ninguna versión o si `<requiredRuntime>` no se encuentra el elemento, se carga la versión más reciente de CLR que está instalada en la máquina.</span><span class="sxs-lookup"><span data-stu-id="e194d-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e194d-114">de `CLSID`De la coclase que implementa la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e194d-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e194d-115">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e194d-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e194d-116">[in] El `IID` de la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="e194d-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="e194d-117">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e194d-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e194d-118">enuncia Puntero de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="e194d-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e194d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e194d-119">Requirements</span></span>  
 <span data-ttu-id="e194d-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e194d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e194d-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e194d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e194d-122">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e194d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e194d-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e194d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e194d-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="e194d-124">See also</span></span>

- [<span data-ttu-id="e194d-125">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="e194d-125">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="e194d-126">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="e194d-126">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="e194d-127">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="e194d-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="e194d-128">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="e194d-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="e194d-129">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e194d-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="e194d-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e194d-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
