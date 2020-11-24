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
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673792"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="1d21a-102">CorBindToRuntimeByCfg (Función)</span><span class="sxs-lookup"><span data-stu-id="1d21a-102">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="1d21a-103">Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión que se lee de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="1d21a-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="1d21a-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1d21a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d21a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d21a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1d21a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d21a-106">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="1d21a-107">de Un puntero a un `IStream` objeto que lee el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="1d21a-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="1d21a-108">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="1d21a-108">[in] Reserved for future use.</span></span> <span data-ttu-id="1d21a-109">Use 0 (cero) como valor.</span><span class="sxs-lookup"><span data-stu-id="1d21a-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="1d21a-110">de Un valor de la enumeración [STARTUP_FLAGS](startup-flags-enumeration.md) que especifica el comportamiento de inicio de CLR.</span><span class="sxs-lookup"><span data-stu-id="1d21a-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="1d21a-111">de `CLSID` De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1d21a-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="1d21a-112">Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="1d21a-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="1d21a-113">de `IID` De la `ICorRuntimeHost` `ICLRRuntimeHost` interfaz o.</span><span class="sxs-lookup"><span data-stu-id="1d21a-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="1d21a-114">Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="1d21a-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="1d21a-115">enuncia Puntero a la dirección de la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="1d21a-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d21a-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1d21a-116">Remarks</span></span>  

 <span data-ttu-id="1d21a-117">El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar.</span><span class="sxs-lookup"><span data-stu-id="1d21a-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="1d21a-118">Para obtener más información acerca de los archivos XML, vea [esquema del archivo de configuración](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="1d21a-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d21a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d21a-119">Requirements</span></span>  

 <span data-ttu-id="1d21a-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d21a-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d21a-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1d21a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d21a-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d21a-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d21a-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d21a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d21a-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d21a-124">See also</span></span>

- [<span data-ttu-id="1d21a-125">CorBindToCurrentRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="1d21a-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="1d21a-126">CorBindToRuntime (Función)</span><span class="sxs-lookup"><span data-stu-id="1d21a-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="1d21a-127">CorBindToRuntimeEx (Función)</span><span class="sxs-lookup"><span data-stu-id="1d21a-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="1d21a-128">CorBindToRuntimeHost (Función)</span><span class="sxs-lookup"><span data-stu-id="1d21a-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="1d21a-129">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d21a-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="1d21a-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="1d21a-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
