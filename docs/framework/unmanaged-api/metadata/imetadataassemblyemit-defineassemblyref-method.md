---
title: IMetaDataAssemblyEmit::DefineAssemblyRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: 612463bca18c23fac0b086adde2d208a0fbc5ae5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008175"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="d32cf-102">IMetaDataAssemblyEmit::DefineAssemblyRef (Método)</span><span class="sxs-lookup"><span data-stu-id="d32cf-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="d32cf-103">Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="d32cf-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d32cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d32cf-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d32cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d32cf-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="d32cf-106">de La clave pública del publicador del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d32cf-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="d32cf-107">La función auxiliar [StrongNameTokenFromAssembly (](../strong-naming/strongnametokenfromassembly-function.md) se puede usar para obtener el hash de la clave pública que se va a pasar como este parámetro.</span><span class="sxs-lookup"><span data-stu-id="d32cf-107">The helper function [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="d32cf-108">de Tamaño en bytes de `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="d32cf-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="d32cf-109">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d32cf-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="d32cf-110">Este valor no debe superar los 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d32cf-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d32cf-111">de Instancia de ASSEMBLYMETADATA (que contiene la información de la versión, la plataforma y la configuración regional del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d32cf-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d32cf-112">de Los datos hash asociados al ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d32cf-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="d32cf-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d32cf-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d32cf-114">de Tamaño en bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="d32cf-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="d32cf-115">de Combinación bit a bit de los valores de [corassemblyflags (](corassemblyflags-enumeration.md) que influyen en el comportamiento del motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d32cf-115">[in] A bitwise combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="d32cf-116">enuncia Puntero al `AssemblyRef` token de metadatos devuelto.</span><span class="sxs-lookup"><span data-stu-id="d32cf-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d32cf-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d32cf-117">Remarks</span></span>  
 <span data-ttu-id="d32cf-118">`AssemblyRef`Se debe definir una estructura de metadatos para cada ensamblado al que haga referencia este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d32cf-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="d32cf-119">En tiempo de ejecución, los detalles de un ensamblado al que se hace referencia se pasan al solucionador del ensamblado con una indicación de que representan la información "como generada".</span><span class="sxs-lookup"><span data-stu-id="d32cf-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="d32cf-120">A continuación, la resolución de ensamblado aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="d32cf-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d32cf-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d32cf-121">Requirements</span></span>  
 <span data-ttu-id="d32cf-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d32cf-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d32cf-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d32cf-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d32cf-124">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d32cf-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d32cf-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d32cf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32cf-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d32cf-126">See also</span></span>

- [<span data-ttu-id="d32cf-127">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d32cf-127">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
