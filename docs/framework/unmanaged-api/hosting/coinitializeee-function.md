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
ms.openlocfilehash: 57508a2df3a49c39d25347f2a3038442c37278da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616767"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="3055f-102">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="3055f-102">CoInitializeEE Function</span></span>
<span data-ttu-id="3055f-103">Garantiza que el motor de ejecución de Common Language Runtime se carga en un proceso.</span><span class="sxs-lookup"><span data-stu-id="3055f-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="3055f-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3055f-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="3055f-105">Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3055f-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3055f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3055f-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3055f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3055f-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="3055f-108">de Una de las constantes de enumeración [coinitiee (](../metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3055f-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3055f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3055f-109">Return Value</span></span>  
 <span data-ttu-id="3055f-110">Este método devuelve los códigos de error COM estándar, tal y como se define en Winerror. h, y los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3055f-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="3055f-111">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="3055f-111">Return code</span></span>|<span data-ttu-id="3055f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3055f-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3055f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3055f-113">S_OK</span></span>|<span data-ttu-id="3055f-114">El motor de ejecución se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3055f-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="3055f-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3055f-115">S_FALSE</span></span>|<span data-ttu-id="3055f-116">El motor de ejecución ya está cargado.</span><span class="sxs-lookup"><span data-stu-id="3055f-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="3055f-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3055f-117">E_FAIL</span></span>|<span data-ttu-id="3055f-118">No se pudo cargar el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3055f-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3055f-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3055f-119">Remarks</span></span>  
 <span data-ttu-id="3055f-120">Este método carga el motor de ejecución si no se ha cargado previamente.</span><span class="sxs-lookup"><span data-stu-id="3055f-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3055f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3055f-121">Requirements</span></span>  
 <span data-ttu-id="3055f-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3055f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3055f-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3055f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3055f-124">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3055f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3055f-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3055f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3055f-126">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3055f-126">See also</span></span>

- [<span data-ttu-id="3055f-127">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="3055f-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
