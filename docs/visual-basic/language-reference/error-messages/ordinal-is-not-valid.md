---
description: 'Más información acerca de: el ordinal no es válido'
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7c58675a08d3821cd05ba0109e5ce0107c68e497
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795526"
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
  
## <a name="see-also"></a>Vea también

- [Declare Statement](../statements/declare-statement.md)
