---
title: SetManifestFile (Método)
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8307960166cfc668a577431d688c439f0f794be2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072433"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="5993f-102">SetManifestFile (Método)</span><span class="sxs-lookup"><span data-stu-id="5993f-102">SetManifestFile Method</span></span>
<span data-ttu-id="5993f-103">Permite especificar o restablecer el archivo de manifiesto que el vinculador usa cuando crea el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5993f-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5993f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5993f-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5993f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5993f-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="5993f-106">El nombre del archivo de manifiesto cuyo contenido se coloca en el blob de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="5993f-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5993f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5993f-107">Return Value</span></span>  
 <span data-ttu-id="5993f-108">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="5993f-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5993f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5993f-109">Remarks</span></span>  
 <span data-ttu-id="5993f-110">Se llama antes de solicitar la Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="5993f-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="5993f-111">El valor de la `pszFile` parámetro es el nombre del archivo de manifiesto cuyo contenido se lee y se colocan en los recursos de Win32 con el identificador de RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="5993f-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="5993f-112">Cuando se llama mediante un parámetro es null, se borra cualquier manifiesto leída previamente.</span><span class="sxs-lookup"><span data-stu-id="5993f-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="5993f-113">Esto permite restablecer el estado del vinculador para que el de tiempo de inicialización.</span><span class="sxs-lookup"><span data-stu-id="5993f-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5993f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5993f-114">Requirements</span></span>  
 <span data-ttu-id="5993f-115">Requiere aLink.h</span><span class="sxs-lookup"><span data-stu-id="5993f-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5993f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5993f-116">See also</span></span>

- [<span data-ttu-id="5993f-117">IALink3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5993f-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="5993f-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="5993f-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="5993f-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5993f-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5993f-120">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="5993f-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
