---
title: Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: b278dcc10a8a4e9e67aacdb16dca2588d2ebd0f1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409794"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="c94cf-102">Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos</span><span class="sxs-lookup"><span data-stu-id="c94cf-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>

<span data-ttu-id="c94cf-103">Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos.</span><span class="sxs-lookup"><span data-stu-id="c94cf-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="c94cf-104">Especificar los tipos de datos explícitamente puede corregir este error.</span><span class="sxs-lookup"><span data-stu-id="c94cf-104">Specifying the data type(s) explicitly might correct this error.</span></span>

<span data-ttu-id="c94cf-105">Este error se produce en caso de error en la resolución de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="c94cf-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="c94cf-106">Se produce como un mensaje subordinado que indica por qué se ha eliminado un candidato de sobrecarga determinado.</span><span class="sxs-lookup"><span data-stu-id="c94cf-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="c94cf-107">El mensaje de error explica que el compilador no puede usar la inferencia de tipos para buscar tipos de datos para los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="c94cf-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="c94cf-108">Al especificar argumentos no es una opción (por ejemplo, para operadores de consulta en expresiones de consulta), el mensaje de error aparece sin la segunda oración.</span><span class="sxs-lookup"><span data-stu-id="c94cf-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>

<span data-ttu-id="c94cf-109">El código siguiente muestra el error.</span><span class="sxs-lookup"><span data-stu-id="c94cf-109">The following code demonstrates the error.</span></span>

```vb
Module Module1

    Sub Main()

        '' Not Valid.
        'OverloadedGenericMethod("Hello", "World")

    End Sub

    Sub OverloadedGenericMethod(Of T)(ByVal x As String,
                                      ByVal y As InterfaceExample(Of T))
    End Sub

    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,
                                         ByVal y As InterfaceExample(Of R))
    End Sub

End Module

Interface InterfaceExample(Of T)
End Interface
```

<span data-ttu-id="c94cf-110">**Identificador de error:** BC36647 y BC36644</span><span class="sxs-lookup"><span data-stu-id="c94cf-110">**Error ID:** BC36647 and BC36644</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c94cf-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c94cf-111">To correct this error</span></span>

<span data-ttu-id="c94cf-112">Es posible que pueda especificar un tipo de datos para el parámetro o parámetros de tipo en lugar de confiar en la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="c94cf-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>

## <a name="see-also"></a><span data-ttu-id="c94cf-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c94cf-113">See also</span></span>

- [<span data-ttu-id="c94cf-114">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="c94cf-114">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="c94cf-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c94cf-115">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="c94cf-116">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c94cf-116">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
