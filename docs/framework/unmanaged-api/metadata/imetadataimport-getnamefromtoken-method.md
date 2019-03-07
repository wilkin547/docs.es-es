---
title: IMetaDataImport::GetNameFromToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f45c89572362f380997e7d8247b93c0f8629655
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478887"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="3a18e-102">IMetaDataImport::GetNameFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="3a18e-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="3a18e-103">Obtiene el nombre en UTF-8 del objeto al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="3a18e-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="3a18e-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="3a18e-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a18e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a18e-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a18e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a18e-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3a18e-107">[in] El token que representa el objeto para devolver el nombre.</span><span class="sxs-lookup"><span data-stu-id="3a18e-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="3a18e-108">[out] Un puntero al nombre de objeto de UTF-8 en el montón.</span><span class="sxs-lookup"><span data-stu-id="3a18e-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a18e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a18e-109">Remarks</span></span>  
 <span data-ttu-id="3a18e-110">`GetNameFromToken` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="3a18e-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="3a18e-111">Como alternativa, llamar a un método para obtener las propiedades del tipo determinado de token necesario, como `GetFieldProps` para un campo o `GetMethodProps` para un método.</span><span class="sxs-lookup"><span data-stu-id="3a18e-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a18e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a18e-112">Requirements</span></span>  
 <span data-ttu-id="3a18e-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a18e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a18e-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a18e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a18e-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a18e-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a18e-116">**Versiones de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="3a18e-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a18e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a18e-117">See also</span></span>
- [<span data-ttu-id="3a18e-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a18e-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3a18e-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a18e-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
