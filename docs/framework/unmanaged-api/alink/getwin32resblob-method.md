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
ms.openlocfilehash: abc5f9350342af0439cb83f1df14979cfabcdb3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601550"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="f8999-102">GetWin32ResBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="f8999-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="f8999-103">Recupera el objeto binario de recursos Win32.</span><span class="sxs-lookup"><span data-stu-id="f8999-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="f8999-104">Llame a este método después de establecer las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f8999-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8999-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8999-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f8999-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8999-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f8999-107">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f8999-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f8999-108">Token de archivo usado para recuperar el nombre de archivo que se utilizará al construir el recurso de versión de Win32</span><span class="sxs-lookup"><span data-stu-id="f8999-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="f8999-109">TRUE si el archivo es un archivo DLL, es false para un archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="f8999-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="f8999-110">Icono opcional para insertar en el objeto binario de recursos.</span><span class="sxs-lookup"><span data-stu-id="f8999-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="f8999-111">Recibe el objeto binario de recursos.</span><span class="sxs-lookup"><span data-stu-id="f8999-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="f8999-112">Recibe el tamaño del blob.</span><span class="sxs-lookup"><span data-stu-id="f8999-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8999-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f8999-113">Return Value</span></span>  
 <span data-ttu-id="f8999-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="f8999-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8999-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8999-115">Requirements</span></span>  
 <span data-ttu-id="f8999-116">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="f8999-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8999-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8999-117">See also</span></span>
- [<span data-ttu-id="f8999-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8999-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f8999-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8999-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f8999-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f8999-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
