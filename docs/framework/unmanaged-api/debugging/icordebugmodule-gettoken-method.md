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
ms.openlocfilehash: 1cf4d82200709971201da60d06d0cb929641a104
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501890"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="25cf7-102">ICorDebugModule::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="25cf7-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="25cf7-103">Obtiene el token para la entrada de la tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="25cf7-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25cf7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25cf7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25cf7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25cf7-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="25cf7-106">enuncia Puntero al `mdModule` token que hace referencia a los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="25cf7-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25cf7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25cf7-107">Remarks</span></span>  
 <span data-ttu-id="25cf7-108">El token se puede pasar a las interfaces de importación de metadatos [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)y [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="25cf7-108">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25cf7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25cf7-109">Requirements</span></span>  
 <span data-ttu-id="25cf7-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25cf7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25cf7-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25cf7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25cf7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25cf7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25cf7-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25cf7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cf7-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="25cf7-114">See also</span></span>

- [<span data-ttu-id="25cf7-115">Metadata</span><span class="sxs-lookup"><span data-stu-id="25cf7-115">Metadata</span></span>](../metadata/index.md)
