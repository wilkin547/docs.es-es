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
ms.openlocfilehash: 707e182e62f4a7b7b813e6b288c6825b0d3d2eab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731762"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="a6388-102">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="a6388-102">CoInitializeEE Function</span></span>

<span data-ttu-id="a6388-103">Garantiza que el motor de ejecución de Common Language Runtime se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="a6388-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="a6388-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a6388-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="a6388-105">Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a6388-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6388-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6388-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6388-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6388-107">Parameters</span></span>  

 `fFlags`  
 <span data-ttu-id="a6388-108">de Una de las constantes de enumeración [coinitiee (](../metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="a6388-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6388-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a6388-109">Return Value</span></span>  

 <span data-ttu-id="a6388-110">Este método devuelve los códigos de error COM estándar, tal y como se define en Winerror. h, y los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a6388-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="a6388-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="a6388-111">Return code</span></span>|<span data-ttu-id="a6388-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6388-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a6388-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6388-113">S_OK</span></span>|<span data-ttu-id="a6388-114">El motor de ejecución se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a6388-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="a6388-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a6388-115">S_FALSE</span></span>|<span data-ttu-id="a6388-116">El motor de ejecución ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="a6388-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="a6388-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a6388-117">E_FAIL</span></span>|<span data-ttu-id="a6388-118">No se pudo cargar el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6388-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6388-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6388-119">Remarks</span></span>  

 <span data-ttu-id="a6388-120">Este método carga el motor de ejecución si no se ha cargado previamente.</span><span class="sxs-lookup"><span data-stu-id="a6388-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6388-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6388-121">Requirements</span></span>  

 <span data-ttu-id="a6388-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6388-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6388-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6388-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6388-124">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6388-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6388-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6388-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6388-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6388-126">See also</span></span>

- [<span data-ttu-id="a6388-127">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="a6388-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
