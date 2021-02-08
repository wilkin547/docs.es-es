---
description: 'Más información sobre: IMetaDataValidate:: Validatorinit ((método)'
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
ms.openlocfilehash: 99435eeab542e9cb3bb679ad146b546ce51c8df4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799192"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="f76c4-103">IMetaDataValidate::ValidatorInit (Método)</span><span class="sxs-lookup"><span data-stu-id="f76c4-103">IMetaDataValidate::ValidatorInit Method</span></span>

<span data-ttu-id="f76c4-104">Establece una marca que especifica el tipo del módulo en el ámbito de metadatos actual y registra el método de devolución de llamada especificado para los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="f76c4-104">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f76c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f76c4-105">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f76c4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f76c4-106">Parameters</span></span>  

 `dwModule`  
 <span data-ttu-id="f76c4-107">de Un valor de la enumeración [corvalidatormoduletype (](corvalidatormoduletype-enumeration.md) que especifica el tipo del módulo en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f76c4-107">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="f76c4-108">de Puntero a una instancia de [IUnknown](/cpp/atl/iunknown) que actúa como devolución de llamada de función para los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="f76c4-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f76c4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f76c4-109">Requirements</span></span>  

 <span data-ttu-id="f76c4-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f76c4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f76c4-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f76c4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f76c4-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f76c4-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f76c4-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f76c4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f76c4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f76c4-114">See also</span></span>

- [<span data-ttu-id="f76c4-115">IMetaDataValidate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f76c4-115">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
