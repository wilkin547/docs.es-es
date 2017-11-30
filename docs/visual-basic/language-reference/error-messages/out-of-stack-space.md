---
title: Espacio de pila insuficiente (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3959c24aa4e95204e156a9863ef0ce237af1fcda
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="d28f8-102">Espacio de pila insuficiente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d28f8-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="d28f8-103">La pila es un área de trabajo de memoria que aumenta y disminuye dinámicamente con las demandas del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="d28f8-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="d28f8-104">Se ha superado su límite.</span><span class="sxs-lookup"><span data-stu-id="d28f8-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d28f8-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d28f8-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="d28f8-106">Compruebe que los procedimientos no están anidados de un nivel demasiado profundo.</span><span class="sxs-lookup"><span data-stu-id="d28f8-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="d28f8-107">Asegúrese de que los procedimientos recursivos terminan correctamente.</span><span class="sxs-lookup"><span data-stu-id="d28f8-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="d28f8-108">Si las variables locales requieren más espacio de variable local que está disponible, intente declarar algunas variables en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="d28f8-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="d28f8-109">También puede declarar todas las variables en el procedimiento estático poniendo el `Property`, `Sub`, o `Function` palabra clave con `Static`.</span><span class="sxs-lookup"><span data-stu-id="d28f8-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="d28f8-110">O bien puede usar el `Static` instrucción para declarar variables estáticas individuales dentro de los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="d28f8-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="d28f8-111">Volver a definir algunas de las cadenas de longitud fija como cadenas de longitud variable, como cadenas de longitud fija usan más espacio de pila que las cadenas de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="d28f8-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="d28f8-112">También puede definir la cadena en el nivel de módulo donde no requiere ningún espacio de pila.</span><span class="sxs-lookup"><span data-stu-id="d28f8-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="d28f8-113">Compruebe el número de anidada `DoEvents` llamadas a funciones, mediante el uso de la `Calls` cuadro de diálogo para ver qué procedimientos están activos en la pila.</span><span class="sxs-lookup"><span data-stu-id="d28f8-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="d28f8-114">Asegúrese de que no ha provocado "eventos en cascada" desencadenando un evento que llama a un procedimiento de evento ya en la pila.</span><span class="sxs-lookup"><span data-stu-id="d28f8-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="d28f8-115">Un evento en cascada es similar a una llamada de procedimiento recursiva indefinida, pero es menos obvio, dado que la llamada se realiza mediante [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] en lugar de una llamada explícita en el código.</span><span class="sxs-lookup"><span data-stu-id="d28f8-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="d28f8-116">Use la `Calls` cuadro de diálogo para ver qué procedimientos están activos en la pila.</span><span class="sxs-lookup"><span data-stu-id="d28f8-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28f8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d28f8-117">See Also</span></span>  
 [<span data-ttu-id="d28f8-118">Ventana Memoria</span><span class="sxs-lookup"><span data-stu-id="d28f8-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
