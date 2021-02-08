---
description: 'Más información sobre: IMetaDataImport:: Isvalidtoken ((método)'
title: IMetaDataImport::IsValidToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: 68589496213c93f81cfbd0992f9b210e03d6f178
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789065"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="ec47f-103">IMetaDataImport::IsValidToken (Método)</span><span class="sxs-lookup"><span data-stu-id="ec47f-103">IMetaDataImport::IsValidToken Method</span></span>

<span data-ttu-id="ec47f-104">Obtiene un valor que indica si el token especificado contiene una referencia válida a un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="ec47f-104">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec47f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec47f-105">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec47f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec47f-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="ec47f-107">de Token para el que se va a comprobar la validez de la referencia.</span><span class="sxs-lookup"><span data-stu-id="ec47f-107">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec47f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec47f-108">Return Value</span></span>  

 <span data-ttu-id="ec47f-109">`true` Si `tk` es un token de metadatos válido dentro del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ec47f-109">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="ec47f-110">En caso contrario, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ec47f-110">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec47f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec47f-111">Requirements</span></span>  

 <span data-ttu-id="ec47f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec47f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec47f-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec47f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec47f-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec47f-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec47f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec47f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec47f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec47f-116">See also</span></span>

- [<span data-ttu-id="ec47f-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec47f-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ec47f-118">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec47f-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
