---
description: 'Más información sobre: IAssemblyName:: GetProperty (método)'
title: IAssemblyName::GetProperty (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: 66528bb54e1cb4adbba8fa87088065bc40c2ee15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760738"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="765d6-103">IAssemblyName::GetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="765d6-103">IAssemblyName::GetProperty Method</span></span>

<span data-ttu-id="765d6-104">Obtiene un puntero a la propiedad a la que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="765d6-104">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="765d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="765d6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="765d6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="765d6-106">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="765d6-107">de Identificador único de la propiedad solicitada.</span><span class="sxs-lookup"><span data-stu-id="765d6-107">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="765d6-108">enuncia Datos de propiedad devueltos.</span><span class="sxs-lookup"><span data-stu-id="765d6-108">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="765d6-109">[in, out] Tamaño, en bytes, de `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="765d6-109">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="765d6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="765d6-110">Requirements</span></span>  

 <span data-ttu-id="765d6-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="765d6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="765d6-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="765d6-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="765d6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="765d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="765d6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="765d6-114">See also</span></span>

- [<span data-ttu-id="765d6-115">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="765d6-115">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
