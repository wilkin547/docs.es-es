---
title: Espacio de pila insuficiente
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 9ae604a9727413f2705d42a4b68f5a50b7dd3feb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349182"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="b1d2c-102">Espacio de pila insuficiente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1d2c-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="b1d2c-103">La pila es un área de trabajo de memoria que aumenta y disminuye dinámicamente con las demandas del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="b1d2c-104">Se han superado sus límites.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b1d2c-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b1d2c-105">To correct this error</span></span>  
  
1. <span data-ttu-id="b1d2c-106">Compruebe que los procedimientos no estén demasiado anidados.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="b1d2c-107">Asegúrese de que los procedimientos recursivos se terminan correctamente.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="b1d2c-108">Si las variables locales requieren más espacio de variables locales que el disponible, intente declarar algunas variables en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="b1d2c-109">También puede declarar todas las variables en el procedimiento static anteponiendo la palabra clave `Property`, `Sub`o `Function` con `Static`.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="b1d2c-110">O bien, puede usar la instrucción `Static` para declarar variables estáticas individuales dentro de los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="b1d2c-111">Vuelva a definir algunas cadenas de longitud fija como cadenas de longitud variable, ya que las cadenas de longitud fija utilizan más espacio de pila que las cadenas de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="b1d2c-112">También puede definir la cadena en el nivel de módulo en el que no se requiere espacio de pila.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="b1d2c-113">Compruebe el número de llamadas a funciones `DoEvents` anidadas mediante el cuadro de diálogo `Calls` para ver los procedimientos que están activos en la pila.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="b1d2c-114">Asegúrese de que no ocasionó un "evento en cascada" desencadenando un evento que llama a un procedimiento de evento que ya está en la pila.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="b1d2c-115">Un evento en cascada es similar a una llamada a procedimiento recursivo no terminada, pero es menos obvio, ya que la llamada se realiza mediante Visual Basic en lugar de una llamada explícita en el código.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="b1d2c-116">Utilice el cuadro de diálogo `Calls` para ver los procedimientos que están activos en la pila.</span><span class="sxs-lookup"><span data-stu-id="b1d2c-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d2c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1d2c-117">See also</span></span>

- [<span data-ttu-id="b1d2c-118">Ventana Memoria</span><span class="sxs-lookup"><span data-stu-id="b1d2c-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
