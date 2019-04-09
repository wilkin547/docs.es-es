---
title: CoInitializeEE (Función)
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18f1a4ede1a362860df1271835600e7b867eac00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127769"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="c94a9-102">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="c94a9-102">CoInitializeEE Function</span></span>
<span data-ttu-id="c94a9-103">Garantiza que el motor de ejecución de common language runtime se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="c94a9-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="c94a9-104">Esta función está en desuso en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c94a9-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c94a9-105">Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c94a9-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c94a9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c94a9-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c94a9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c94a9-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="c94a9-108">[in] Uno de los [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="c94a9-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c94a9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c94a9-109">Return Value</span></span>  
 <span data-ttu-id="c94a9-110">Este método devuelve códigos de error COM estándar, tal como se define en Winerror.h y los valores en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c94a9-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="c94a9-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="c94a9-111">Return code</span></span>|<span data-ttu-id="c94a9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c94a9-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c94a9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c94a9-113">S_OK</span></span>|<span data-ttu-id="c94a9-114">El motor de ejecución se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c94a9-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="c94a9-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c94a9-115">S_FALSE</span></span>|<span data-ttu-id="c94a9-116">El motor de ejecución ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="c94a9-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="c94a9-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c94a9-117">E_FAIL</span></span>|<span data-ttu-id="c94a9-118">No se pudo cargar el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c94a9-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c94a9-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c94a9-119">Remarks</span></span>  
 <span data-ttu-id="c94a9-120">Este método carga el motor de ejecución si no se ha cargado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c94a9-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c94a9-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c94a9-121">Requirements</span></span>  
 <span data-ttu-id="c94a9-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c94a9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c94a9-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c94a9-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c94a9-124">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c94a9-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c94a9-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c94a9-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c94a9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c94a9-126">See also</span></span>

- [<span data-ttu-id="c94a9-127">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="c94a9-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
