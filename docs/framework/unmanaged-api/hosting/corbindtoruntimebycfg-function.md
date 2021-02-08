---
description: 'Más información acerca de: CorBindToRuntimeByCfg (función)'
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
ms.openlocfilehash: c1acf6a8f1d8637bc2d6cd180016ff51cf500107
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790079"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="36950-103">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="36950-103">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="36950-104">Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión que se lee de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="36950-104">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="36950-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="36950-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36950-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36950-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="36950-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36950-107">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="36950-108">de Un puntero a un `IStream` objeto que lee el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="36950-108">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="36950-109">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="36950-109">[in] Reserved for future use.</span></span> <span data-ttu-id="36950-110">Use 0 (cero) como valor.</span><span class="sxs-lookup"><span data-stu-id="36950-110">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="36950-111">de Un valor de la enumeración [STARTUP_FLAGS](startup-flags-enumeration.md) que especifica el comportamiento de inicio de CLR.</span><span class="sxs-lookup"><span data-stu-id="36950-111">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="36950-112">de `CLSID` De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="36950-112">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="36950-113">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="36950-113">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="36950-114">de `IID` De la `ICorRuntimeHost` `ICLRRuntimeHost` interfaz o.</span><span class="sxs-lookup"><span data-stu-id="36950-114">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="36950-115">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="36950-115">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="36950-116">enuncia Puntero a la dirección de la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="36950-116">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36950-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36950-117">Remarks</span></span>  

 <span data-ttu-id="36950-118">El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar.</span><span class="sxs-lookup"><span data-stu-id="36950-118">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="36950-119">Para obtener más información acerca de los archivos XML, vea [esquema del archivo de configuración](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="36950-119">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36950-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36950-120">Requirements</span></span>  

 <span data-ttu-id="36950-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36950-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36950-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="36950-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36950-123">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36950-123">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36950-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36950-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36950-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="36950-125">See also</span></span>

- [<span data-ttu-id="36950-126">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="36950-126">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="36950-127">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="36950-127">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="36950-128">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="36950-128">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="36950-129">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="36950-129">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="36950-130">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36950-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="36950-131">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="36950-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
