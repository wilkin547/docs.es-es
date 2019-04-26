---
title: ICeeGen::GetSectionDataLen (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca01f78cf46d4f7543b949c820eb6b1971687e23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905481"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="9a444-102">ICeeGen::GetSectionDataLen (Método)</span><span class="sxs-lookup"><span data-stu-id="9a444-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="9a444-103">Obtiene la longitud de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="9a444-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="9a444-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="9a444-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a444-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a444-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a444-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a444-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9a444-107">[in] La sección de datos cuya longitud se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="9a444-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="9a444-108">[out] La longitud devuelta de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="9a444-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a444-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a444-109">Remarks</span></span>  
 <span data-ttu-id="9a444-110">Llamar a `GetSectionDataLen` sólo si tiene requisitos de sección especial que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="9a444-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a444-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a444-111">Requirements</span></span>  
 <span data-ttu-id="9a444-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a444-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a444-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a444-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a444-114">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a444-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a444-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a444-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a444-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a444-116">See also</span></span>

- [<span data-ttu-id="9a444-117">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a444-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
