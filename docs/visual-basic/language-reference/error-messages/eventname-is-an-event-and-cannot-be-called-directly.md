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
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a>BC32022: ' \<eventname> ' es un evento y no se puede llamar directamente

' <`eventname`> ' es un evento, por lo que no se puede llamar directamente a. Use una `RaiseEvent` instrucción para generar un evento.

 Una llamada a procedimiento especifica un evento para el nombre del procedimiento. Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que se debe generar y controlar.

 **Identificador de error:** BC32022

## <a name="to-correct-this-error"></a>Para corregir este error

- Use una `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o los procedimientos que lo controlan.

## <a name="see-also"></a>Vea también

- [RaiseEvent (Instrucción)](../statements/raiseevent-statement.md)
