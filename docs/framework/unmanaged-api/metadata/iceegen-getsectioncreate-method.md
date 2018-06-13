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
ms.openlocfilehash: 857462c380ce51994e13dab5cfe3c28bba0f38be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443344"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="e9364-102">ICeeGen::GetSectionCreate (Método)</span><span class="sxs-lookup"><span data-stu-id="e9364-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="e9364-103">Genera y obtiene una sección de código usando el nombre especificado y los valores de marca.</span><span class="sxs-lookup"><span data-stu-id="e9364-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="e9364-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e9364-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9364-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9364-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9364-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9364-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e9364-107">[in] Un puntero a una cadena que especifica el nombre de la sección que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="e9364-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="e9364-108">[in] Marcas que especifican opciones.</span><span class="sxs-lookup"><span data-stu-id="e9364-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="e9364-109">[out] Un puntero a la sección de código recién creado.</span><span class="sxs-lookup"><span data-stu-id="e9364-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9364-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9364-110">Remarks</span></span>  
 <span data-ttu-id="e9364-111">Llame a `GetSectionCreate` sólo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="e9364-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9364-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9364-112">Requirements</span></span>  
 <span data-ttu-id="e9364-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9364-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9364-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9364-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9364-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9364-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9364-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9364-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9364-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9364-117">See Also</span></span>  
 [<span data-ttu-id="e9364-118">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9364-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
