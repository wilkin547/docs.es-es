---
description: 'Más información sobre: IMetaDataImport:: GetUserString ((método)'
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
ms.openlocfilehash: 074d196c74be30f5879410ad44b9bb5c096eb153
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789104"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="08f49-103">IMetaDataImport::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="08f49-103">IMetaDataImport::GetUserString Method</span></span>

<span data-ttu-id="08f49-104">Obtiene la cadena literal representada por el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="08f49-104">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f49-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08f49-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08f49-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08f49-106">Parameters</span></span>  

 `stk`  
 <span data-ttu-id="08f49-107">de Token de cadena para el que se va a devolver la cadena asociada.</span><span class="sxs-lookup"><span data-stu-id="08f49-107">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="08f49-108">enuncia Una copia de la cadena solicitada.</span><span class="sxs-lookup"><span data-stu-id="08f49-108">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="08f49-109">de Tamaño máximo en caracteres anchos de la solicitud solicitada `szString` .</span><span class="sxs-lookup"><span data-stu-id="08f49-109">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="08f49-110">enuncia Tamaño en caracteres anchos del devuelto `szString` .</span><span class="sxs-lookup"><span data-stu-id="08f49-110">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f49-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08f49-111">Requirements</span></span>  

 <span data-ttu-id="08f49-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08f49-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f49-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08f49-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08f49-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08f49-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08f49-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f49-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f49-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="08f49-116">See also</span></span>

- [<span data-ttu-id="08f49-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08f49-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="08f49-118">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08f49-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
