---
title: "'<eventname>' es un evento y no se le puede llamar directamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4e27d9ce788ae7b9741c0cb80da776959748b8b9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272732"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>'\<eventname >' es un evento y no se puede llamar directamente
' <`eventname`>' es un evento y no se puede llamar directamente. Use un `RaiseEvent` instrucción para generar un evento.  
  
 Una llamada a procedimiento especifica un evento para el nombre del procedimiento. Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que debe generarse y controlarse.  
  
 **Identificador de error:** BC32022  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Use un `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o procedimientos que lo procesan.  
  
## <a name="see-also"></a>Vea también
- [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
