---
title: ICorDebugManagedCallback3::CustomNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: 078f90387a475559067d402610ec264f4076ae01
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793264"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="388a7-102">ICorDebugManagedCallback3::CustomNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="388a7-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="388a7-103">Indica que se ha generado una notificación del depurador personalizado.</span><span class="sxs-lookup"><span data-stu-id="388a7-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="388a7-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="388a7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="388a7-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="388a7-106">de Puntero al subproceso que provocó la notificación.</span><span class="sxs-lookup"><span data-stu-id="388a7-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="388a7-107">de Puntero al dominio de aplicación que contiene el subproceso que provocó la notificación.</span><span class="sxs-lookup"><span data-stu-id="388a7-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="388a7-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="388a7-108">Return Value</span></span>  
 <span data-ttu-id="388a7-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="388a7-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="388a7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="388a7-110">HRESULT</span></span>|<span data-ttu-id="388a7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="388a7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="388a7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="388a7-112">S_OK</span></span>|<span data-ttu-id="388a7-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="388a7-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="388a7-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="388a7-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="388a7-115">Notas</span><span class="sxs-lookup"><span data-stu-id="388a7-115">Remarks</span></span>  
 <span data-ttu-id="388a7-116">Una llamada subsiguiente al método [ICorDebugThread4:: getcurrentcustomdebuggernotification (](icordebugthread4-getcurrentcustomdebuggernotification-method.md) recupera el objeto de subproceso que se pasó al método <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="388a7-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="388a7-117">El tipo del objeto de subproceso debe haberse habilitado previamente mediante una llamada al método [ICorDebugProcess3 (:: SetEnableCustomNotification (](icordebugprocess3-setenablecustomnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="388a7-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="388a7-118">El depurador puede leer parámetros específicos del tipo de los campos del objeto de subproceso y puede almacenar las respuestas en los campos.</span><span class="sxs-lookup"><span data-stu-id="388a7-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="388a7-119">La interfaz [ICorDebug](icordebug-interface.md) no impone ninguna directiva en los tipos de notificaciones ni su contenido, y la semántica de las notificaciones es estrictamente un contrato entre los depuradores, las aplicaciones y el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="388a7-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="388a7-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="388a7-120">Requirements</span></span>  
 <span data-ttu-id="388a7-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="388a7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="388a7-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="388a7-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="388a7-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="388a7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="388a7-124">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="388a7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388a7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="388a7-125">See also</span></span>

- [<span data-ttu-id="388a7-126">ICorDebugManagedCallback3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="388a7-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="388a7-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="388a7-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="388a7-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="388a7-128">Debugging</span></span>](index.md)
