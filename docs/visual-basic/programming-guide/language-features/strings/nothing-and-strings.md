---
title: Nothing y cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 392de45b0ee1688224f3e8170b0144f1acdb0912
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360571"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing y cadenas en Visual Basic
El tiempo de ejecución de Visual Basic y el .NET Framework se evalúan de `Nothing` forma diferente cuando se trata de cadenas.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic en tiempo de ejecución y el .NET Framework  
 Considere el ejemplo siguiente:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Normalmente, el tiempo de ejecución de Visual Basic se evalúa `Nothing` como una cadena vacía (""). Sin embargo, el .NET Framework no y produce una excepción cada vez que se realiza un intento de realizar una operación de cadena en `Nothing` .  
  
## <a name="see-also"></a>Consulte también

- [Introducción a las cadenas en Visual Basic](introduction-to-strings.md)
