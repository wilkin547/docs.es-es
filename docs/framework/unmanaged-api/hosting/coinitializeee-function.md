---
title: "CoInitializeEE (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoInitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoInitializeEE
helpviewer_keywords: CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ca564830411a9df0d47cc9765958286bbd40f96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="coinitializeee-function"></a><span data-ttu-id="acf9c-102">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="acf9c-102">CoInitializeEE Function</span></span>
<span data-ttu-id="acf9c-103">Garantiza que el motor de ejecución de common language runtime se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="acf9c-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="acf9c-104">Esta función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acf9c-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="acf9c-105">Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="acf9c-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf9c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acf9c-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acf9c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acf9c-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="acf9c-108">[in] Uno de los [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="acf9c-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acf9c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="acf9c-109">Return Value</span></span>  
 <span data-ttu-id="acf9c-110">Este método devuelve los códigos de error COM estándar definidos en Winerror.h y los valores en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="acf9c-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="acf9c-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="acf9c-111">Return code</span></span>|<span data-ttu-id="acf9c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="acf9c-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="acf9c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="acf9c-113">S_OK</span></span>|<span data-ttu-id="acf9c-114">El motor de ejecución se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="acf9c-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="acf9c-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="acf9c-115">S_FALSE</span></span>|<span data-ttu-id="acf9c-116">El motor de ejecución ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="acf9c-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="acf9c-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="acf9c-117">E_FAIL</span></span>|<span data-ttu-id="acf9c-118">No se pudo cargar el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="acf9c-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acf9c-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acf9c-119">Remarks</span></span>  
 <span data-ttu-id="acf9c-120">Este método carga el motor de ejecución si no se ha cargado previamente.</span><span class="sxs-lookup"><span data-stu-id="acf9c-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf9c-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acf9c-121">Requirements</span></span>  
 <span data-ttu-id="acf9c-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf9c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf9c-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="acf9c-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acf9c-124">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acf9c-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="acf9c-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf9c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf9c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="acf9c-126">See Also</span></span>  
 [<span data-ttu-id="acf9c-127">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="acf9c-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
