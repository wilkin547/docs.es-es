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
ms.openlocfilehash: 1855c73849c35bf709b0af261a88e6cd7a40abfb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008305"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="ea381-102">ICeeGen::GetSectionDataLen (Método)</span><span class="sxs-lookup"><span data-stu-id="ea381-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="ea381-103">Obtiene la longitud de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="ea381-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="ea381-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="ea381-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea381-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea381-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea381-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea381-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ea381-107">de Sección de datos cuya longitud se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="ea381-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="ea381-108">enuncia La longitud devuelta de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="ea381-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea381-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea381-109">Remarks</span></span>  
 <span data-ttu-id="ea381-110">Llame `GetSectionDataLen` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="ea381-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea381-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea381-111">Requirements</span></span>  
 <span data-ttu-id="ea381-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea381-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea381-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ea381-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea381-114">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ea381-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea381-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea381-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea381-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea381-116">See also</span></span>

- [<span data-ttu-id="ea381-117">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea381-117">ICeeGen Interface</span></span>](iceegen-interface.md)
