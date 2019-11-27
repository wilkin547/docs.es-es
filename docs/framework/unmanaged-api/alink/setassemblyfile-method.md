---
title: SetAssemblyFile (Método)
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 1db4c4ab7e47e223a492e08297ac3cedcb3a27eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445604"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="d0ee3-102">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="d0ee3-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="d0ee3-103">Asigna el nombre del ensamblado que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="d0ee3-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="d0ee3-104">No se usa al generar módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="d0ee3-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ee3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0ee3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0ee3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0ee3-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="d0ee3-107">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d0ee3-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="d0ee3-108">Puntero a la interfaz de [interfaz IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d0ee3-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="d0ee3-109">Marcas tal y como se definen en la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="d0ee3-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="d0ee3-110">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="d0ee3-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0ee3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0ee3-111">Return Value</span></span>  
 <span data-ttu-id="d0ee3-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="d0ee3-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ee3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0ee3-113">Requirements</span></span>  
 <span data-ttu-id="d0ee3-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="d0ee3-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ee3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0ee3-115">See also</span></span>

- [<span data-ttu-id="d0ee3-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0ee3-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d0ee3-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0ee3-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d0ee3-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d0ee3-118">ALink API</span></span>](index.md)
