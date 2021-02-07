---
description: 'Más información sobre: Icordebugprocess3 (:: SetEnableCustomNotification ((método)'
title: ICorDebugProcess3::SetEnableCustomNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: 71d1d23b1fa4ba16b26b7c9bacf7fb5cec5e5074
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746480"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="38490-103">ICorDebugProcess3::SetEnableCustomNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="38490-103">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>

<span data-ttu-id="38490-104">Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="38490-104">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38490-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38490-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38490-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38490-106">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="38490-107">de Tipo que especifica las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="38490-107">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="38490-108">[in] `true` para habilitar las notificaciones del depurador personalizadas; `false` para deshabilitar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="38490-108">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="38490-109">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="38490-109">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38490-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38490-110">Remarks</span></span>  

 <span data-ttu-id="38490-111">Cuando `fEnable` se establece en `true` , las llamadas al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> método desencadenan una devolución de llamada [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="38490-111">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="38490-112">Las notificaciones están deshabilitadas de forma predeterminada; por consiguiente, el depurador debe especificar los tipos de notificación que conoce y desea controlar.</span><span class="sxs-lookup"><span data-stu-id="38490-112">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="38490-113">Dado que el ámbito de la clase [ICorDebugClass](icordebug-interface.md) es el dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="38490-113">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="38490-114">A partir de la .NET Framework 4, la única notificación admitida es una notificación de dependencia entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="38490-114">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38490-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38490-115">Requirements</span></span>  

 <span data-ttu-id="38490-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38490-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38490-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38490-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38490-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38490-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38490-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38490-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38490-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="38490-120">See also</span></span>

- [<span data-ttu-id="38490-121">ICorDebugProcess3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="38490-121">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="38490-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="38490-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="38490-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="38490-123">Debugging</span></span>](index.md)
