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
ms.openlocfilehash: c88b7a401a19b1bd0e02edab7ef7bbee1372199e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432080"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="28c75-102">IMetaDataAssemblyEmit::DefineAssemblyRef (Método)</span><span class="sxs-lookup"><span data-stu-id="28c75-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="28c75-103">Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="28c75-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28c75-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="28c75-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28c75-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="28c75-106">de La clave pública del publicador del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="28c75-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="28c75-107">La función auxiliar [StrongNameTokenFromAssembly (](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) se puede usar para obtener el hash de la clave pública que se va a pasar como este parámetro.</span><span class="sxs-lookup"><span data-stu-id="28c75-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="28c75-108">de Tamaño en bytes de `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="28c75-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="28c75-109">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="28c75-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="28c75-110">Este valor no debe superar los 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="28c75-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="28c75-111">de Instancia de ASSEMBLYMETADATA (que contiene la información de la versión, la plataforma y la configuración regional del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="28c75-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="28c75-112">de Los datos hash asociados al ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="28c75-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="28c75-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="28c75-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="28c75-114">de Tamaño en bytes de `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="28c75-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="28c75-115">de Combinación bit a bit de los valores de [corassemblyflags (](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) que influyen en el comportamiento del motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="28c75-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="28c75-116">enuncia Puntero al token de metadatos de `AssemblyRef` devuelto.</span><span class="sxs-lookup"><span data-stu-id="28c75-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28c75-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28c75-117">Remarks</span></span>  
 <span data-ttu-id="28c75-118">Se debe definir una `AssemblyRef` estructura de metadatos para cada ensamblado al que hace referencia este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="28c75-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="28c75-119">En tiempo de ejecución, los detalles de un ensamblado al que se hace referencia se pasan al solucionador del ensamblado con una indicación de que representan la información "como generada".</span><span class="sxs-lookup"><span data-stu-id="28c75-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="28c75-120">A continuación, la resolución de ensamblado aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="28c75-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28c75-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28c75-121">Requirements</span></span>  
 <span data-ttu-id="28c75-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28c75-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28c75-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="28c75-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28c75-124">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="28c75-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28c75-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28c75-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c75-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="28c75-126">See also</span></span>

- [<span data-ttu-id="28c75-127">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28c75-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
