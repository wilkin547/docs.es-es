---
title: IMetaDataImport::GetUserString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
ms.openlocfilehash: af3de5454ce3d4a763c216de6e8efdb39407457b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729140"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="239b5-102">IMetaDataImport::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="239b5-102">IMetaDataImport::GetUserString Method</span></span>

<span data-ttu-id="239b5-103">Obtiene la cadena literal representada por el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="239b5-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="239b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="239b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="239b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="239b5-105">Parameters</span></span>  

 `stk`  
 <span data-ttu-id="239b5-106">de Token de cadena para el que se va a devolver la cadena asociada.</span><span class="sxs-lookup"><span data-stu-id="239b5-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="239b5-107">enuncia Una copia de la cadena solicitada.</span><span class="sxs-lookup"><span data-stu-id="239b5-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="239b5-108">de Tamaño máximo en caracteres anchos de la solicitud solicitada `szString` .</span><span class="sxs-lookup"><span data-stu-id="239b5-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="239b5-109">enuncia Tamaño en caracteres anchos del devuelto `szString` .</span><span class="sxs-lookup"><span data-stu-id="239b5-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="239b5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="239b5-110">Requirements</span></span>  

 <span data-ttu-id="239b5-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="239b5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="239b5-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="239b5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="239b5-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="239b5-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="239b5-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="239b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="239b5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="239b5-115">See also</span></span>

- [<span data-ttu-id="239b5-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="239b5-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="239b5-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="239b5-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
