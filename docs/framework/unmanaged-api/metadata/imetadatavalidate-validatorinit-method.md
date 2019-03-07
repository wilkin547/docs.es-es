---
title: IMetaDataValidate::ValidatorInit (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d2018be28cbfe72bb7c989634374b8ab43693e6f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491963"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="c3492-102">IMetaDataValidate::ValidatorInit (Método)</span><span class="sxs-lookup"><span data-stu-id="c3492-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="c3492-103">Establece una marca que especifica el tipo del módulo en el ámbito de metadatos actual y registra el método de devolución de llamada especificado para los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="c3492-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3492-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3492-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3492-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3492-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="c3492-106">[in] Un valor de la [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeración que especifica el tipo del módulo en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="c3492-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="c3492-107">[in] Un puntero a un [IUnknown](/cpp/atl/iunknown) instancia que actúa como una devolución de llamada de función para errores de validación.</span><span class="sxs-lookup"><span data-stu-id="c3492-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3492-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3492-108">Requirements</span></span>  
 <span data-ttu-id="c3492-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3492-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3492-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c3492-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3492-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3492-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3492-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3492-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3492-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3492-113">See also</span></span>
- [<span data-ttu-id="c3492-114">IMetaDataValidate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3492-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
