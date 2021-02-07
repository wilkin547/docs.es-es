---
description: 'Más información acerca de: IMetaDataAssemblyEmit:: SetAssemblyRefProps ((método)'
title: IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: 704fff656b705bb246e2742ce991d41fcadcdfcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678177"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="98251-103">IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="98251-103">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>

<span data-ttu-id="98251-104">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="98251-104">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98251-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98251-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,
    [in] const ASSEMBLYMETADATA     *pMetaData,
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98251-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98251-106">Parameters</span></span>  

 `ar`  
 <span data-ttu-id="98251-107">de Token de metadatos que especifica la `AssemblyRef` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="98251-107">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="98251-108">de La clave pública del publicador del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="98251-108">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="98251-109">de Tamaño en bytes de `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="98251-109">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="98251-110">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98251-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="98251-111">de Un puntero a una instancia de ASSEMBLYMETADATA (que contiene la versión, la plataforma y la información de configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98251-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="98251-112">de Puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98251-112">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="98251-113">de Tamaño en bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="98251-113">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="98251-114">de Combinación bit a bit de valores de [AssemblyRefFlags (](assemblyrefflags-enumeration.md) que especifican los atributos del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="98251-114">[in] A bitwise combination of [AssemblyRefFlags](assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98251-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="98251-115">Remarks</span></span>  

 <span data-ttu-id="98251-116">Para crear una `AssemblyRef` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineassemblyref](imetadataassemblyemit-defineassemblyref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="98251-116">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98251-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98251-117">Requirements</span></span>  

 <span data-ttu-id="98251-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98251-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98251-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="98251-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98251-120">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98251-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98251-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98251-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98251-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="98251-122">See also</span></span>

- [<span data-ttu-id="98251-123">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98251-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
