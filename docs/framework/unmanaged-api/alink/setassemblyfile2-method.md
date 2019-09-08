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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aba11ccd61b65d2a779b39db8e0e082cf4d4015b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787216"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="4e3be-102">SetAssemblyFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="4e3be-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="4e3be-103">Establece el nombre y las opciones de un nuevo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4e3be-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="4e3be-104">No llame a este método cuando genere módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="4e3be-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3be-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e3be-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e3be-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e3be-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4e3be-107">Nombre del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="4e3be-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="4e3be-108">Interfaz de [interfaz IMetaDataEmit2](../metadata/imetadataemit2-interface.md) para este archivo.</span><span class="sxs-lookup"><span data-stu-id="4e3be-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="4e3be-109">Opciones representadas por la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4e3be-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="4e3be-110">Recibe el identificador único para el ensamblado que se está construyendo.</span><span class="sxs-lookup"><span data-stu-id="4e3be-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e3be-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e3be-111">Return Value</span></span>  
 <span data-ttu-id="4e3be-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e3be-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e3be-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e3be-113">Requirements</span></span>  
 <span data-ttu-id="4e3be-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="4e3be-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3be-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e3be-115">See also</span></span>

- [<span data-ttu-id="4e3be-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e3be-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4e3be-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e3be-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4e3be-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="4e3be-118">ALink API</span></span>](index.md)
