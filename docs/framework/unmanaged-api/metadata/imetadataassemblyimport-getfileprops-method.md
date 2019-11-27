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
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447214"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="d1ef5-102">IMetaDataAssemblyImport::GetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="d1ef5-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="d1ef5-103">Obtiene las propiedades del archivo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ef5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1ef5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d1ef5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1ef5-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="d1ef5-106">de Símbolo (token) de metadatos de `mdFile` que representa el archivo para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="d1ef5-107">enuncia Nombre simple del archivo.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d1ef5-108">de Tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d1ef5-109">enuncia Número de caracteres anchos realmente devueltos en `szName`.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="d1ef5-110">enuncia Puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="d1ef5-111">Este es el hash, mediante el algoritmo SHA-1, del archivo.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="d1ef5-112">enuncia Número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="d1ef5-113">enuncia Puntero a las marcas que describen los metadatos aplicados a un archivo.</span><span class="sxs-lookup"><span data-stu-id="d1ef5-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="d1ef5-114">El valor de flags es una combinación de uno o más valores de [CorFileFlags (](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d1ef5-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1ef5-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1ef5-115">Requirements</span></span>  
 <span data-ttu-id="d1ef5-116">**Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1ef5-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ef5-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d1ef5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1ef5-118">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d1ef5-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1ef5-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1ef5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ef5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1ef5-120">See also</span></span>

- [<span data-ttu-id="d1ef5-121">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1ef5-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
