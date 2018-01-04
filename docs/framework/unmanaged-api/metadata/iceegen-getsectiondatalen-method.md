---
title: "ICeeGen::GetSectionDataLen (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionDataLen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 217a6c87d5152b68e062d9c2a64ec78478f301cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="5fd51-102">ICeeGen::GetSectionDataLen (Método)</span><span class="sxs-lookup"><span data-stu-id="5fd51-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="5fd51-103">Obtiene la longitud de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="5fd51-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="5fd51-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="5fd51-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fd51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fd51-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fd51-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fd51-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="5fd51-107">[in] La sección de datos cuya longitud se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="5fd51-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="5fd51-108">[out] La longitud devuelta de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="5fd51-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fd51-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fd51-109">Remarks</span></span>  
 <span data-ttu-id="5fd51-110">Llame a `GetSectionDataLen` sólo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="5fd51-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fd51-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fd51-111">Requirements</span></span>  
 <span data-ttu-id="5fd51-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fd51-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fd51-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5fd51-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5fd51-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5fd51-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5fd51-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fd51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd51-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fd51-116">See Also</span></span>  
 [<span data-ttu-id="5fd51-117">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fd51-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
