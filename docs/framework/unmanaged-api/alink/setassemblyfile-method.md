---
description: 'Más información sobre: método Setassemblyfile ('
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
ms.openlocfilehash: 943e0600b9781aeaf45cc26e39bd8a8b33a783c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662499"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="28574-103">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="28574-103">SetAssemblyFile Method</span></span>

<span data-ttu-id="28574-104">Asigna el nombre del ensamblado que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="28574-104">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="28574-105">No se usa al generar módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="28574-105">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28574-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28574-106">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="28574-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28574-107">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="28574-108">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="28574-108">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="28574-109">Puntero a la interfaz de [interfaz IMetaDataEmit](../metadata/imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="28574-109">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="28574-110">Marcas tal y como se definen en la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="28574-110">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="28574-111">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="28574-111">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28574-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28574-112">Return Value</span></span>  

 <span data-ttu-id="28574-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="28574-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28574-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28574-114">Requirements</span></span>  

 <span data-ttu-id="28574-115">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="28574-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28574-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="28574-116">See also</span></span>

- [<span data-ttu-id="28574-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28574-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="28574-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28574-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="28574-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="28574-119">ALink API</span></span>](index.md)
