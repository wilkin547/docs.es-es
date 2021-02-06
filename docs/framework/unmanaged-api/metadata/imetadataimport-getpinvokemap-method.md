---
description: 'Más información sobre: IMetaDataImport:: Getpinvokemap ((método)'
title: IMetaDataImport::GetPinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: fcf45f4741709423aa48dcf895dfc4be276e19fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649447"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="5a0cc-103">IMetaDataImport::GetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="5a0cc-103">IMetaDataImport::GetPinvokeMap Method</span></span>

<span data-ttu-id="5a0cc-104">Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="5a0cc-104">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a0cc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a0cc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a0cc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a0cc-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="5a0cc-107">de Un token de FieldDef o MethodDef para el que obtener los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="5a0cc-107">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="5a0cc-108">enuncia Puntero a las marcas que se usan para la asignación.</span><span class="sxs-lookup"><span data-stu-id="5a0cc-108">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="5a0cc-109">Este valor es una máscara de máscara de la enumeración [CorPinvokeMap (](corpinvokemap-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="5a0cc-109">This value is a bitmask from the [CorPinvokeMap](corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="5a0cc-110">enuncia Nombre de la DLL de destino no administrada.</span><span class="sxs-lookup"><span data-stu-id="5a0cc-110">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="5a0cc-111">de Tamaño en caracteres anchos de `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="5a0cc-111">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="5a0cc-112">enuncia Número de caracteres anchos devueltos en `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="5a0cc-112">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="5a0cc-113">enuncia Un puntero a un token ModuleRef que representa la biblioteca de objetos de destino no administrada.</span><span class="sxs-lookup"><span data-stu-id="5a0cc-113">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a0cc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a0cc-114">Requirements</span></span>  

 <span data-ttu-id="5a0cc-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a0cc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a0cc-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5a0cc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a0cc-117">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a0cc-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a0cc-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a0cc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0cc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a0cc-119">See also</span></span>

- [<span data-ttu-id="5a0cc-120">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a0cc-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5a0cc-121">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a0cc-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
