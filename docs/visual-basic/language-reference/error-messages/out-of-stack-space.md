---
title: Espacio de pila insuficiente
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: afb6a42372bdbd2e49ac15fbbf2b9e254f8db431
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871314"
---
# <a name="out-of-stack-space-visual-basic"></a>Espacio de pila insuficiente (Visual Basic)

La pila es un área de trabajo de memoria que aumenta y disminuye dinámicamente con las demandas del programa en ejecución. Se han superado sus límites.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe que los procedimientos no estén demasiado anidados.  
  
2. Asegúrese de que los procedimientos recursivos se terminan correctamente.  
  
3. Si las variables locales requieren más espacio de variables locales que el disponible, intente declarar algunas variables en el nivel de módulo. También puede declarar todas las variables en el procedimiento static anteponiendo la `Property` `Sub` palabra clave, o `Function` con `Static` . O bien, puede usar la `Static` instrucción para declarar variables estáticas individuales dentro de los procedimientos.  
  
4. Vuelva a definir algunas cadenas de longitud fija como cadenas de longitud variable, ya que las cadenas de longitud fija utilizan más espacio de pila que las cadenas de longitud variable. También puede definir la cadena en el nivel de módulo en el que no se requiere espacio de pila.  
  
5. Compruebe el número de `DoEvents` llamadas a funciones anidadas mediante el `Calls` cuadro de diálogo para ver los procedimientos que están activos en la pila.  
  
6. Asegúrese de que no ocasionó un "evento en cascada" desencadenando un evento que llama a un procedimiento de evento que ya está en la pila. Un evento en cascada es similar a una llamada a procedimiento recursivo no terminada, pero es menos obvio, ya que la llamada se realiza mediante Visual Basic en lugar de una llamada explícita en el código. Utilice el `Calls` cuadro de diálogo para ver los procedimientos que están activos en la pila.  
  
## <a name="see-also"></a>Vea también

- [Ventana Memoria](/visualstudio/debugger/memory-windows)
