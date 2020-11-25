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
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708561"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="255ab-102">IMetaDataValidate::ValidatorInit (Método)</span><span class="sxs-lookup"><span data-stu-id="255ab-102">IMetaDataValidate::ValidatorInit Method</span></span>

<span data-ttu-id="255ab-103">Establece una marca que especifica el tipo del módulo en el ámbito de metadatos actual y registra el método de devolución de llamada especificado para los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="255ab-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="255ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="255ab-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="255ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="255ab-105">Parameters</span></span>  

 `dwModule`  
 <span data-ttu-id="255ab-106">de Un valor de la enumeración [corvalidatormoduletype (](corvalidatormoduletype-enumeration.md) que especifica el tipo del módulo en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="255ab-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="255ab-107">de Puntero a una instancia de [IUnknown](/cpp/atl/iunknown) que actúa como devolución de llamada de función para los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="255ab-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="255ab-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="255ab-108">Requirements</span></span>  

 <span data-ttu-id="255ab-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="255ab-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="255ab-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="255ab-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="255ab-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="255ab-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="255ab-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="255ab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="255ab-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="255ab-113">See also</span></span>

- [<span data-ttu-id="255ab-114">IMetaDataValidate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="255ab-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
