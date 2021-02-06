---
description: 'Más información sobre: método Setassemblyfile2 ('
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
ms.openlocfilehash: 890646b718c211b476d013daf021f8889198c1ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662408"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="29906-103">SetAssemblyFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="29906-103">SetAssemblyFile2 Method</span></span>

<span data-ttu-id="29906-104">Establece el nombre y las opciones de un nuevo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="29906-104">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="29906-105">No llame a este método cuando genere módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="29906-105">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29906-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29906-106">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="29906-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29906-107">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="29906-108">Nombre del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="29906-108">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="29906-109">Interfaz de [interfaz IMetaDataEmit2](../metadata/imetadataemit2-interface.md) para este archivo.</span><span class="sxs-lookup"><span data-stu-id="29906-109">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="29906-110">Opciones representadas por la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="29906-110">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="29906-111">Recibe el identificador único para el ensamblado que se está construyendo.</span><span class="sxs-lookup"><span data-stu-id="29906-111">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29906-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="29906-112">Return Value</span></span>  

 <span data-ttu-id="29906-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="29906-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29906-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29906-114">Requirements</span></span>  

 <span data-ttu-id="29906-115">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="29906-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29906-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="29906-116">See also</span></span>

- [<span data-ttu-id="29906-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29906-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="29906-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29906-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="29906-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="29906-119">ALink API</span></span>](index.md)
