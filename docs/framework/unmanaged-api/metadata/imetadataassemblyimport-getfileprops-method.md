---
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
ms.openlocfilehash: 78c192f10f629a0c1316ae7af7fc774819f4de8f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007486"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="57f11-102">IMetaDataAssemblyImport::GetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="57f11-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="57f11-103">Obtiene las propiedades del archivo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="57f11-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57f11-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="57f11-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57f11-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="57f11-106">de `mdFile`Token de metadatos que representa el archivo para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="57f11-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="57f11-107">enuncia Nombre simple del archivo.</span><span class="sxs-lookup"><span data-stu-id="57f11-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="57f11-108">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="57f11-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="57f11-109">enuncia Número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="57f11-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="57f11-110">enuncia Puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="57f11-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="57f11-111">Este es el hash, mediante el algoritmo SHA-1, del archivo.</span><span class="sxs-lookup"><span data-stu-id="57f11-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="57f11-112">enuncia Número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="57f11-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="57f11-113">enuncia Puntero a las marcas que describen los metadatos aplicados a un archivo.</span><span class="sxs-lookup"><span data-stu-id="57f11-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="57f11-114">El valor de flags es una combinación de uno o más valores de [CorFileFlags (](corfileflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="57f11-114">The flags value is a combination of one or more [CorFileFlags](corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57f11-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57f11-115">Requirements</span></span>  
 <span data-ttu-id="57f11-116">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57f11-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57f11-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="57f11-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57f11-118">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="57f11-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57f11-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57f11-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f11-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57f11-120">See also</span></span>

- [<span data-ttu-id="57f11-121">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57f11-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
