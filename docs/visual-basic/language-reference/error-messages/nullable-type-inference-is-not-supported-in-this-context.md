---
description: 'Más información sobre: BC36629: no se admite la inferencia de tipos que aceptan valores NULL en este contexto'
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 915f964d55068f39b0468e2c47cc6e5538be1a6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795630"
---
# <a name="bc36629-nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="6e2bb-103">BC36629: no se admite la inferencia de tipos que aceptan valores NULL en este contexto</span><span class="sxs-lookup"><span data-stu-id="6e2bb-103">BC36629: Nullable type inference is not supported in this context</span></span>

<span data-ttu-id="6e2bb-104">Los tipos de valor y las estructuras se pueden declarar como valores NULL.</span><span class="sxs-lookup"><span data-stu-id="6e2bb-104">Value types and structures can be declared nullable.</span></span>

```vb
Dim a? As Integer
Dim b As Integer?
```

 <span data-ttu-id="6e2bb-105">Sin embargo, no puede utilizar la declaración que acepta valores NULL en combinación con la inferencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="6e2bb-105">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="6e2bb-106">En los ejemplos siguientes se produce este error.</span><span class="sxs-lookup"><span data-stu-id="6e2bb-106">The following examples cause this error.</span></span>

```vb
' Not valid.
' Dim c? = 10
' Dim d? = a
```

 <span data-ttu-id="6e2bb-107">**Identificador de error:** BC36629</span><span class="sxs-lookup"><span data-stu-id="6e2bb-107">**Error ID:** BC36629</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6e2bb-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6e2bb-108">To correct this error</span></span>

- <span data-ttu-id="6e2bb-109">Use una `As` cláusula para declarar la variable como un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="6e2bb-109">Use an `As` clause to declare the variable as a nullable value type.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e2bb-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e2bb-110">See also</span></span>

- [<span data-ttu-id="6e2bb-111">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="6e2bb-111">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="6e2bb-112">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="6e2bb-112">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
