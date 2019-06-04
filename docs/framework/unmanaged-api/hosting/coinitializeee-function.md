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
ms.openlocfilehash: 9597b12b0da6df807b2d4eaa42c2035c518b71d9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490629"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="cca83-102">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="cca83-102">CoInitializeEE Function</span></span>
<span data-ttu-id="cca83-103">Garantiza que el motor de ejecución de common language runtime se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="cca83-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="cca83-104">Esta función está en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cca83-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="cca83-105">Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cca83-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca83-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cca83-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cca83-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cca83-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="cca83-108">[in] Uno de los [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="cca83-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cca83-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cca83-109">Return Value</span></span>  
 <span data-ttu-id="cca83-110">Este método devuelve códigos de error COM estándar, tal como se define en Winerror.h y los valores en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cca83-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="cca83-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="cca83-111">Return code</span></span>|<span data-ttu-id="cca83-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cca83-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cca83-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cca83-113">S_OK</span></span>|<span data-ttu-id="cca83-114">El motor de ejecución se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cca83-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="cca83-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="cca83-115">S_FALSE</span></span>|<span data-ttu-id="cca83-116">El motor de ejecución ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="cca83-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="cca83-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cca83-117">E_FAIL</span></span>|<span data-ttu-id="cca83-118">No se pudo cargar el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cca83-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cca83-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cca83-119">Remarks</span></span>  
 <span data-ttu-id="cca83-120">Este método carga el motor de ejecución si no se ha cargado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cca83-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cca83-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cca83-121">Requirements</span></span>  
 <span data-ttu-id="cca83-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cca83-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cca83-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="cca83-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cca83-124">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cca83-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cca83-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cca83-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca83-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca83-126">See also</span></span>

- [<span data-ttu-id="cca83-127">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="cca83-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
