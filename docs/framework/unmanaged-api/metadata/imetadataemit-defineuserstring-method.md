---
title: IMetaDataEmit::DefineUserString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: aa5d66d2408010d7a7b52ec68a18f667097795ae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450172"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="45a2c-102">IMetaDataEmit::DefineUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="45a2c-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="45a2c-103">Obtiene un símbolo (token) de metadatos para la cadena literal especificada.</span><span class="sxs-lookup"><span data-stu-id="45a2c-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a2c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45a2c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45a2c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45a2c-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="45a2c-106">de Cadena de usuario que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="45a2c-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="45a2c-107">de Recuento de caracteres anchos de `szString`.</span><span class="sxs-lookup"><span data-stu-id="45a2c-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="45a2c-108">enuncia El token de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="45a2c-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a2c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45a2c-109">Requirements</span></span>  
 <span data-ttu-id="45a2c-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a2c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a2c-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45a2c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45a2c-112">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="45a2c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45a2c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a2c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a2c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="45a2c-114">See also</span></span>

- [<span data-ttu-id="45a2c-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a2c-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="45a2c-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a2c-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
