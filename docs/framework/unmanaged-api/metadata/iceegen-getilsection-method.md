---
title: ICeeGen::GetIlSection (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e75f46d73e068c6bdaac6ae01740ecf589c97d42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635915"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="ccdba-102">ICeeGen::GetIlSection (Método)</span><span class="sxs-lookup"><span data-stu-id="ccdba-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="ccdba-103">Obtiene la sección de la base de código de lenguaje intermedio al que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="ccdba-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="ccdba-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="ccdba-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccdba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccdba-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccdba-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccdba-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ccdba-107">[in] El identificador de la sección para obtener.</span><span class="sxs-lookup"><span data-stu-id="ccdba-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccdba-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccdba-108">Requirements</span></span>  
 <span data-ttu-id="ccdba-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccdba-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccdba-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ccdba-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccdba-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccdba-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccdba-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccdba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccdba-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccdba-113">See also</span></span>
- [<span data-ttu-id="ccdba-114">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccdba-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
