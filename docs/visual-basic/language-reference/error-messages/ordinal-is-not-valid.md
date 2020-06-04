---
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7b9bd8435b56dd5e33d14eb35d76aacc7d60c8b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413058"
---
# <a name="ordinal-is-not-valid"></a>El ordinal no es válido
La llamada a una biblioteca de vínculos dinámicos (DLL) indicada para usar un número en lugar de un nombre de procedimiento mediante la `#num` Sintaxis. Este error tiene las siguientes causas posibles:  
  
- Error al intentar convertir la `#num` expresión a un ordinal.  
  
- El `#num` especificado no especifica ninguna función en el archivo dll.  
  
- Una biblioteca de tipos tiene una declaración no válida que produce el uso interno de un número ordinal no válido.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que la expresión representa un número válido o llame al procedimiento por su nombre.  
  
2. Asegúrese `#num` de que identifica una función válida en el archivo dll.  
  
3. Aísle la llamada al procedimiento que causa el problema mediante el comentario del código. Escriba una `Declare` instrucción para el procedimiento e informe del problema al proveedor de la biblioteca de tipos.  
  
## <a name="see-also"></a>Consulte también

- [Declare Statement](../statements/declare-statement.md)
