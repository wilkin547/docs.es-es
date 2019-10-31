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
ms.openlocfilehash: 9e90772ae8c3e6be5744fcccc9901123df871831
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131942"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="5c5df-102">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="5c5df-102">CoInitializeEE Function</span></span>
<span data-ttu-id="5c5df-103">Garantiza que el motor de ejecución de Common Language Runtime se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="5c5df-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="5c5df-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5c5df-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="5c5df-105">Use en su lugar el método [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c5df-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5df-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c5df-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c5df-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c5df-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="5c5df-108">de Una de las constantes de enumeración [coinitiee (](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="5c5df-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c5df-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5c5df-109">Return Value</span></span>  
 <span data-ttu-id="5c5df-110">Este método devuelve los códigos de error COM estándar, tal y como se define en Winerror. h, y los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c5df-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="5c5df-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="5c5df-111">Return code</span></span>|<span data-ttu-id="5c5df-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c5df-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5c5df-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c5df-113">S_OK</span></span>|<span data-ttu-id="5c5df-114">El motor de ejecución se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5c5df-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="5c5df-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5c5df-115">S_FALSE</span></span>|<span data-ttu-id="5c5df-116">El motor de ejecución ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="5c5df-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="5c5df-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c5df-117">E_FAIL</span></span>|<span data-ttu-id="5c5df-118">No se pudo cargar el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5c5df-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c5df-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c5df-119">Remarks</span></span>  
 <span data-ttu-id="5c5df-120">Este método carga el motor de ejecución si no se ha cargado previamente.</span><span class="sxs-lookup"><span data-stu-id="5c5df-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c5df-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c5df-121">Requirements</span></span>  
 <span data-ttu-id="5c5df-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c5df-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c5df-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c5df-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c5df-124">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c5df-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c5df-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5df-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5df-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c5df-126">See also</span></span>

- [<span data-ttu-id="5c5df-127">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="5c5df-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
