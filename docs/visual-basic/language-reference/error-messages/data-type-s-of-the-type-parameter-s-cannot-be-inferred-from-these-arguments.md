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
ms.openlocfilehash: 91ee4bf9242df822890b0a171061f375a3b24cbc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803875"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="6b894-102">Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos</span><span class="sxs-lookup"><span data-stu-id="6b894-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="6b894-103">Tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos.</span><span class="sxs-lookup"><span data-stu-id="6b894-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="6b894-104">Especificar los tipos de datos explícitamente puede corregir este error.</span><span class="sxs-lookup"><span data-stu-id="6b894-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="6b894-105">Este error se produce cuando en caso de error en la resolución de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6b894-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="6b894-106">Se produce como un mensaje subordinado que indica por qué se ha eliminado un candidato de sobrecarga determinado.</span><span class="sxs-lookup"><span data-stu-id="6b894-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="6b894-107">El mensaje de error explica que el compilador no puede usar la inferencia de tipos para buscar tipos de datos para los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="6b894-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b894-108">Al especificar argumentos no es una opción (por ejemplo, para operadores de consulta en expresiones de consulta), el mensaje de error aparece sin la segunda oración.</span><span class="sxs-lookup"><span data-stu-id="6b894-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="6b894-109">El código siguiente muestra el error.</span><span class="sxs-lookup"><span data-stu-id="6b894-109">The following code demonstrates the error.</span></span>  
  
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
  
 <span data-ttu-id="6b894-110">**Identificador de error:** BC36647 y BC36644</span><span class="sxs-lookup"><span data-stu-id="6b894-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b894-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6b894-111">To correct this error</span></span>  
  
- <span data-ttu-id="6b894-112">Es posible que pueda especificar un tipo de datos para el parámetro o parámetros de tipo en lugar de confiar en la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="6b894-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b894-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b894-113">See also</span></span>

- [<span data-ttu-id="6b894-114">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="6b894-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="6b894-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b894-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="6b894-116">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b894-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
