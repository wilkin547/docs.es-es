---
title: "'<eventname>' es un evento y no se le puede llamar directamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 246cb92daa2c838c95f695542f33cf02af42764d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161990"
---
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="05f74-102">BC32022: ' \<eventname> ' es un evento y no se puede llamar directamente</span><span class="sxs-lookup"><span data-stu-id="05f74-102">BC32022: '\<eventname>' is an event, and cannot be called directly</span></span>

<span data-ttu-id="05f74-103">' <`eventname`> ' es un evento, por lo que no se puede llamar directamente a.</span><span class="sxs-lookup"><span data-stu-id="05f74-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="05f74-104">Use una `RaiseEvent` instrucción para generar un evento.</span><span class="sxs-lookup"><span data-stu-id="05f74-104">Use a `RaiseEvent` statement to raise an event.</span></span>

 <span data-ttu-id="05f74-105">Una llamada a procedimiento especifica un evento para el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="05f74-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="05f74-106">Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que se debe generar y controlar.</span><span class="sxs-lookup"><span data-stu-id="05f74-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>

 <span data-ttu-id="05f74-107">**Identificador de error:** BC32022</span><span class="sxs-lookup"><span data-stu-id="05f74-107">**Error ID:** BC32022</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="05f74-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="05f74-108">To correct this error</span></span>

- <span data-ttu-id="05f74-109">Use una `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o los procedimientos que lo controlan.</span><span class="sxs-lookup"><span data-stu-id="05f74-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>

## <a name="see-also"></a><span data-ttu-id="05f74-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="05f74-110">See also</span></span>

- [<span data-ttu-id="05f74-111">RaiseEvent (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="05f74-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
