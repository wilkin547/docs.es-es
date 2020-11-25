---
title: IMetaDataImport::GetRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: b4e7209c357f21a3f0de5770b483b673d5a5570b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729218"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="d4d3d-102">IMetaDataImport::GetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="d4d3d-102">IMetaDataImport::GetRVA Method</span></span>

<span data-ttu-id="d4d3d-103">Obtiene la dirección virtual relativa (RVA) y las marcas de implementación del método o campo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4d3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4d3d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4d3d-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="d4d3d-106">de Símbolo (token) de metadatos de MethodDef o FieldDef que representa el objeto de código para el que se va a devolver la RVA.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="d4d3d-107">Si el token es FieldDef, el campo debe ser una variable global.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="d4d3d-108">enuncia Un puntero a la dirección virtual relativa del objeto de código representado por el token.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="d4d3d-109">enuncia Puntero a las marcas de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="d4d3d-110">Este valor es una máscara de máscara de la enumeración [CorMethodImpl (](cormethodimpl-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d4d3d-110">This value is a bitmask from the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="d4d3d-111">El valor de `pdwImplFlags` solo es válido si `tk` es un token de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4d3d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4d3d-112">Requirements</span></span>  

 <span data-ttu-id="d4d3d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4d3d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4d3d-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d4d3d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4d3d-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4d3d-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4d3d-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4d3d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d3d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4d3d-117">See also</span></span>

- [<span data-ttu-id="d4d3d-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4d3d-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d4d3d-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4d3d-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
