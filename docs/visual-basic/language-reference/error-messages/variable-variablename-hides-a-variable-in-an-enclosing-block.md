---
title: La variable '<variablename>' oculta una variable en un bloque de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 4312abef83728f432e2f6a492e5acad3450719b1
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592061"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>La variable ' \<variablename > ' oculta una variable en un bloque de inclusión
Una variable encerrada en un bloque tiene el mismo nombre que otra variable local.  
  
 **IDENTIFICADOR de error:** BC30616  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Cambie el nombre de la variable en el bloque incluido para que no sea el mismo que cualquier otra variable local. Por ejemplo:  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Una causa común de este error es el uso de `Catch e As Exception` dentro de un controlador de eventos. En este caso, asigne un nombre a la variable de bloque `Catch` `ex` en lugar de `e`.  
  
- Otro origen común de este error es un intento de obtener acceso a una variable local declarada dentro de un bloque `Try` en un bloque `Catch` independiente. Para corregir esto, declare la variable fuera de la estructura `Try...Catch...Finally`.  
  
## <a name="see-also"></a>Vea también

- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
