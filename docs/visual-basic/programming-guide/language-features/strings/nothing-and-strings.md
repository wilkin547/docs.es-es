---
title: Nothing y cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344293"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing y cadenas en Visual Basic
El tiempo de ejecución de Visual Basic y el .NET Framework evalúan `Nothing` de manera diferente cuando se trata de cadenas.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic en tiempo de ejecución y el .NET Framework  
 Considere el ejemplo siguiente:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Normalmente, el tiempo de ejecución de Visual Basic evalúa `Nothing` como una cadena vacía (""). Sin embargo, el .NET Framework no y produce una excepción cada vez que se realiza un intento de realizar una operación de cadena en `Nothing`.  
  
## <a name="see-also"></a>Vea también

- [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
