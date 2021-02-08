---
description: 'Más información acerca de: espacio insuficiente en la pila (Visual Basic)'
title: Espacio de pila insuficiente
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: a32ca0d2becade33177596501b7eabde4251e0a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795497"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="bd1c2-103">Espacio de pila insuficiente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd1c2-103">Out of stack space (Visual Basic)</span></span>

<span data-ttu-id="bd1c2-104">La pila es un área de trabajo de memoria que aumenta y disminuye dinámicamente con las demandas del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-104">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="bd1c2-105">Se han superado sus límites.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-105">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd1c2-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="bd1c2-106">To correct this error</span></span>  
  
1. <span data-ttu-id="bd1c2-107">Compruebe que los procedimientos no estén demasiado anidados.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-107">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="bd1c2-108">Asegúrese de que los procedimientos recursivos se terminan correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-108">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="bd1c2-109">Si las variables locales requieren más espacio de variables locales que el disponible, intente declarar algunas variables en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-109">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="bd1c2-110">También puede declarar todas las variables en el procedimiento static anteponiendo la `Property` `Sub` palabra clave, o `Function` con `Static` .</span><span class="sxs-lookup"><span data-stu-id="bd1c2-110">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="bd1c2-111">O bien, puede usar la `Static` instrucción para declarar variables estáticas individuales dentro de los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-111">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="bd1c2-112">Vuelva a definir algunas cadenas de longitud fija como cadenas de longitud variable, ya que las cadenas de longitud fija utilizan más espacio de pila que las cadenas de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-112">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="bd1c2-113">También puede definir la cadena en el nivel de módulo en el que no se requiere espacio de pila.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-113">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="bd1c2-114">Compruebe el número de `DoEvents` llamadas a funciones anidadas mediante el `Calls` cuadro de diálogo para ver los procedimientos que están activos en la pila.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-114">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="bd1c2-115">Asegúrese de que no ocasionó un "evento en cascada" desencadenando un evento que llama a un procedimiento de evento que ya está en la pila.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-115">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="bd1c2-116">Un evento en cascada es similar a una llamada a procedimiento recursivo no terminada, pero es menos obvio, ya que la llamada se realiza mediante Visual Basic en lugar de una llamada explícita en el código.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-116">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="bd1c2-117">Utilice el `Calls` cuadro de diálogo para ver los procedimientos que están activos en la pila.</span><span class="sxs-lookup"><span data-stu-id="bd1c2-117">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1c2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd1c2-118">See also</span></span>

- [<span data-ttu-id="bd1c2-119">Ventana Memoria</span><span class="sxs-lookup"><span data-stu-id="bd1c2-119">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
