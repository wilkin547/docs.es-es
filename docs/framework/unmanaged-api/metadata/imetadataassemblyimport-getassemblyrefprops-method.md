---
title: IMetaDataAssemblyImport::GetAssemblyRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 2858e924ab6effe192955ce53dad9d333d2d244d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009072"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="2ec0f-102">IMetaDataAssemblyImport::GetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="2ec0f-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="2ec0f-103">Obtiene el conjunto de propiedades para la referencia de ensamblado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec0f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ec0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ec0f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ec0f-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="2ec0f-106">de `mdAssemblyRef`Símbolo (token) de metadatos que representa la referencia del ensamblado para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="2ec0f-107">enuncia Puntero a la clave pública o al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="2ec0f-108">enuncia Número de bytes de la clave pública o el token devueltos.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="2ec0f-109">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2ec0f-110">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="2ec0f-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2ec0f-111">enuncia Puntero al número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="2ec0f-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="2ec0f-112">enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="2ec0f-113">enuncia Puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="2ec0f-114">Este es el hash, mediante el algoritmo SHA-1, de la `PublicKey` propiedad del ensamblado al que se hace referencia, a menos que se establezca la marca arfFullOriginator de la enumeración [AssemblyRefFlags (](assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2ec0f-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="2ec0f-115">enuncia Número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="2ec0f-116">enuncia Puntero a las marcas que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="2ec0f-117">El valor de flags es una combinación de uno o más valores de [corassemblyflags (](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2ec0f-117">The flags value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ec0f-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2ec0f-118">Return Value</span></span>  
 <span data-ttu-id="2ec0f-119">Este método devuelve S_OK si se realiza correctamente; de lo contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="2ec0f-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ec0f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ec0f-120">Requirements</span></span>  
 <span data-ttu-id="2ec0f-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ec0f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ec0f-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2ec0f-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ec0f-123">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ec0f-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ec0f-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ec0f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec0f-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ec0f-125">See also</span></span>

- [<span data-ttu-id="2ec0f-126">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ec0f-126">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
