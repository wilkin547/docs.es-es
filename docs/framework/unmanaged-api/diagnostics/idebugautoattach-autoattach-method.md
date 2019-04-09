---
title: IDebugAutoAttach::AutoAttach (Método)
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5064e66708044d82e3a097c8235b5b28a3412200
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077139"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="2399f-102">IDebugAutoAttach::AutoAttach (Método)</span><span class="sxs-lookup"><span data-stu-id="2399f-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="2399f-103">Realiza automática del depurador invocado por el servidor de adjuntar.</span><span class="sxs-lookup"><span data-stu-id="2399f-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2399f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2399f-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2399f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2399f-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="2399f-106">[in] Siempre se establece en `GUID_NULL`.</span><span class="sxs-lookup"><span data-stu-id="2399f-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="2399f-107">[in] Identificador del proceso, normalmente se recuperan con el `GetCurrentProcessId` función.</span><span class="sxs-lookup"><span data-stu-id="2399f-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="2399f-108">[in] Tipo de programa: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, o `AUTOATTACH_PROGRAM_UNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="2399f-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="2399f-109">[in] Identificador de programa.</span><span class="sxs-lookup"><span data-stu-id="2399f-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="2399f-110">[in] Cadena pasada por el verbo debug.</span><span class="sxs-lookup"><span data-stu-id="2399f-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2399f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2399f-111">Return Value</span></span>  
 <span data-ttu-id="2399f-112">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="2399f-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2399f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2399f-113">Requirements</span></span>  
 <span data-ttu-id="2399f-114">**Encabezado**: DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="2399f-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2399f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2399f-115">See also</span></span>

- [<span data-ttu-id="2399f-116">IDebugAutoAttach (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2399f-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
