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
ms.openlocfilehash: 006360203518f74adb964634af52505a71d51473
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587104"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="47569-102">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="47569-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="47569-103">Asigna el nombre del ensamblado que se crea.</span><span class="sxs-lookup"><span data-stu-id="47569-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="47569-104">No para su uso cuando se producen los módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="47569-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47569-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47569-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47569-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47569-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="47569-107">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="47569-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="47569-108">Puntero a [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="47569-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="47569-109">Marcadores definidos en [AssemblyFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="47569-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="47569-110">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="47569-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47569-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47569-111">Return Value</span></span>  
 <span data-ttu-id="47569-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="47569-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47569-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47569-113">Requirements</span></span>  
 <span data-ttu-id="47569-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="47569-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47569-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="47569-115">See also</span></span>
- [<span data-ttu-id="47569-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47569-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="47569-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47569-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="47569-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="47569-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
