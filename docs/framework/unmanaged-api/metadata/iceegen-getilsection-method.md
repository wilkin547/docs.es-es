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
ms.openlocfilehash: 7ef944fd06d07dc8c4e49061a5e72d8acc4d0465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436349"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="4ec9a-102">ICeeGen::GetIlSection (Método)</span><span class="sxs-lookup"><span data-stu-id="4ec9a-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="4ec9a-103">Obtiene la sección de la base de código de lenguaje intermedio a la que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="4ec9a-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="4ec9a-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4ec9a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ec9a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ec9a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ec9a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ec9a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="4ec9a-107">de Identificador de la sección que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="4ec9a-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ec9a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ec9a-108">Requirements</span></span>  
 <span data-ttu-id="4ec9a-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ec9a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ec9a-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4ec9a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ec9a-111">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4ec9a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ec9a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ec9a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec9a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ec9a-113">See also</span></span>

- [<span data-ttu-id="4ec9a-114">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ec9a-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
