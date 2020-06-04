---
title: Elemento Sub o Function no definido
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 9eb13d943f9f1cffc984847f7339111e06f5aa6b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373932"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub o Function no definida (Visual Basic)
Se `Sub` `Function` debe definir o para que se llame a. Las causas posibles de este error son:  
  
- Error al escribir el nombre del procedimiento.  
  
- Intentar llamar a un procedimiento desde otro proyecto sin agregar explícitamente una referencia a ese proyecto en el cuadro de diálogo **referencias** .  
  
- Especificar un procedimiento que no es visible para el procedimiento que realiza la llamada.  
  
- Declarar una rutina de biblioteca de vínculos dinámicos (DLL) de Windows o una rutina de recursos de código de Macintosh que no está en la biblioteca o el recurso de código especificado.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que el nombre del procedimiento esté escrito correctamente.  
  
2. Busque el nombre del proyecto que contiene el procedimiento al que desea llamar en el cuadro de diálogo **referencias** . Si no aparece, haga clic en el botón **examinar** para buscarlo. Active la casilla situada a la izquierda del nombre del proyecto y, a continuación, haga clic en **Aceptar**.  
  
3. Compruebe el nombre de la rutina.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de error](../../programming-guide/language-features/error-types.md)
- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [Instrucción Sub](../statements/sub-statement.md)
- [Instrucción Function](../statements/function-statement.md)
