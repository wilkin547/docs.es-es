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
ms.openlocfilehash: 969d74933e908674225684a2e77d5c4804b86122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615649"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="2806d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="2806d-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="2806d-103">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="2806d-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="2806d-104">Un *depósito* es una colección de datos de error que está relacionada con el mismo defecto de código.</span><span class="sxs-lookup"><span data-stu-id="2806d-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="2806d-105">*Watson* hace referencia a un conjunto de tecnologías para recopilar y analizar los datos asociados a una excepción.</span><span class="sxs-lookup"><span data-stu-id="2806d-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2806d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2806d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2806d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2806d-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="2806d-108">enuncia Puntero a una estructura [bucketparameters (](bucketparameters-structure.md) que contiene los datos de error de la excepción.</span><span class="sxs-lookup"><span data-stu-id="2806d-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2806d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2806d-109">Requirements</span></span>  
 <span data-ttu-id="2806d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2806d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2806d-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2806d-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2806d-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2806d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2806d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2806d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2806d-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2806d-114">See also</span></span>

- [<span data-ttu-id="2806d-115">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2806d-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
