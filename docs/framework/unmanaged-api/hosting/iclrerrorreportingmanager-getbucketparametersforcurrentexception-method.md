---
description: 'Más información acerca de: ICLRErrorReportingManager:: Getbucketparametersforcurrentexception ((método)'
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
ms.openlocfilehash: ba2b6cf1215e5d57f608a76a870b0a9c846ee8ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689409"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="b0a92-103">ICLRErrorReportingManager::GetBucketParametersForCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="b0a92-103">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>

<span data-ttu-id="b0a92-104">Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="b0a92-104">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="b0a92-105">Un *depósito* es una colección de datos de error que está relacionada con el mismo defecto de código.</span><span class="sxs-lookup"><span data-stu-id="b0a92-105">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="b0a92-106">*Watson* hace referencia a un conjunto de tecnologías para recopilar y analizar los datos asociados a una excepción.</span><span class="sxs-lookup"><span data-stu-id="b0a92-106">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a92-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0a92-107">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0a92-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0a92-108">Parameters</span></span>  

 `pParams`  
 <span data-ttu-id="b0a92-109">enuncia Puntero a una estructura [bucketparameters (](bucketparameters-structure.md) que contiene los datos de error de la excepción.</span><span class="sxs-lookup"><span data-stu-id="b0a92-109">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a92-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0a92-110">Requirements</span></span>  

 <span data-ttu-id="b0a92-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0a92-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a92-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b0a92-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0a92-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0a92-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0a92-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a92-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a92-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0a92-115">See also</span></span>

- [<span data-ttu-id="b0a92-116">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0a92-116">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
