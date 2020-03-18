---
title: Utilizar controladores de excepciones filtradas por el usuario
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
ms.openlocfilehash: 5537404178b746310f720c5b0c075c77287dda4c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708458"
---
# <a name="using-user-filtered-exception-handlers"></a><span data-ttu-id="12444-102">Utilizar controladores de excepciones filtradas por el usuario</span><span class="sxs-lookup"><span data-stu-id="12444-102">Using User-Filtered Exception Handlers</span></span>

<span data-ttu-id="12444-103">Actualmente, Visual Basic admite excepciones filtradas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="12444-103">Currently, Visual Basic supports user-filtered exceptions.</span></span> <span data-ttu-id="12444-104">Los controladores de excepciones filtradas por usuario detectan y controlan las excepciones en función de los requisitos que se definen para la excepción.</span><span class="sxs-lookup"><span data-stu-id="12444-104">User-filtered exception handlers catch and handle exceptions based on requirements you define for the exception.</span></span> <span data-ttu-id="12444-105">Estos controladores utilizan la instrucción **Catch** con la palabra clave **When**.</span><span class="sxs-lookup"><span data-stu-id="12444-105">These handlers use the **Catch** statement with the **When** keyword.</span></span>  
  
 <span data-ttu-id="12444-106">Esta técnica es útil cuando un objeto de excepción concreto corresponde a varios errores.</span><span class="sxs-lookup"><span data-stu-id="12444-106">This technique is useful when a particular exception object corresponds to multiple errors.</span></span> <span data-ttu-id="12444-107">En este caso, el objeto normalmente tiene una propiedad que contiene el código de error específico asociado con el error.</span><span class="sxs-lookup"><span data-stu-id="12444-107">In this case, the object typically has a property that contains the specific error code associated with the error.</span></span> <span data-ttu-id="12444-108">Puede utilizar la propiedad de código de error en la expresión para seleccionar solo el error concreto que desea administrar en esa cláusula **Catch**.</span><span class="sxs-lookup"><span data-stu-id="12444-108">You can use the error code property in the expression to select only the particular error you want to handle in that **Catch** clause.</span></span>  
  
 <span data-ttu-id="12444-109">El siguiente ejemplo de Visual Basic ilustra la instrucción **Catch/When**.</span><span class="sxs-lookup"><span data-stu-id="12444-109">The following Visual Basic example illustrates the **Catch/When** statement.</span></span>  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 <span data-ttu-id="12444-110">La expresión de la cláusula filtrada por el usuario no está restringida en modo alguno.</span><span class="sxs-lookup"><span data-stu-id="12444-110">The expression of the user-filtered clause is not restricted in any way.</span></span> <span data-ttu-id="12444-111">Si se produce una excepción durante la ejecución de la expresión filtrada por el usuario, esa excepción se descarta y la expresión de filtro se considera evaluada como false.</span><span class="sxs-lookup"><span data-stu-id="12444-111">If an exception occurs during execution of the user-filtered expression, that exception is discarded and the filter expression is considered to have evaluated to false.</span></span> <span data-ttu-id="12444-112">En este caso, Common Language Runtime continúa la búsqueda de un controlador para la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="12444-112">In this case, the common language runtime continues the search for a handler for the current exception.</span></span>  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a><span data-ttu-id="12444-113">Combinar la excepción específica y las cláusulas filtradas por el usuario</span><span class="sxs-lookup"><span data-stu-id="12444-113">Combining the Specific Exception and the User-Filtered Clauses</span></span>  
 <span data-ttu-id="12444-114">Una instrucción Catch puede contener tanto la excepción específica como las cláusulas filtradas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="12444-114">A catch statement can contain both the specific exception and the user-filtered clauses.</span></span> <span data-ttu-id="12444-115">El motor de tiempo de ejecución comprueba primero la excepción específica.</span><span class="sxs-lookup"><span data-stu-id="12444-115">The runtime tests the specific exception first.</span></span> <span data-ttu-id="12444-116">Si la comprobación de la excepción específica es correcta, el motor de tiempo de ejecución ejecuta el filtro de usuario.</span><span class="sxs-lookup"><span data-stu-id="12444-116">If the specific exception succeeds, the runtime executes the user filter.</span></span> <span data-ttu-id="12444-117">El filtro genérico puede contener una referencia a la variable declarada en el filtro de clase.</span><span class="sxs-lookup"><span data-stu-id="12444-117">The generic filter can contain a reference to the variable declared in the class filter.</span></span> <span data-ttu-id="12444-118">Tenga en cuenta que no se puede revertir el orden de las dos cláusulas de filtro.</span><span class="sxs-lookup"><span data-stu-id="12444-118">Note that the order of the two filter clauses cannot be reversed.</span></span>  
  
 <span data-ttu-id="12444-119">El siguiente ejemplo de Visual Basic muestra la excepción específica `ClassLoadException` en la instrucción **Catch**, así como la cláusula filtrada por el usuario mediante la palabra clave **When**.</span><span class="sxs-lookup"><span data-stu-id="12444-119">The following Visual Basic example shows the specific exception `ClassLoadException` in the **Catch** statement as well as the user-filtered clause using the **When** keyword.</span></span>  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a><span data-ttu-id="12444-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="12444-120">See also</span></span>

- [<span data-ttu-id="12444-121">Excepciones</span><span class="sxs-lookup"><span data-stu-id="12444-121">Exceptions</span></span>](index.md)
