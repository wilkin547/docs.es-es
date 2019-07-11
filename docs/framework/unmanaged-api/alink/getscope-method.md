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
ms.openlocfilehash: f3c3142ca12789b086bcd8b5a9c00c943264ae7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741856"
---
# <a name="getscope-method"></a><span data-ttu-id="704db-102">Método GetScope</span><span class="sxs-lookup"><span data-stu-id="704db-102">GetScope Method</span></span>
<span data-ttu-id="704db-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="704db-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="704db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="704db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="704db-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="704db-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="704db-106">Identificador único del ensamblado para importar a.</span><span class="sxs-lookup"><span data-stu-id="704db-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="704db-107">Identificador único del archivo para importar desde.</span><span class="sxs-lookup"><span data-stu-id="704db-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="704db-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="704db-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="704db-109">Recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="704db-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="704db-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="704db-110">Return Value</span></span>  
 <span data-ttu-id="704db-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="704db-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="704db-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="704db-112">Requirements</span></span>  
 <span data-ttu-id="704db-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="704db-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704db-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="704db-114">See also</span></span>

- [<span data-ttu-id="704db-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="704db-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="704db-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="704db-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="704db-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="704db-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
