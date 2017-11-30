---
title: "Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b290c25286dce2236823919e8287db9abefc0dd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="41c75-102">Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos</span><span class="sxs-lookup"><span data-stu-id="41c75-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="41c75-103">Tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos.</span><span class="sxs-lookup"><span data-stu-id="41c75-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="41c75-104">Especificar los tipos de datos explícitamente puede corregir este error.</span><span class="sxs-lookup"><span data-stu-id="41c75-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="41c75-105">Este error se produce cuando en caso de error en la resolución de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="41c75-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="41c75-106">Se produce como un mensaje subordinado que indica por qué se ha eliminado un candidato de sobrecarga determinado.</span><span class="sxs-lookup"><span data-stu-id="41c75-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="41c75-107">El mensaje de error explica que el compilador no puede usar la inferencia de tipos para buscar tipos de datos para los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="41c75-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41c75-108">Al especificar argumentos no es una opción (por ejemplo, para operadores de consulta en expresiones de consulta), el mensaje de error aparece sin la segunda oración.</span><span class="sxs-lookup"><span data-stu-id="41c75-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="41c75-109">El código siguiente muestra el error.</span><span class="sxs-lookup"><span data-stu-id="41c75-109">The following code demonstrates the error.</span></span>  
  
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
  
 <span data-ttu-id="41c75-110">**Id. de error:** BC36647 y BC36644</span><span class="sxs-lookup"><span data-stu-id="41c75-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41c75-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="41c75-111">To correct this error</span></span>  
  
-   <span data-ttu-id="41c75-112">Es posible que pueda especificar un tipo de datos para el parámetro o parámetros de tipo en lugar de confiar en la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="41c75-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c75-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="41c75-113">See Also</span></span>  
 [<span data-ttu-id="41c75-114">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="41c75-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="41c75-115">Procedimientos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41c75-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="41c75-116">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41c75-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
