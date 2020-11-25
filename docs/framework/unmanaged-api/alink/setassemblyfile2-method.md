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
ms.openlocfilehash: 131f5d951e524ef48f2cfe1e3e88ef80ac21c452
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703686"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="50417-102">SetAssemblyFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="50417-102">SetAssemblyFile2 Method</span></span>

<span data-ttu-id="50417-103">Establece el nombre y las opciones de un nuevo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50417-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="50417-104">No llame a este método cuando genere módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="50417-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50417-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50417-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="50417-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50417-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="50417-107">Nombre del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="50417-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="50417-108">Interfaz de [interfaz IMetaDataEmit2](../metadata/imetadataemit2-interface.md) para este archivo.</span><span class="sxs-lookup"><span data-stu-id="50417-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="50417-109">Opciones representadas por la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="50417-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="50417-110">Recibe el identificador único para el ensamblado que se está construyendo.</span><span class="sxs-lookup"><span data-stu-id="50417-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50417-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="50417-111">Return Value</span></span>  

 <span data-ttu-id="50417-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="50417-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50417-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50417-113">Requirements</span></span>  

 <span data-ttu-id="50417-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="50417-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50417-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50417-115">See also</span></span>

- [<span data-ttu-id="50417-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50417-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="50417-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50417-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="50417-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="50417-118">ALink API</span></span>](index.md)
