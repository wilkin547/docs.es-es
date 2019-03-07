---
title: GetScope2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3c11eeeb4eece495a7ccbe51c7e04d077e497ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494576"
---
# <a name="getscope2-method"></a><span data-ttu-id="cb554-102">GetScope2 (Método)</span><span class="sxs-lookup"><span data-stu-id="cb554-102">GetScope2 Method</span></span>
<span data-ttu-id="cb554-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="cb554-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb554-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb554-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="cb554-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb554-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cb554-106">Id. del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="cb554-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cb554-107">Id. de archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="cb554-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="cb554-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="cb554-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="cb554-109">Recibe el puntero a [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interfaz para el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="cb554-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb554-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cb554-110">Return Value</span></span>  
 <span data-ttu-id="cb554-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="cb554-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb554-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb554-112">Requirements</span></span>  
 <span data-ttu-id="cb554-113">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="cb554-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb554-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb554-114">See also</span></span>
- [<span data-ttu-id="cb554-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb554-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cb554-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb554-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cb554-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="cb554-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
