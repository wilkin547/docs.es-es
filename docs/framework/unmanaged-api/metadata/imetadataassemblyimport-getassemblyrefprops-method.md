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
ms.openlocfilehash: 25aefff46f7557f89f27d1eccab58c9c70d2d13e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722120"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="b3e71-102">IMetaDataAssemblyImport::GetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b3e71-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>

<span data-ttu-id="b3e71-103">Obtiene el conjunto de propiedades para la referencia de ensamblado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="b3e71-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3e71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3e71-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b3e71-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3e71-105">Parameters</span></span>  

 `mdar`  
 <span data-ttu-id="b3e71-106">de `mdAssemblyRef` Símbolo (token) de metadatos que representa la referencia del ensamblado para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="b3e71-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="b3e71-107">enuncia Puntero a la clave pública o al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b3e71-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="b3e71-108">enuncia Número de bytes de la clave pública o el token devueltos.</span><span class="sxs-lookup"><span data-stu-id="b3e71-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="b3e71-109">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b3e71-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b3e71-110">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="b3e71-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b3e71-111">enuncia Puntero al número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="b3e71-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="b3e71-112">enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b3e71-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="b3e71-113">enuncia Puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="b3e71-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="b3e71-114">Este es el hash, mediante el algoritmo SHA-1, de la `PublicKey` propiedad del ensamblado al que se hace referencia, a menos que se establezca la marca arfFullOriginator de la enumeración [AssemblyRefFlags (](assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b3e71-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="b3e71-115">enuncia Número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="b3e71-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="b3e71-116">enuncia Puntero a las marcas que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b3e71-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="b3e71-117">El valor de flags es una combinación de uno o más valores de [corassemblyflags (](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b3e71-117">The flags value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3e71-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b3e71-118">Return Value</span></span>  

 <span data-ttu-id="b3e71-119">Este método devuelve S_OK si se realiza correctamente; de lo contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="b3e71-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3e71-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3e71-120">Requirements</span></span>  

 <span data-ttu-id="b3e71-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3e71-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3e71-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b3e71-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3e71-123">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3e71-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3e71-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3e71-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e71-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3e71-125">See also</span></span>

- [<span data-ttu-id="b3e71-126">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3e71-126">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
