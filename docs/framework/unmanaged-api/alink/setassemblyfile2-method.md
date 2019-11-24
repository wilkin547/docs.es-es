---
title: SetAssemblyFile2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
ms.openlocfilehash: 4f710ef9741869a2b4fd8473ed3ecf379cfcc56d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445589"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="f94eb-102">SetAssemblyFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f94eb-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="f94eb-103">Sets the name of and options for a new assembly.</span><span class="sxs-lookup"><span data-stu-id="f94eb-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="f94eb-104">Do not call this method when you produce unbound modules.</span><span class="sxs-lookup"><span data-stu-id="f94eb-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f94eb-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f94eb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f94eb-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="f94eb-107">Name of manifest file.</span><span class="sxs-lookup"><span data-stu-id="f94eb-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="f94eb-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span><span class="sxs-lookup"><span data-stu-id="f94eb-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="f94eb-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f94eb-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="f94eb-110">Receives unique ID for the assembly being constructed.</span><span class="sxs-lookup"><span data-stu-id="f94eb-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f94eb-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f94eb-111">Return Value</span></span>  
 <span data-ttu-id="f94eb-112">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="f94eb-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f94eb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f94eb-113">Requirements</span></span>  
 <span data-ttu-id="f94eb-114">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="f94eb-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94eb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f94eb-115">See also</span></span>

- [<span data-ttu-id="f94eb-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f94eb-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f94eb-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f94eb-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f94eb-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f94eb-118">ALink API</span></span>](index.md)
