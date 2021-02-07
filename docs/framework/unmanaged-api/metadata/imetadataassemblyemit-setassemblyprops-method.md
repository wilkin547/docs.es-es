---
description: 'Más información acerca de: IMetaDataAssemblyEmit:: SetAssemblyProps ((método)'
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
ms.openlocfilehash: d5dfb5fa472bb83863c8e4909998deeb2b9fc53b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678203"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="74855-103">IMetaDataAssemblyEmit::SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="74855-103">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>

<span data-ttu-id="74855-104">Modifica la estructura de metadatos `Assembly` especificada.</span><span class="sxs-lookup"><span data-stu-id="74855-104">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74855-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74855-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="74855-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74855-106">Parameters</span></span>  

 `pma`  
 <span data-ttu-id="74855-107">de Token de metadatos que especifica la `Assembly` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="74855-107">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="74855-108">de Puntero a la clave pública del publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="74855-108">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="74855-109">de Tamaño en bytes de `pbPublicKey` .</span><span class="sxs-lookup"><span data-stu-id="74855-109">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="74855-110">de Identificador del algoritmo hash usado para aplicar un algoritmo hash a los archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="74855-110">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="74855-111">de Nombre del texto legible del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="74855-111">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="74855-112">de Puntero al ASSEMBLYMETADATA (que contiene información sobre la versión, la plataforma y la configuración regional para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="74855-112">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="74855-113">de Combinación bit a bit de valores de [AssemblyFlags (](assemblyflags-enumeration.md) que especifican varios atributos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="74855-113">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74855-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74855-114">Remarks</span></span>  

 <span data-ttu-id="74855-115">Para crear una `Assembly` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineassembly](imetadataassemblyemit-defineassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="74855-115">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74855-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74855-116">Requirements</span></span>  

 <span data-ttu-id="74855-117">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74855-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74855-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74855-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74855-119">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74855-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74855-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74855-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74855-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="74855-121">See also</span></span>

- [<span data-ttu-id="74855-122">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74855-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
