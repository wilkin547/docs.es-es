---
description: 'Más información sobre: IMetaDataImport:: GetScopeProps ((método)'
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
ms.openlocfilehash: 2ed7c08cc876f467a46fe38c7c27719e5608e623
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789156"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="42d47-103">IMetaDataImport::GetScopeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="42d47-103">IMetaDataImport::GetScopeProps Method</span></span>

<span data-ttu-id="42d47-104">Obtiene el nombre y, si quiere, el identificador de versión del ensamblado o el módulo en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="42d47-104">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42d47-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42d47-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42d47-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42d47-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="42d47-107">enuncia Búfer del nombre del ensamblado o del módulo.</span><span class="sxs-lookup"><span data-stu-id="42d47-107">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="42d47-108">de Tamaño en caracteres anchos de `szName` .</span><span class="sxs-lookup"><span data-stu-id="42d47-108">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="42d47-109">enuncia Número de caracteres anchos devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="42d47-109">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="42d47-110">[out, opcional] Un puntero a un GUID que identifica de forma única la versión del ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="42d47-110">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42d47-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42d47-111">Remarks</span></span>  

 <span data-ttu-id="42d47-112">El método [IMetaDataEmit:: SetModuleProps (](imetadataemit-setmoduleprops-method.md) se usa para establecer estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="42d47-112">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42d47-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42d47-113">Requirements</span></span>  

 <span data-ttu-id="42d47-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42d47-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="42d47-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42d47-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42d47-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42d47-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42d47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d47-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="42d47-118">See also</span></span>

- [<span data-ttu-id="42d47-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42d47-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="42d47-120">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42d47-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
