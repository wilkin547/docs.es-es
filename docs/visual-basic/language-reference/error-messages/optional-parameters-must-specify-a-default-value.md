---
title: Los parámetros opcionales deben especificar un valor predeterminado
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 6788a7908489591e266af6d141006f2aa2d0e6f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="optional-parameters-must-specify-a-default-value"></a>Los parámetros opcionales deben especificar un valor predeterminado
Parámetros opcionales deben proporcionar valores predeterminados que se pueden utilizar si se proporciona ningún parámetro por un procedimiento que realiza la llamada.  
  
 **Id. de error:** BC30812  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Especificar los valores predeterminados para los parámetros opcionales; Por ejemplo:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Opcional](../../../visual-basic/language-reference/modifiers/optional.md)
