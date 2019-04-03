---
title: Los parámetros opcionales deben especificar un valor predeterminado
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 01c0abb366e8605a9b153333e645fc3276b6bd16
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821730"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>Los parámetros opcionales deben especificar un valor predeterminado
Parámetros opcionales deben proporcionar valores predeterminados que se pueden usar si no se proporciona ningún parámetro de un procedimiento que realiza la llamada.  
  
 **Identificador de error:** BC30812  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Especificar valores predeterminados para los parámetros opcionales; Por ejemplo:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vea también

- [Opcional](../../../visual-basic/language-reference/modifiers/optional.md)
