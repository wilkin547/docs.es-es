---
title: Los límites de matriz no pueden aparecer en los especificadores de tipo
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="90af1-102">Los límites de matriz no pueden aparecer en los especificadores de tipo</span><span class="sxs-lookup"><span data-stu-id="90af1-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="90af1-103">Los tamaños de matriz no pueden declararse como parte de un especificador de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="90af1-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="90af1-104">**Id. de error:** BC30638</span><span class="sxs-lookup"><span data-stu-id="90af1-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="90af1-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="90af1-105">To correct this error</span></span>  
  
-   <span data-ttu-id="90af1-106">Especifique el tamaño de la matriz inmediatamente después del nombre de variable en lugar de establecer el tamaño de matriz detrás del tipo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="90af1-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="90af1-107">Definir una matriz e inicialícela con el número deseado de elementos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="90af1-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="90af1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="90af1-108">See Also</span></span>  
 [<span data-ttu-id="90af1-109">Matrices</span><span class="sxs-lookup"><span data-stu-id="90af1-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
