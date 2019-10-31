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
ms.openlocfilehash: b24f8ed4f5e2c6e0022f5599f2ab8c44a30a561a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129276"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="596e4-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="596e4-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="596e4-103">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="596e4-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="596e4-104">Un *depósito* es una colección de datos de error que está relacionada con el mismo defecto de código.</span><span class="sxs-lookup"><span data-stu-id="596e4-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="596e4-105">*Watson* hace referencia a un conjunto de tecnologías para recopilar y analizar los datos asociados a una excepción.</span><span class="sxs-lookup"><span data-stu-id="596e4-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596e4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="596e4-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="596e4-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="596e4-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="596e4-108">enuncia Puntero a una estructura [bucketparameters (](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) que contiene los datos de error de la excepción.</span><span class="sxs-lookup"><span data-stu-id="596e4-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="596e4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="596e4-109">Requirements</span></span>  
 <span data-ttu-id="596e4-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="596e4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="596e4-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="596e4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="596e4-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="596e4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="596e4-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="596e4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="596e4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="596e4-114">See also</span></span>

- [<span data-ttu-id="596e4-115">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="596e4-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
