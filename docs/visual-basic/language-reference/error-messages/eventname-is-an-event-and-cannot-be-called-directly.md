---
title: "'<eventname>' es un evento y no se le puede llamar directamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305603"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>'\<eventname >' es un evento y no se puede llamar directamente
' <`eventname`>' es un evento y no se puede llamar directamente. Use un `RaiseEvent` instrucción para generar un evento.  
  
 Una llamada a procedimiento especifica un evento para el nombre del procedimiento. Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que debe generarse y controlarse.  
  
 **Identificador de error:** BC32022  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Use un `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o procedimientos que lo procesan.  
  
## <a name="see-also"></a>Vea también

- [RaiseEvent (Instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
