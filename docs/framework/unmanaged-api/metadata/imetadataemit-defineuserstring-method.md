---
description: 'Más información acerca de: IMetaDataEmit::D método efineUserString'
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
ms.openlocfilehash: 0d1c376e3f121d35cb9f6c08d7013a3913a8bd49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784007"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="911b1-103">IMetaDataEmit::DefineUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="911b1-103">IMetaDataEmit::DefineUserString Method</span></span>

<span data-ttu-id="911b1-104">Obtiene un símbolo (token) de metadatos para la cadena literal especificada.</span><span class="sxs-lookup"><span data-stu-id="911b1-104">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="911b1-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="911b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="911b1-106">Parameters</span></span>  

 `szString`  
 <span data-ttu-id="911b1-107">de Cadena de usuario que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="911b1-107">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="911b1-108">de Recuento de caracteres anchos en `szString` .</span><span class="sxs-lookup"><span data-stu-id="911b1-108">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="911b1-109">enuncia El token de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="911b1-109">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="911b1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="911b1-110">Requirements</span></span>  

 <span data-ttu-id="911b1-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="911b1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="911b1-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="911b1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="911b1-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="911b1-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="911b1-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="911b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911b1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="911b1-115">See also</span></span>

- [<span data-ttu-id="911b1-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="911b1-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="911b1-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="911b1-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
