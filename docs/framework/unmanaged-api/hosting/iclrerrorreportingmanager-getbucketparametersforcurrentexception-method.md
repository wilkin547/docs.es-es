---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException (Método)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3877f00a22c43ef5f22974b621b32b78ce15d795
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494472"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="40823-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="40823-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="40823-103">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="40823-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="40823-104">Un *depósito* es una colección de datos de error que está relacionado con el mismo defecto de código.</span><span class="sxs-lookup"><span data-stu-id="40823-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="40823-105">*Watson* hace referencia a un conjunto de tecnologías para recopilar y analizar los datos que está asociados con una excepción.</span><span class="sxs-lookup"><span data-stu-id="40823-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40823-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40823-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40823-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40823-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="40823-108">[out] Un puntero a un [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) estructura que contiene datos de error para la excepción.</span><span class="sxs-lookup"><span data-stu-id="40823-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40823-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40823-109">Requirements</span></span>  
 <span data-ttu-id="40823-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40823-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40823-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40823-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40823-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40823-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40823-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40823-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40823-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="40823-114">See also</span></span>
- [<span data-ttu-id="40823-115">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40823-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
