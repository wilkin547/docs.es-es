---
title: ICorDebugModule::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30097ff0cd92253897a366a5a18f305eddb06b5b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763519"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="2b821-102">ICorDebugModule::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2b821-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="2b821-103">Obtiene el token para la entrada de tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="2b821-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b821-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b821-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b821-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b821-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="2b821-106">[out] Un puntero a la `mdModule` símbolo (token) que hace referencia a los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="2b821-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b821-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b821-107">Remarks</span></span>  
 <span data-ttu-id="2b821-108">El token se puede pasar a la [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), y [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaces de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2b821-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b821-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b821-109">Requirements</span></span>  
 <span data-ttu-id="2b821-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b821-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b821-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b821-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b821-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b821-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b821-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b821-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b821-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b821-114">See also</span></span>

- [<span data-ttu-id="2b821-115">Metadatos</span><span class="sxs-lookup"><span data-stu-id="2b821-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
