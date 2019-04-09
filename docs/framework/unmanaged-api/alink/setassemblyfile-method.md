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
ms.openlocfilehash: a19762cbec91871d7af617957896e4ee34944fba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132721"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="46ca7-102">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="46ca7-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="46ca7-103">Asigna el nombre del ensamblado que se crea.</span><span class="sxs-lookup"><span data-stu-id="46ca7-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="46ca7-104">No para su uso cuando se producen los módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="46ca7-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ca7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46ca7-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="46ca7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46ca7-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="46ca7-107">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="46ca7-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="46ca7-108">Puntero a [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="46ca7-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="46ca7-109">Marcadores definidos en [AssemblyFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="46ca7-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="46ca7-110">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="46ca7-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46ca7-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="46ca7-111">Return Value</span></span>  
 <span data-ttu-id="46ca7-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="46ca7-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46ca7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46ca7-113">Requirements</span></span>  
 <span data-ttu-id="46ca7-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="46ca7-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ca7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="46ca7-115">See also</span></span>

- [<span data-ttu-id="46ca7-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46ca7-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="46ca7-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46ca7-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="46ca7-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="46ca7-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
