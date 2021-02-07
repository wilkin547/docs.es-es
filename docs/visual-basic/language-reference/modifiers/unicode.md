---
description: 'Más información acerca de: Unicode (Visual Basic)'
title: Unicode
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: b0c71d8fdefe3f0d240201e0d57265e5c6081d50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700720"
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)

Especifica que Visual Basic debe serializar todas las cadenas en valores Unicode, independientemente del nombre del procedimiento externo que se está declarando.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que debe tener para poder llamar al procedimiento correctamente. Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa. La [instrucción Declare](../statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 La `charsetmodifier` parte de la `Declare` instrucción proporciona la información del juego de caracteres para calcular las referencias de cadenas durante una llamada al procedimiento externo. También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo. El `Unicode` modificador especifica que Visual Basic debe serializar todas las cadenas en valores Unicode y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.  
  
 Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Observaciones  

 El `Unicode` modificador se puede usar en este contexto:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas para desarrolladores de Smart Device  

 Esta palabra clave no es compatible.  
  
## <a name="see-also"></a>Vea también

- [Ansi](ansi.md)
- [Automático](auto.md)
- [Palabras clave](../keywords/index.md)
