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
ms.openlocfilehash: 321038a148c27086ca499e2f448eb50cb93525ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405517"
---
# <a name="importtypes-method"></a><span data-ttu-id="1ef97-102">ImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="1ef97-102">ImportTypes Method</span></span>
<span data-ttu-id="1ef97-103">Inicia la importación de los tipos de cada ámbito importado a través de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="1ef97-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ef97-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="1ef97-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ef97-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1ef97-106">Id. del ensamblado que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="1ef97-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1ef97-107">Identificador del archivo para importar desde.</span><span class="sxs-lookup"><span data-stu-id="1ef97-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="1ef97-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="1ef97-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="1ef97-109">Recibe el identificador de enumerador para los tipos en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="1ef97-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="1ef97-110">Opcionalmente, recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="1ef97-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="1ef97-111">Opcionalmente, recibe el recuento de tipos en el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="1ef97-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ef97-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ef97-112">Return Value</span></span>  
 <span data-ttu-id="1ef97-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="1ef97-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef97-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ef97-114">Requirements</span></span>  
 <span data-ttu-id="1ef97-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="1ef97-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef97-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ef97-116">See Also</span></span>  
 [<span data-ttu-id="1ef97-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ef97-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1ef97-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ef97-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1ef97-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1ef97-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
