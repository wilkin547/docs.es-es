---
title: IMetaDataAssemblyEmit::SetAssemblyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: 3736e7279056e015b157758b1233cf6dc5aa6d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720209"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="a7e2b-102">IMetaDataAssemblyEmit::SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a7e2b-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>

<span data-ttu-id="a7e2b-103">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="a7e2b-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7e2b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7e2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7e2b-105">Parameters</span></span>  

 `pma`  
 <span data-ttu-id="a7e2b-106">de Token de metadatos que especifica la `Assembly` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="a7e2b-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="a7e2b-107">de Puntero a la clave pública del publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a7e2b-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="a7e2b-108">de Tamaño en bytes de `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="a7e2b-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="a7e2b-109">de Identificador del algoritmo hash usado para aplicar un algoritmo hash a los archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a7e2b-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="a7e2b-110">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a7e2b-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="a7e2b-111">de Puntero al ASSEMBLYMETADATA (que contiene información sobre la versión, la plataforma y la configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a7e2b-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="a7e2b-112">de Combinación bit a bit de valores de [AssemblyFlags (](assemblyflags-enumeration.md) que especifican varios atributos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a7e2b-112">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7e2b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7e2b-113">Remarks</span></span>  

 <span data-ttu-id="a7e2b-114">Para crear una `Assembly` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineassembly](imetadataassemblyemit-defineassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a7e2b-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7e2b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7e2b-115">Requirements</span></span>  

 <span data-ttu-id="a7e2b-116">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7e2b-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e2b-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a7e2b-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7e2b-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7e2b-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7e2b-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e2b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e2b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7e2b-120">See also</span></span>

- [<span data-ttu-id="a7e2b-121">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7e2b-121">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
