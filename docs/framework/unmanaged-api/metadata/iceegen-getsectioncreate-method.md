---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 93e96e7804a3b5ecc64e9e50ce700435be83b77a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643369"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="d3649-102">ICeeGen::GetSectionCreate (Método)</span><span class="sxs-lookup"><span data-stu-id="d3649-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="d3649-103">Genera y obtiene una sección de código con el nombre especificado y los valores de marca.</span><span class="sxs-lookup"><span data-stu-id="d3649-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="d3649-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="d3649-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3649-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3649-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3649-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3649-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d3649-107">[in] Un puntero a una cadena que especifica el nombre de la sección que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="d3649-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="d3649-108">[in] Marcadores que especifican opciones.</span><span class="sxs-lookup"><span data-stu-id="d3649-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="d3649-109">[out] Un puntero a la sección de código recién creado.</span><span class="sxs-lookup"><span data-stu-id="d3649-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3649-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3649-110">Remarks</span></span>  
 <span data-ttu-id="d3649-111">Llamar a `GetSectionCreate` sólo si tiene requisitos de sección especial que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="d3649-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3649-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3649-112">Requirements</span></span>  
 <span data-ttu-id="d3649-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3649-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3649-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3649-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3649-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3649-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3649-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3649-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3649-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3649-117">See also</span></span>
- [<span data-ttu-id="d3649-118">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3649-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
