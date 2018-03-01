---
title: "El ordinal no es válido"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a>El ordinal no es válido
La llamada a una biblioteca de vínculos dinámicos (DLL) indica el uso de un número en lugar de un nombre de procedimiento, mediante el `#num` sintaxis. Este error tiene las siguientes causas posibles:  
  
-   Un intento para convertir el `#num` expresión a un valor ordinal no se pudo.  
  
-   El `#num` especificado no se especifica ninguna función en el archivo DLL.  
  
-   Una biblioteca de tipos tiene una declaración no válida que permite el uso interno de un número ordinal no válido.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que la expresión representa un número válido o llame al procedimiento por nombre.  
  
2.  Asegúrese de que `#num` identifica una función válida en el archivo DLL.  
  
3.  Aislar la llamada de procedimiento que causa el problema marcando como comentario el código. Escribir un `Declare` declaración para el procedimiento y notificar el problema al proveedor de la biblioteca de tipos.  
  
## <a name="see-also"></a>Vea también  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
