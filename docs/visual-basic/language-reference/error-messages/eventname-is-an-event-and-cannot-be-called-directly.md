---
title: '&#39;&lt;EventName&gt; &#39; es un evento y no se puede llamar directamente'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3efd8c18497ce288e16659db4ca4693d5a3e6acc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582007"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39;&lt;EventName&gt; &#39; es un evento y no se puede llamar directamente
' <`eventname`>' es un evento y no se puede llamar directamente. Use un `RaiseEvent` instrucción para generar un evento.  
  
 Una llamada a procedimiento especifica un evento para el nombre del procedimiento. Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que debe generarse y controlarse.  
  
 **Identificador de error:** BC32022  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Use un `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o procedimientos que lo procesan.  
  
## <a name="see-also"></a>Vea también
- [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
