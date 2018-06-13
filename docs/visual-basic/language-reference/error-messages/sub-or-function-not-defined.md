---
title: Sub o Function no definida (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 58e90d769d5a7f2d88b5c27d1ec7d0d28c8d7b03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593706"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub o Function no definida (Visual Basic)
A `Sub` o `Function` deben definirse con el fin de llamar. Las causas posibles de este error son:  
  
-   Error al escribir el nombre del procedimiento.  
  
-   Intenta llamar a un procedimiento desde otro proyecto sin agregar explícitamente una referencia a ese proyecto en el **referencias** cuadro de diálogo.  
  
-   Especifica un procedimiento que no es visible para el procedimiento que realiza la llamada.  
  
-   La declaración de una rutina de biblioteca de vínculos dinámicos (DLL) de Windows o una rutina de recurso de código de Macintosh que no está en el recurso de biblioteca o el código especificado.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el nombre del procedimiento se ha escrito correctamente.  
  
2.  Busque el nombre del proyecto que contiene el procedimiento que desea llamar el **referencias** cuadro de diálogo. Si no aparece, haga clic en el **examinar** botón para buscarlo. Active la casilla situada a la izquierda del nombre del proyecto y, a continuación, haga clic en **Aceptar**.  
  
3.  Compruebe el nombre de la rutina.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
