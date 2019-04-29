---
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 28f78161e14604c1f59872801855ccc918faec58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772494"
---
# <a name="ordinal-is-not-valid"></a>El ordinal no es válido
La llamada a una biblioteca de vínculos dinámicos (DLL) indica que use un número en lugar de un nombre de procedimiento mediante el `#num` sintaxis. Este error tiene las siguientes causas posibles:  
  
- Un intento para convertir el `#num` expresión a un error de ordinal.  
  
- El `#num` especificado no se especifica ninguna función en el archivo DLL.  
  
- Una biblioteca de tipos tiene una declaración no válida, lo que resulta en un uso interno de un número ordinal no válido.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que la expresión representa un número válido, o llame al procedimiento por nombre.  
  
2. Asegúrese de que `#num` identifica una función válida en el archivo DLL.  
  
3. Aislar la causa del problema marcando como comentario el código de la llamada del procedimiento. Escribir un `Declare` declaración para el procedimiento y notificar el problema para el proveedor de la biblioteca de tipos.  
  
## <a name="see-also"></a>Vea también

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
