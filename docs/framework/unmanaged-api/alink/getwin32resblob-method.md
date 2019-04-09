---
title: GetWin32ResBlob (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4c77ade46d2401e2499a94504808efd94f79f93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152157"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="1af7e-102">GetWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="1af7e-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="1af7e-103">Recupera el objeto binario de recursos Win32.</span><span class="sxs-lookup"><span data-stu-id="1af7e-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="1af7e-104">Llame a este método después de establecer las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1af7e-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af7e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1af7e-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1af7e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1af7e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1af7e-107">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1af7e-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1af7e-108">Token de archivo usado para recuperar el nombre de archivo que se utilizará al construir el recurso de versión de Win32</span><span class="sxs-lookup"><span data-stu-id="1af7e-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="1af7e-109">TRUE si el archivo es un archivo DLL, es false para un archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="1af7e-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="1af7e-110">Icono opcional para insertar en el objeto binario de recursos.</span><span class="sxs-lookup"><span data-stu-id="1af7e-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="1af7e-111">Recibe el objeto binario de recursos.</span><span class="sxs-lookup"><span data-stu-id="1af7e-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="1af7e-112">Recibe el tamaño del blob.</span><span class="sxs-lookup"><span data-stu-id="1af7e-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1af7e-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1af7e-113">Return Value</span></span>  
 <span data-ttu-id="1af7e-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="1af7e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af7e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1af7e-115">Requirements</span></span>  
 <span data-ttu-id="1af7e-116">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="1af7e-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af7e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1af7e-117">See also</span></span>

- [<span data-ttu-id="1af7e-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1af7e-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1af7e-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1af7e-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1af7e-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1af7e-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
