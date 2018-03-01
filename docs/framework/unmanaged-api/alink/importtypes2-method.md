---
title: "ImportTypes2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47c49253a1e2839939ef4e671f155e4a44d07529
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="importtypes2-method"></a><span data-ttu-id="e47ec-102">ImportTypes2 (Método)</span><span class="sxs-lookup"><span data-stu-id="e47ec-102">ImportTypes2 Method</span></span>
<span data-ttu-id="e47ec-103">Inicia la importación de tipos.</span><span class="sxs-lookup"><span data-stu-id="e47ec-103">Initiates the import of types.</span></span> <span data-ttu-id="e47ec-104">Llamar a este método para iniciar la importación de tipos de cada ámbito importado a través de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="e47ec-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e47ec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e47ec-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e47ec-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e47ec-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e47ec-107">Identificador del ensamblado al que desea importar.</span><span class="sxs-lookup"><span data-stu-id="e47ec-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e47ec-108">Identificador del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="e47ec-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="e47ec-109">Ámbito de base cero de la que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="e47ec-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="e47ec-110">Recibe el identificador de enumerador para los tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="e47ec-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="e47ec-111">Opcionalmente, recibe [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="e47ec-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="e47ec-112">Opcionalmente, recibe el recuento de tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="e47ec-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e47ec-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e47ec-113">Return Value</span></span>  
 <span data-ttu-id="e47ec-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="e47ec-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e47ec-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e47ec-115">Requirements</span></span>  
 <span data-ttu-id="e47ec-116">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="e47ec-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47ec-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e47ec-117">See Also</span></span>  
 [<span data-ttu-id="e47ec-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e47ec-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e47ec-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e47ec-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e47ec-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e47ec-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
