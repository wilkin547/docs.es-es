---
title: Sub o Function no definida (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
dev_langs:
- VB
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7d32bc9c8f13b245e6333c4460cab541f6e9409e
ms.lasthandoff: 03/13/2017

---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub o Function no definida (Visual Basic)
Un `Sub` o `Function` para llamarse deben definirse. Las causas posibles de este error son:  
  
-   Error al escribir el nombre del procedimiento.  
  
-   Intenta llamar a un procedimiento desde otro proyecto sin agregar explícitamente una referencia a ese proyecto en el **referencias** cuadro de diálogo.  
  
-   Especifica un procedimiento que no es visible para el procedimiento que realiza la llamada.  
  
-   Declaración de una rutina de biblioteca de vínculos dinámicos (DLL) de Windows o una rutina de recursos del código Macintosh que no está en el recurso de biblioteca o de código especificado.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que ha escrito correctamente el nombre del procedimiento.  
  
2.  Busque el nombre del proyecto que contiene el procedimiento que desea llamar el **referencias** cuadro de diálogo. Si no aparece, haga clic en el **examinar** botón para buscarlo. Active la casilla de verificación a la izquierda del nombre del proyecto y, a continuación, haga clic en **Aceptar**.  
  
3.  Compruebe el nombre de la rutina.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Administrar referencias en un proyecto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
