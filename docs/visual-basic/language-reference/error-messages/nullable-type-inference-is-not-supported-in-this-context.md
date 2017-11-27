---
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords: BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="480df-102">No se admite la inferencia de tipos que acepten valores NULL en este contexto</span><span class="sxs-lookup"><span data-stu-id="480df-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="480df-103">Tipos de valor y estructuras se pueden declarar que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="480df-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="480df-104">Sin embargo, no se puede utilizar la declaración que acepta valores NULL en combinación con la inferencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="480df-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="480df-105">Los ejemplos siguientes producen este error.</span><span class="sxs-lookup"><span data-stu-id="480df-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="480df-106">**Id. de error:** BC36629</span><span class="sxs-lookup"><span data-stu-id="480df-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="480df-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="480df-107">To correct this error</span></span>  
  
-   <span data-ttu-id="480df-108">Use un `As` cláusula para declarar la variable como que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="480df-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480df-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="480df-109">See Also</span></span>  
 [<span data-ttu-id="480df-110">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="480df-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="480df-111">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="480df-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
