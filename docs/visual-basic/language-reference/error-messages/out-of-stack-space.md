---
title: (Visual Basic) de espacio de pila | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 6343767da28ea4e02f9443006b222640755f7882
ms.lasthandoff: 03/13/2017

---
# <a name="out-of-stack-space-visual-basic"></a>Espacio de pila insuficiente (Visual Basic)
La pila es un área de trabajo de memoria que aumenta y disminuye dinámicamente con las demandas del programa en ejecución. Se han superado su límite.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe que los procedimientos no están anidados demasiado profundo.  
  
2.  Asegúrese de que los procedimientos recursivos terminan correctamente.  
  
3.  Si las variables locales requieren más espacio de variable local que está disponible, intente declarar algunas variables en el nivel de módulo. También puede declarar todas las variables en el procedimiento estático poniendo el `Property`, `Sub`, o `Function` palabra clave with `Static`. O bien puede usar el `Static` instrucción para declarar variables estáticas individuales dentro de procedimientos.  
  
4.  Volver a definir algunas de las cadenas de longitud fija como cadenas de longitud variable, como cadenas de longitud fija utilizan más espacio de pila que las cadenas de longitud variable. También puede definir la cadena en el nivel de módulo donde no requiere ningún espacio de pila.  
  
5.  Compruebe el número de anidada `DoEvents` llamadas a funciones, usando la `Calls` cuadro de diálogo para ver qué procedimientos están activos en la pila.  
  
6.  Asegúrese de que no ha provocado "eventos en cascada" desencadenando un evento que llama a un procedimiento de evento ya en la pila. Un evento en cascada es similar a una llamada de procedimiento recursiva indefinida, pero es menos evidente, dado que la llamada se realiza por [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] en lugar de una llamada explícita en el código. Utilice la `Calls`cuadro de diálogo para ver qué procedimientos están activos en la pila.  
  
## <a name="see-also"></a>Vea también  
 [Ventana Memoria](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
