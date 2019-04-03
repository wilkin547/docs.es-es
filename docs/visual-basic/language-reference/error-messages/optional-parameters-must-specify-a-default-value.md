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
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="3de29-102">Los parámetros opcionales deben especificar un valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3de29-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="3de29-103">Parámetros opcionales deben proporcionar valores predeterminados que se pueden usar si no se proporciona ningún parámetro de un procedimiento que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="3de29-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="3de29-104">**Identificador de error:** BC30812</span><span class="sxs-lookup"><span data-stu-id="3de29-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3de29-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3de29-105">To correct this error</span></span>  
  
-   <span data-ttu-id="3de29-106">Especificar valores predeterminados para los parámetros opcionales; Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3de29-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3de29-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="3de29-107">See also</span></span>

- [<span data-ttu-id="3de29-108">Opcional</span><span class="sxs-lookup"><span data-stu-id="3de29-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
