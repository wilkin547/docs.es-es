---
title: ICLRMetaHost::ExitProcess (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 83cbfa097541681305ff285f21c2b6c9c6391ef8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703747"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="6ef29-102">ICLRMetaHost::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="6ef29-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="6ef29-103">Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="6ef29-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="6ef29-104">Reemplaza la función [CorExitProcess (](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="6ef29-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef29-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ef29-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ef29-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ef29-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="6ef29-107">de Código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="6ef29-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ef29-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ef29-108">Return Value</span></span>  
 <span data-ttu-id="6ef29-109">Este método nunca devuelve, por lo que el valor devuelto es indefinido.</span><span class="sxs-lookup"><span data-stu-id="6ef29-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef29-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6ef29-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef29-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ef29-111">Requirements</span></span>  
 <span data-ttu-id="6ef29-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ef29-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef29-113">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="6ef29-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6ef29-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6ef29-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ef29-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef29-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef29-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6ef29-116">See also</span></span>

- [<span data-ttu-id="6ef29-117">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ef29-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="6ef29-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="6ef29-118">Hosting</span></span>](index.md)
