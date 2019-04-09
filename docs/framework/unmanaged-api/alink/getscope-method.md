---
title: Método GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 571612796d4e66be9dd8469d748c2380c839ddfa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165794"
---
# <a name="getscope-method"></a><span data-ttu-id="a6391-102">Método GetScope</span><span class="sxs-lookup"><span data-stu-id="a6391-102">GetScope Method</span></span>
<span data-ttu-id="a6391-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="a6391-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6391-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6391-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6391-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6391-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a6391-106">Identificador único del ensamblado para importar a.</span><span class="sxs-lookup"><span data-stu-id="a6391-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a6391-107">Identificador único del archivo para importar desde.</span><span class="sxs-lookup"><span data-stu-id="a6391-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="a6391-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="a6391-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="a6391-109">Recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a6391-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6391-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a6391-110">Return Value</span></span>  
 <span data-ttu-id="a6391-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="a6391-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6391-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6391-112">Requirements</span></span>  
 <span data-ttu-id="a6391-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="a6391-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6391-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6391-114">See also</span></span>

- [<span data-ttu-id="a6391-115">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6391-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a6391-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6391-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a6391-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a6391-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
