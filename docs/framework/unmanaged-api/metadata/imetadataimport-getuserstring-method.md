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
ms.openlocfilehash: 690abec6104f6eed1ad5a0eae9a6b6bb18d35b0d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436687"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="bf25e-102">IMetaDataImport::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="bf25e-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="bf25e-103">Obtiene la cadena literal representada por el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="bf25e-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf25e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf25e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf25e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf25e-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="bf25e-106">de Token de cadena para el que se va a devolver la cadena asociada.</span><span class="sxs-lookup"><span data-stu-id="bf25e-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="bf25e-107">enuncia Una copia de la cadena solicitada.</span><span class="sxs-lookup"><span data-stu-id="bf25e-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="bf25e-108">de Tamaño máximo en caracteres anchos de la `szString`solicitada.</span><span class="sxs-lookup"><span data-stu-id="bf25e-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="bf25e-109">enuncia Tamaño en caracteres anchos del `szString`devuelto.</span><span class="sxs-lookup"><span data-stu-id="bf25e-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf25e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf25e-110">Requirements</span></span>  
 <span data-ttu-id="bf25e-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf25e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf25e-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bf25e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf25e-113">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf25e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf25e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf25e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf25e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf25e-115">See also</span></span>

- [<span data-ttu-id="bf25e-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf25e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bf25e-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf25e-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
