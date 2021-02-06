---
description: 'Más información sobre: método Setmanifestfile ('
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
ms.openlocfilehash: fe91c7f2b4e6f58a0a740de84e055ead49adb77d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662330"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="4d50a-103">SetManifestFile (Método)</span><span class="sxs-lookup"><span data-stu-id="4d50a-103">SetManifestFile Method</span></span>

<span data-ttu-id="4d50a-104">Permite especificar o restablecer el archivo de manifiesto que el vinculador utiliza al crear el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4d50a-104">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d50a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d50a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d50a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d50a-106">Parameters</span></span>  

 `pszFile`  
  
 <span data-ttu-id="4d50a-107">Nombre del archivo de manifiesto cuyo contenido se coloca en el BLOB de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="4d50a-107">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d50a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d50a-108">Return Value</span></span>  

 <span data-ttu-id="4d50a-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d50a-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d50a-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4d50a-110">Remarks</span></span>  

 <span data-ttu-id="4d50a-111">Llame a este método antes de solicitar el Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="4d50a-111">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="4d50a-112">El valor del `pszFile` parámetro es el nombre del archivo de manifiesto cuyo contenido se lee y se coloca en los recursos de Win32 con el identificador de RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="4d50a-112">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="4d50a-113">Cuando se llama con un parámetro de NULL, se borra cualquier manifiesto leído previamente.</span><span class="sxs-lookup"><span data-stu-id="4d50a-113">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="4d50a-114">Esto permite restablecer el estado del enlazador con respecto al tiempo de inicialización.</span><span class="sxs-lookup"><span data-stu-id="4d50a-114">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d50a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d50a-115">Requirements</span></span>  

 <span data-ttu-id="4d50a-116">Requiere aLink. h</span><span class="sxs-lookup"><span data-stu-id="4d50a-116">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d50a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d50a-117">See also</span></span>

- [<span data-ttu-id="4d50a-118">IALink3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d50a-118">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="4d50a-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="4d50a-119">ALink API</span></span>](index.md)
- [<span data-ttu-id="4d50a-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d50a-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4d50a-121">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="4d50a-121">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
