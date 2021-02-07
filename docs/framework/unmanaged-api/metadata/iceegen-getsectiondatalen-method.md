---
description: 'Más información sobre: ICeeGen:: Getsectiondatalen ((método)'
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
ms.openlocfilehash: 9475112a6f25e9a4c57c4ded6cd11dab9bf352b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721062"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="47509-103">ICeeGen::GetSectionDataLen (Método)</span><span class="sxs-lookup"><span data-stu-id="47509-103">ICeeGen::GetSectionDataLen Method</span></span>

<span data-ttu-id="47509-104">Obtiene la longitud de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="47509-104">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="47509-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="47509-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47509-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47509-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47509-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47509-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="47509-108">de Sección de datos cuya longitud se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="47509-108">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="47509-109">enuncia La longitud devuelta de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="47509-109">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47509-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47509-110">Remarks</span></span>  

 <span data-ttu-id="47509-111">Llame `GetSectionDataLen` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="47509-111">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47509-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47509-112">Requirements</span></span>  

 <span data-ttu-id="47509-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47509-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47509-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="47509-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47509-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47509-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47509-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47509-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47509-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="47509-117">See also</span></span>

- [<span data-ttu-id="47509-118">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47509-118">ICeeGen Interface</span></span>](iceegen-interface.md)
