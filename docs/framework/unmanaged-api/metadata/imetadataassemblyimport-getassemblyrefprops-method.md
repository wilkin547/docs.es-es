---
description: 'Más información sobre: IMetaDataAssemblyImport:: Getassemblyrefprops ((método)'
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
ms.openlocfilehash: f7011806920ba37ca84b1a48f12da3a5557fa464
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784137"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="1eb75-103">IMetaDataAssemblyImport::GetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="1eb75-103">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>

<span data-ttu-id="1eb75-104">Obtiene el conjunto de propiedades para la referencia de ensamblado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="1eb75-104">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb75-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1eb75-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1eb75-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1eb75-106">Parameters</span></span>  

 `mdar`  
 <span data-ttu-id="1eb75-107">de `mdAssemblyRef` Símbolo (token) de metadatos que representa la referencia del ensamblado para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="1eb75-107">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="1eb75-108">enuncia Puntero a la clave pública o al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="1eb75-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="1eb75-109">enuncia Número de bytes de la clave pública o el token devueltos.</span><span class="sxs-lookup"><span data-stu-id="1eb75-109">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="1eb75-110">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1eb75-110">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1eb75-111">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="1eb75-111">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="1eb75-112">enuncia Puntero al número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="1eb75-112">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="1eb75-113">enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1eb75-113">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="1eb75-114">enuncia Puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="1eb75-114">[out] A pointer to the hash value.</span></span> <span data-ttu-id="1eb75-115">Este es el hash, mediante el algoritmo SHA-1, de la `PublicKey` propiedad del ensamblado al que se hace referencia, a menos que se establezca la marca arfFullOriginator de la enumeración [AssemblyRefFlags (](assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1eb75-115">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="1eb75-116">enuncia Número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="1eb75-116">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="1eb75-117">enuncia Puntero a las marcas que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1eb75-117">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="1eb75-118">El valor de flags es una combinación de uno o más valores de [corassemblyflags (](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1eb75-118">The flags value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1eb75-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1eb75-119">Return Value</span></span>  

 <span data-ttu-id="1eb75-120">Este método devuelve S_OK si se realiza correctamente; de lo contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="1eb75-120">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb75-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1eb75-121">Requirements</span></span>  

 <span data-ttu-id="1eb75-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eb75-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eb75-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1eb75-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1eb75-124">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1eb75-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1eb75-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eb75-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb75-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1eb75-126">See also</span></span>

- [<span data-ttu-id="1eb75-127">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1eb75-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
