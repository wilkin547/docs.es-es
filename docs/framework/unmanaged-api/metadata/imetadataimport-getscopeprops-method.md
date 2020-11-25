---
title: IMetaDataImport::GetScopeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 5a89d1406daa9a2416a708b63d88fd9005234015
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729205"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="5c611-102">IMetaDataImport::GetScopeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5c611-102">IMetaDataImport::GetScopeProps Method</span></span>

<span data-ttu-id="5c611-103">Obtiene el nombre y, si quiere, el identificador de versión del ensamblado o el módulo en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="5c611-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c611-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c611-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c611-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c611-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="5c611-106">enuncia Búfer del nombre del ensamblado o del módulo.</span><span class="sxs-lookup"><span data-stu-id="5c611-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5c611-107">de Tamaño en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="5c611-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5c611-108">enuncia Número de caracteres anchos devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="5c611-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="5c611-109">[out, opcional] Un puntero a un GUID que identifica de forma única la versión del ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="5c611-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c611-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c611-110">Remarks</span></span>  

 <span data-ttu-id="5c611-111">El método [IMetaDataEmit:: SetModuleProps (](imetadataemit-setmoduleprops-method.md) se usa para establecer estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="5c611-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c611-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c611-112">Requirements</span></span>  

 <span data-ttu-id="5c611-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c611-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c611-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c611-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c611-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c611-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c611-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c611-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c611-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c611-117">See also</span></span>

- [<span data-ttu-id="5c611-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c611-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5c611-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c611-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
