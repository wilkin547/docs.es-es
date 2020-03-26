---
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249505"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="a84dd-102">No se admite la inferencia de tipos que acepten valores NULL en este contexto</span><span class="sxs-lookup"><span data-stu-id="a84dd-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="a84dd-103">Los tipos de valor y las estructuras se pueden declarar que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a84dd-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="a84dd-104">Sin embargo, no puede usar la declaración que acepta valores NULL en combinación con la inferencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="a84dd-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="a84dd-105">Los siguientes ejemplos provocan este error.</span><span class="sxs-lookup"><span data-stu-id="a84dd-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="a84dd-106">**ID de error:** BC36629</span><span class="sxs-lookup"><span data-stu-id="a84dd-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a84dd-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a84dd-107">To correct this error</span></span>  
  
- <span data-ttu-id="a84dd-108">Utilice `As` una cláusula para declarar la variable como un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a84dd-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84dd-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a84dd-109">See also</span></span>

- [<span data-ttu-id="a84dd-110">Tipos de valores que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="a84dd-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="a84dd-111">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="a84dd-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
