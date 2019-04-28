---
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 9f7f878649d8b96f050b56d5b878eb3d67e027ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918227"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="be615-102">No se admite la inferencia de tipos que acepten valores NULL en este contexto</span><span class="sxs-lookup"><span data-stu-id="be615-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="be615-103">Tipos de valor y las estructuras se pueden declarar que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="be615-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="be615-104">Sin embargo, no se puede utilizar la declaración que acepta valores NULL en combinación con la inferencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="be615-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="be615-105">Los ejemplos siguientes producen este error.</span><span class="sxs-lookup"><span data-stu-id="be615-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="be615-106">**Identificador de error:** BC36629</span><span class="sxs-lookup"><span data-stu-id="be615-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be615-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="be615-107">To correct this error</span></span>  
  
- <span data-ttu-id="be615-108">Use un `As` cláusula para declarar la variable que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="be615-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be615-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="be615-109">See also</span></span>

- [<span data-ttu-id="be615-110">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="be615-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="be615-111">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="be615-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
