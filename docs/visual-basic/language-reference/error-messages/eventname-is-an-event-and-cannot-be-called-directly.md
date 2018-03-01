---
title: '&#39; &lt;eventname&gt;&#39; es un evento y no se puede llamar directamente'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39; &lt;eventname&gt;&#39; es un evento y no se puede llamar directamente
' <`eventname`>' es un evento y no se puede llamar directamente. Use un `RaiseEvent` instrucción genera un evento.  
  
 Una llamada a procedimiento especifica un evento para el nombre del procedimiento. Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que debe generarse y controlarse.  
  
 **Id. de error:** BC32022  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Use un `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o procedimientos que lo controlan.  
  
## <a name="see-also"></a>Vea también  
 [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
