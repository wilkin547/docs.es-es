---
title: ImportTypes (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92dfc2bec33501a5cd9ca6b4ec4c3629b6d89946
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487959"
---
# <a name="importtypes-method"></a><span data-ttu-id="1dd30-102">ImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="1dd30-102">ImportTypes Method</span></span>
<span data-ttu-id="1dd30-103">Inicia la importación de los tipos de cada ámbito importado a través de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="1dd30-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dd30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dd30-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dd30-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1dd30-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1dd30-106">Id. del ensamblado para importar a.</span><span class="sxs-lookup"><span data-stu-id="1dd30-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1dd30-107">Id. del archivo para importar desde.</span><span class="sxs-lookup"><span data-stu-id="1dd30-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="1dd30-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="1dd30-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="1dd30-109">Recibe el identificador de enumerador para los tipos en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="1dd30-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="1dd30-110">Si lo desea recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="1dd30-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="1dd30-111">Opcionalmente, recibe el recuento de tipos en el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="1dd30-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dd30-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1dd30-112">Return Value</span></span>  
 <span data-ttu-id="1dd30-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="1dd30-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dd30-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1dd30-114">Requirements</span></span>  
 <span data-ttu-id="1dd30-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="1dd30-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd30-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dd30-116">See also</span></span>
- [<span data-ttu-id="1dd30-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1dd30-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1dd30-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1dd30-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1dd30-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1dd30-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
