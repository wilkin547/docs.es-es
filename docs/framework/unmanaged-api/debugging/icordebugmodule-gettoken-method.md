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
ms.openlocfilehash: 6ffc74247a4ecafcc3744923c0def99220b5ca6f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709887"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="667e5-102">ICorDebugModule::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="667e5-102">ICorDebugModule::GetToken Method</span></span>

<span data-ttu-id="667e5-103">Obtiene el token para la entrada de la tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="667e5-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="667e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="667e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="667e5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="667e5-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="667e5-106">enuncia Puntero al `mdModule` token que hace referencia a los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="667e5-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="667e5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="667e5-107">Remarks</span></span>  

 <span data-ttu-id="667e5-108">El token se puede pasar a las interfaces de importación de metadatos [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)y [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="667e5-108">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="667e5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="667e5-109">Requirements</span></span>  

 <span data-ttu-id="667e5-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="667e5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="667e5-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="667e5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="667e5-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="667e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="667e5-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="667e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667e5-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="667e5-114">See also</span></span>

- [<span data-ttu-id="667e5-115">Metadata</span><span class="sxs-lookup"><span data-stu-id="667e5-115">Metadata</span></span>](../metadata/index.md)
