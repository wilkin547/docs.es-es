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
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732650"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="84068-102">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="84068-102">SetAssemblyFile Method</span></span>

<span data-ttu-id="84068-103">Asigna el nombre del ensamblado que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="84068-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="84068-104">No se usa al generar módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="84068-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84068-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84068-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="84068-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84068-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="84068-107">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="84068-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="84068-108">Puntero a la interfaz de [interfaz IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="84068-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="84068-109">Marcas tal y como se definen en la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="84068-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="84068-110">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="84068-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84068-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84068-111">Return Value</span></span>  

 <span data-ttu-id="84068-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="84068-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84068-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84068-113">Requirements</span></span>  

 <span data-ttu-id="84068-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="84068-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84068-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84068-115">See also</span></span>

- [<span data-ttu-id="84068-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84068-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="84068-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84068-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="84068-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="84068-118">ALink API</span></span>](index.md)
