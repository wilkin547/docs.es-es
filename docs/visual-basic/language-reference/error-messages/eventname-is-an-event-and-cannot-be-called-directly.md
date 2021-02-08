---
description: "Más información sobre: BC32022: ' <eventname> ' es un evento y no se puede llamar directamente"
title: "'<eventname>' es un evento y no se le puede llamar directamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: f9d4b8fe54e1101e7963933f871cf5af2c1af903
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796449"
---
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="52d1c-103">BC32022: ' \<eventname> ' es un evento y no se puede llamar directamente</span><span class="sxs-lookup"><span data-stu-id="52d1c-103">BC32022: '\<eventname>' is an event, and cannot be called directly</span></span>

<span data-ttu-id="52d1c-104">' <`eventname`> ' es un evento, por lo que no se puede llamar directamente a.</span><span class="sxs-lookup"><span data-stu-id="52d1c-104">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="52d1c-105">Use una `RaiseEvent` instrucción para generar un evento.</span><span class="sxs-lookup"><span data-stu-id="52d1c-105">Use a `RaiseEvent` statement to raise an event.</span></span>

 <span data-ttu-id="52d1c-106">Una llamada a procedimiento especifica un evento para el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="52d1c-106">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="52d1c-107">Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que se debe generar y controlar.</span><span class="sxs-lookup"><span data-stu-id="52d1c-107">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>

 <span data-ttu-id="52d1c-108">**Identificador de error:** BC32022</span><span class="sxs-lookup"><span data-stu-id="52d1c-108">**Error ID:** BC32022</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="52d1c-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="52d1c-109">To correct this error</span></span>

- <span data-ttu-id="52d1c-110">Use una `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o los procedimientos que lo controlan.</span><span class="sxs-lookup"><span data-stu-id="52d1c-110">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>

## <a name="see-also"></a><span data-ttu-id="52d1c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="52d1c-111">See also</span></span>

- [<span data-ttu-id="52d1c-112">RaiseEvent (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="52d1c-112">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
