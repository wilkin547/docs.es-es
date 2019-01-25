---
title: GetScope (método1)
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
ms.openlocfilehash: 782697536f5e01fa29830a64e47d960a47fe4eae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663146"
---
# <a name="getscope-method1"></a><span data-ttu-id="12951-102">GetScope (método1)</span><span class="sxs-lookup"><span data-stu-id="12951-102">GetScope Method1</span></span>
<span data-ttu-id="12951-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="12951-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12951-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12951-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12951-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12951-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="12951-106">Identificador único del ensamblado para importar a.</span><span class="sxs-lookup"><span data-stu-id="12951-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="12951-107">Identificador único del archivo para importar desde.</span><span class="sxs-lookup"><span data-stu-id="12951-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="12951-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="12951-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="12951-109">Recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="12951-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12951-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="12951-110">Return Value</span></span>  
 <span data-ttu-id="12951-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="12951-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12951-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12951-112">Requirements</span></span>  
 <span data-ttu-id="12951-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="12951-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12951-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="12951-114">See also</span></span>
- [<span data-ttu-id="12951-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12951-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="12951-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12951-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="12951-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="12951-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
