---
title: ICeeGen::GetString (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d8d6a0ebecb4fbb9ba277844710c775d80648e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716822"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="7c7c4-102">ICeeGen::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="7c7c4-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="7c7c4-103">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="7c7c4-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="7c7c4-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="7c7c4-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c7c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c7c4-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c7c4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c7c4-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="7c7c4-107">[in] La dirección virtual relativa de la cadena para devolver.</span><span class="sxs-lookup"><span data-stu-id="7c7c4-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="7c7c4-108">[out] La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="7c7c4-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c7c4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c7c4-109">Requirements</span></span>  
 <span data-ttu-id="7c7c4-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c7c4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c7c4-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c7c4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c7c4-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c7c4-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c7c4-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c7c4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c7c4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c7c4-114">See also</span></span>
- [<span data-ttu-id="7c7c4-115">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c7c4-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
