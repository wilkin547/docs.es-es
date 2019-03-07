---
title: IMetaDataImport::GetParamForMethodIndex (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7455d87caff86c57409f4bb016ec73c365a3d35d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487127"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="8a091-102">IMetaDataImport::GetParamForMethodIndex (Método)</span><span class="sxs-lookup"><span data-stu-id="8a091-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="8a091-103">Obtiene el token que representa un parámetro especificado del método representado por el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="8a091-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a091-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a091-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a091-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a091-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="8a091-106">[in] Un token que representa el método para devolver el token de parámetro para.</span><span class="sxs-lookup"><span data-stu-id="8a091-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="8a091-107">[in] La posición ordinal en la lista de parámetros que se produce el parámetro solicitado.</span><span class="sxs-lookup"><span data-stu-id="8a091-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="8a091-108">Los parámetros se numeran a partir de uno, con el valor devuelto del método en la posición cero.</span><span class="sxs-lookup"><span data-stu-id="8a091-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="8a091-109">[out] Un puntero a un token de ParamDef que representa el parámetro solicitado.</span><span class="sxs-lookup"><span data-stu-id="8a091-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a091-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a091-110">Requirements</span></span>  
 <span data-ttu-id="8a091-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a091-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a091-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a091-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a091-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a091-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a091-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a091-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a091-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a091-115">See also</span></span>
- [<span data-ttu-id="8a091-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a091-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8a091-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a091-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
