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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 358346af540c8b6b7ee1523e763bebbacf8cd2bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777525"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="5230b-102">IMetaDataImport::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="5230b-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="5230b-103">Obtiene la cadena literal representada por el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="5230b-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5230b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5230b-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5230b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5230b-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="5230b-106">[in] El token de cadena para devolver la cadena asociada.</span><span class="sxs-lookup"><span data-stu-id="5230b-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="5230b-107">[out] Una copia de la cadena solicitada.</span><span class="sxs-lookup"><span data-stu-id="5230b-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="5230b-108">[in] El tamaño máximo de caracteres anchos de solicitado `szString`.</span><span class="sxs-lookup"><span data-stu-id="5230b-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="5230b-109">[out] El tamaño en caracteres anchos de devuelto `szString`.</span><span class="sxs-lookup"><span data-stu-id="5230b-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5230b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5230b-110">Requirements</span></span>  
 <span data-ttu-id="5230b-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5230b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5230b-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5230b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5230b-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5230b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5230b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5230b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5230b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5230b-115">See also</span></span>

- [<span data-ttu-id="5230b-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5230b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5230b-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5230b-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
