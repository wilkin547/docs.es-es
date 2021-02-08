---
description: 'Más información sobre: IMetaDataAssemblyImport:: GetFileProps ((método)'
title: IMetaDataAssemblyImport::GetFileProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 6814fee7edf5478a1ce2cf2b81d8f16fa62cd3f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784111"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="5fa99-103">IMetaDataAssemblyImport::GetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5fa99-103">IMetaDataAssemblyImport::GetFileProps Method</span></span>

<span data-ttu-id="5fa99-104">Obtiene las propiedades del archivo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="5fa99-104">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa99-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fa99-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa99-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fa99-106">Parameters</span></span>  

 `mdf`  
 <span data-ttu-id="5fa99-107">de `mdFile` Token de metadatos que representa el archivo para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="5fa99-107">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="5fa99-108">enuncia Nombre simple del archivo.</span><span class="sxs-lookup"><span data-stu-id="5fa99-108">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5fa99-109">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="5fa99-109">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5fa99-110">enuncia Número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="5fa99-110">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="5fa99-111">enuncia Puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="5fa99-111">[out] A pointer to the hash value.</span></span> <span data-ttu-id="5fa99-112">Este es el hash, mediante el algoritmo SHA-1, del archivo.</span><span class="sxs-lookup"><span data-stu-id="5fa99-112">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="5fa99-113">enuncia Número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="5fa99-113">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="5fa99-114">enuncia Puntero a las marcas que describen los metadatos aplicados a un archivo.</span><span class="sxs-lookup"><span data-stu-id="5fa99-114">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="5fa99-115">El valor de flags es una combinación de uno o más valores de [CorFileFlags (](corfileflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="5fa99-115">The flags value is a combination of one or more [CorFileFlags](corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa99-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fa99-116">Requirements</span></span>  

 <span data-ttu-id="5fa99-117">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa99-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa99-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5fa99-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5fa99-119">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5fa99-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5fa99-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa99-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa99-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fa99-121">See also</span></span>

- [<span data-ttu-id="5fa99-122">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fa99-122">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
