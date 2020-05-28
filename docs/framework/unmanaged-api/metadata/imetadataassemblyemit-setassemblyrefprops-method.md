---
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
ms.openlocfilehash: fb381a872cbeb787da0c6920f2cdeef434fb33ea
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008097"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="7c628-102">IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7c628-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="7c628-103">Modifica la estructura de metadatos `AssemblyRef` especificada.</span><span class="sxs-lookup"><span data-stu-id="7c628-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c628-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c628-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7c628-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c628-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="7c628-106">de Token de metadatos que especifica la `AssemblyRef` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="7c628-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="7c628-107">de La clave pública del publicador del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7c628-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="7c628-108">de Tamaño en bytes de `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="7c628-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="7c628-109">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7c628-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="7c628-110">de Un puntero a una instancia de ASSEMBLYMETADATA (que contiene la versión, la plataforma y la información de configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7c628-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7c628-111">de Puntero a los datos hash asociados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7c628-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7c628-112">de Tamaño en bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="7c628-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="7c628-113">de Combinación bit a bit de valores de [AssemblyRefFlags (](assemblyrefflags-enumeration.md) que especifican los atributos del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7c628-113">[in] A bitwise combination of [AssemblyRefFlags](assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c628-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c628-114">Remarks</span></span>  
 <span data-ttu-id="7c628-115">Para crear una `AssemblyRef` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineassemblyref](imetadataassemblyemit-defineassemblyref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7c628-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c628-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c628-116">Requirements</span></span>  
 <span data-ttu-id="7c628-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c628-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c628-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7c628-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c628-119">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7c628-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c628-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c628-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c628-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c628-121">See also</span></span>

- [<span data-ttu-id="7c628-122">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c628-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
