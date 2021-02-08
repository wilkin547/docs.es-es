---
description: 'Más información sobre: función de coinicializar'
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
ms.openlocfilehash: 9664324c569ed4de73262491cf8eda8296b3c3a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799829"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="8de2d-103">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="8de2d-103">CoInitializeEE Function</span></span>

<span data-ttu-id="8de2d-104">Garantiza que el motor de ejecución de Common Language Runtime se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="8de2d-104">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="8de2d-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8de2d-105">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="8de2d-106">Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8de2d-106">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de2d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8de2d-107">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8de2d-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8de2d-108">Parameters</span></span>  

 `fFlags`  
 <span data-ttu-id="8de2d-109">de Una de las constantes de enumeración [coinitiee (](../metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="8de2d-109">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8de2d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8de2d-110">Return Value</span></span>  

 <span data-ttu-id="8de2d-111">Este método devuelve los códigos de error COM estándar, tal y como se define en Winerror. h, y los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8de2d-111">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="8de2d-112">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="8de2d-112">Return code</span></span>|<span data-ttu-id="8de2d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8de2d-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="8de2d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8de2d-114">S_OK</span></span>|<span data-ttu-id="8de2d-115">El motor de ejecución se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8de2d-115">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="8de2d-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8de2d-116">S_FALSE</span></span>|<span data-ttu-id="8de2d-117">El motor de ejecución ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="8de2d-117">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="8de2d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8de2d-118">E_FAIL</span></span>|<span data-ttu-id="8de2d-119">No se pudo cargar el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8de2d-119">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8de2d-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8de2d-120">Remarks</span></span>  

 <span data-ttu-id="8de2d-121">Este método carga el motor de ejecución si no se ha cargado previamente.</span><span class="sxs-lookup"><span data-stu-id="8de2d-121">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de2d-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8de2d-122">Requirements</span></span>  

 <span data-ttu-id="8de2d-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8de2d-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de2d-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8de2d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8de2d-125">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8de2d-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8de2d-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de2d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de2d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8de2d-127">See also</span></span>

- [<span data-ttu-id="8de2d-128">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="8de2d-128">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
