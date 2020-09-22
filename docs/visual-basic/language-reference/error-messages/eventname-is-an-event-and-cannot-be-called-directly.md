---
title: "'<eventname>' es un evento y no se le puede llamar directamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3366bc215a45cd7de9dc2de285758a78144df509
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874318"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>'\<eventname>' es un evento y no se le puede llamar directamente

' <`eventname`> ' es un evento, por lo que no se puede llamar directamente a. Use una `RaiseEvent` instrucción para generar un evento.  
  
 Una llamada a procedimiento especifica un evento para el nombre del procedimiento. Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que se debe generar y controlar.  
  
 **Identificador de error:** BC32022  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Use una `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o los procedimientos que lo controlan.  
  
## <a name="see-also"></a>Consulte también

- [RaiseEvent (Instrucción)](../statements/raiseevent-statement.md)
