---
description: 'Más información sobre: ICeeGen:: GetSectionCreate ((método)'
title: ICeeGen::GetSectionCreate (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 2839d11c927dbf573f213d3ebaa9e6e6d8d5015d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706869"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="5540a-103">ICeeGen::GetSectionCreate (Método)</span><span class="sxs-lookup"><span data-stu-id="5540a-103">ICeeGen::GetSectionCreate Method</span></span>

<span data-ttu-id="5540a-104">Genera y obtiene una sección de código usando el nombre y los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="5540a-104">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="5540a-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="5540a-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5540a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5540a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5540a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5540a-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="5540a-108">de Puntero a una cadena que especifica el nombre de la sección que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="5540a-108">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="5540a-109">de Marcas que especifican las opciones.</span><span class="sxs-lookup"><span data-stu-id="5540a-109">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="5540a-110">enuncia Un puntero a la sección de código que se acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="5540a-110">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5540a-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5540a-111">Remarks</span></span>  

 <span data-ttu-id="5540a-112">Llame `GetSectionCreate` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="5540a-112">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5540a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5540a-113">Requirements</span></span>  

 <span data-ttu-id="5540a-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5540a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5540a-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5540a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5540a-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5540a-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5540a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5540a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5540a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5540a-118">See also</span></span>

- [<span data-ttu-id="5540a-119">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5540a-119">ICeeGen Interface</span></span>](iceegen-interface.md)
