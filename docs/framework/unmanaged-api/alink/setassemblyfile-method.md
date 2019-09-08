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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76d341aca7c96e5932a1fc155ccaee17ce6585da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777003"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="2d85c-102">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="2d85c-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="2d85c-103">Asigna el nombre del ensamblado que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="2d85c-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="2d85c-104">No se usa al generar módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="2d85c-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d85c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d85c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d85c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d85c-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="2d85c-107">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="2d85c-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="2d85c-108">Puntero a la interfaz de [interfaz IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2d85c-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="2d85c-109">Marcas tal y como se definen en la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="2d85c-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="2d85c-110">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="2d85c-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d85c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d85c-111">Return Value</span></span>  
 <span data-ttu-id="2d85c-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d85c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d85c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d85c-113">Requirements</span></span>  
 <span data-ttu-id="2d85c-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="2d85c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d85c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d85c-115">See also</span></span>

- [<span data-ttu-id="2d85c-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d85c-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2d85c-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d85c-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2d85c-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="2d85c-118">ALink API</span></span>](index.md)
