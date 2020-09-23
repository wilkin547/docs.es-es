---
title: Nothing y cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d4c7ee6d13334617a80abb845af52bf388a12797
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072527"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing y cadenas en Visual Basic

El tiempo de ejecución de Visual Basic y el .NET Framework se evalúan de `Nothing` forma diferente cuando se trata de cadenas.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic en tiempo de ejecución y el .NET Framework  

 Considere el ejemplo siguiente:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Normalmente, el tiempo de ejecución de Visual Basic se evalúa `Nothing` como una cadena vacía (""). Sin embargo, el .NET Framework no y produce una excepción cada vez que se realiza un intento de realizar una operación de cadena en `Nothing` .  
  
## <a name="see-also"></a>Vea también

- [Introducción a las cadenas en Visual Basic](introduction-to-strings.md)
