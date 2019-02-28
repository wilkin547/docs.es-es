---
title: GetScope (Método)
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
ms.openlocfilehash: c5798fc488cf4453b6abcf00a7169b1ec0b529ec
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965376"
---
# <a name="getscope-method"></a><span data-ttu-id="6cd84-102">GetScope (Método)</span><span class="sxs-lookup"><span data-stu-id="6cd84-102">GetScope Method</span></span>
<span data-ttu-id="6cd84-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="6cd84-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6cd84-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6cd84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6cd84-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6cd84-106">Identificador único del ensamblado para importar a.</span><span class="sxs-lookup"><span data-stu-id="6cd84-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6cd84-107">Identificador único del archivo para importar desde.</span><span class="sxs-lookup"><span data-stu-id="6cd84-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="6cd84-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="6cd84-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="6cd84-109">Recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="6cd84-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cd84-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6cd84-110">Return Value</span></span>  
 <span data-ttu-id="6cd84-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="6cd84-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cd84-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6cd84-112">Requirements</span></span>  
 <span data-ttu-id="6cd84-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="6cd84-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cd84-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cd84-114">See also</span></span>
- [<span data-ttu-id="6cd84-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6cd84-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6cd84-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6cd84-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6cd84-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="6cd84-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
