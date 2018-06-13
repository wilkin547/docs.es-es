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
ms.openlocfilehash: 1e557cc0da7bc684843ae3969242ffb84d811c44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405351"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="85376-102">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="85376-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="85376-103">Asigna el nombre del ensamblado que se crea.</span><span class="sxs-lookup"><span data-stu-id="85376-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="85376-104">No para usar al generar módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="85376-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85376-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85376-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85376-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85376-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="85376-107">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="85376-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="85376-108">Puntero a [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="85376-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="85376-109">Marca como se define en [AssemblyFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="85376-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="85376-110">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="85376-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85376-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="85376-111">Return Value</span></span>  
 <span data-ttu-id="85376-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="85376-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85376-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85376-113">Requirements</span></span>  
 <span data-ttu-id="85376-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="85376-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85376-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="85376-115">See Also</span></span>  
 [<span data-ttu-id="85376-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85376-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="85376-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85376-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="85376-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="85376-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
