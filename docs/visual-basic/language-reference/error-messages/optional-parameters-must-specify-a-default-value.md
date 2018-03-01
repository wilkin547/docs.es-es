---
title: "Los parámetros opcionales deben especificar un valor predeterminado"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e9ec6d044ba0a1bb904030ddbb4c4fa406c3ba63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
